# Engineer's Logbook

*Honourable Guild of Enginewrights — Ex Vapore, Ordo*

Copy this into your week's folder as `logbook.md` and fill it in as you
work. Paste your wax seals where marked — that's how a milestone gets
marked done.

Write it the way you'd explain the week to a classmate who missed it:
plain sentences, no polish. An honest half-answer under "what it
means" — *I got the seal but I'm still fuzzy on why the second run
differed* — beats a confident sentence you don't believe, and it tells
me where to start when you bring it to studio.

**Name:** Caleb Toye
**Week:** 7
**Work Order No.:** 1851-07

## Milestone 1
**What I did:** I investigated a deadlock in the engine by finding the time processes
began to hold.

**Output or seal:**
```~~~ WAX SEAL of the Guild: 8FB23102 ~~~
```
**What it means:**
 Northgate ........ hold taken 1851-09-26 18:51:07 (second 7)
  Waterside ........ hold taken 1851-09-26 18:51:21 (second 21)
  Old Quarter ...... hold taken 1851-09-26 18:51:35 (second 35)
  Kiln Row ......... hold taken 1851-09-26 18:51:49 (second 49)
  
  All are 14 seconds apart.
  The engine must release a process to ensure it runs smoothly. It chooses Kiln Row
  which entered last and because it has the smallest amount of the ring's work to lose.
  
  day .............. Saturday, 26 September 1851
  entered: 1851-09-23

## Milestone 2
**What I did:** I explored which levers wait for other levers and where the deadlock occurred.

**Output or seal:** ~~~ WAX SEAL of the Guild: 7ED21DDD ~~~
```
```
**What it means:** 0x0000555555555a8a in take_lever (district=0x555555556028 "Kiln Row", lever=0x5555555580c0 <lever_northgate>) at ring-frame.c:127
#4  0x0000555555555a8a in take_lever (district=0x55555555601c "Old Quarter", lever=0x555555558180 <lever_kilnrow>) at ring-frame.c:127
#4  0x0000555555555a8a in take_lever (district=0x555555556012 "Waterside", lever=0x555555558140 <lever_oldquarter>) at ring-frame.c:127
#4  0x0000555555555a8a in take_lever (district=0x555555556008 "Northgate", lever=0x555555558100 <lever_waterside>) at ring-frame.c:127
Lever numbers above, all stopped at line 127.
Kiln Row waits for Northgate, Northgate waits for Waterside, Waterside waits for Old Quarter, Old Quarter waits for Kiln Row.
Find thread Name with thread N showed which lever was waiting on which, and print holding
showed what it was holding. The ring cannot break itself because each lever is holding
a lever that another lever wants simultaneously, and so no process can run since they are all
waiting (holding themselves) until they receive other levers (which cannot happen).
## Milestone 3
**What I did:** I checked all 4 of the deadlock conditions and broke the deadlock
with disabling the resource preemption.

**Output or seal:**
```~~~ WAX SEAL of the Guild: FDE452E7 ~~~
```
**What it means:**
Mutual Exclusion: I used print lever and info threads to show that in this case the owner of
the thread is also the same as the thread the lever holds.
Hold and Wait: exploring holding and take_lever proved all levers were holding their own lever
while also waiting for another lever. This prohibited any lever from actually running.
Resource Preemption: gdb continue shows nothing is taking levers because the lever must be released
before it is taken, and no levers are being released because they need another lever first. take_lever
in mutex also proves the levers are not being released properly.
Circular Wait: pipe thread apply all bt | grep take_lever shows all levers getting stuck at
the same line because they all wait on something someone else has at the same time, so nothing
ever gets done. 

The release order broke preemption because the youngest claim was required to release
its lever so another process could take it. This wasn't circular wait because a
lever had to be released manually (it wouldn't release itself) due to preemption in
order to solve the other issues such as circular wait.
This broke the deadlock and every lever could run at the cost
of the youngest claim going last. The youngest claim was chosen because making it go last
sacrifices the least overall.

> Fewer or more milestones this week? Copy a block above as needed.

## Reflection

1. **(Prompt 1 from the work order):** A deadlock needs mutual exclusion, hold and wait,
resource preemption, and circular wait all at once because they work together to prevent 
any process from running and releasing its data for other processes to run all at the same
time. No process is willing to release data without first receiving some and in the case of a
deadlock this means no process will ever run. Breaking one of these issues allows one process to
receive the data it needs to run and then all of them can then run because they will all be given
access to the date they need. When all levers need a resource that isn't being released, circular 
wait is not the solution. You need resource preemption authority to have a resource become available.
If everything is holding and waiting, mutual exclusion is the wrong fix because resources
cannot access resources that are being held by others, and you need to allow one program to stop
waiting and run first.
2. **(Prompt 2 from the work order):** Stopping a machine from deadlock would prevent errors,
but could limit user freedom (starvation could be cause to some processes)
and possibly hurt run time. Allowing deadlock but having deadlock
recovery methods saves user freedom (all processes run) and run time while providing easy ways to debug a system.
With this reasoning, I would rather a system that can deadlock but provides ways to debug, as 
this creates a greater ceiling for process optimization than could be generated with complete
deadlock prevention.

## Sources and help

Anyone or anything that helped you this week — a classmate, a man page,
a Stack Overflow answer, an AI assistant. One line each: who or what,
and what you used it for. This is **not graded and never costs points**;
it is the habit professional engineers keep, and the syllabus asks for
it under *Academic integrity* and *Use of AI tools*.

- *(example)* Worked through the `fork` ordering with Sam in studio.
- *(example)* Used an AI assistant to explain what `EAGAIN` means in the trace.

*Nothing to report? Write "None" — that's a perfectly normal week.*

## Time spent

Roughly how long this took, start to finish: _______ hours
*No wrong answer — this just helps calibrate future work orders.*
