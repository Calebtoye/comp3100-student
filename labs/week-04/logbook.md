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
**Week:** 4
**Work Order No.:** 1851-04

## Milestone 1
**What I did:** I found the CPU usage and process nice values with top after setting up
North and South looms in the other terminal.

**Output or seal:** ~~~ WAX SEAL of the Guild: E9891F11 ~~~
```
```
**What it means:** The nice value (NI) decides which job goes first when two compete, while
%CPU shows how much of the CPU certain processes use. Top showed two processes using
virtually all of the CPU and that had a nice value of 19. The looms report lines/sec are read in a 
process and the process's nice value. Full courtesy on a quiet floor still means full speed because
there are no competing processes with higher priority (negative) nice values.


## Milestone 2
**What I did:** I went to find why the looms would starve when the drill ran and attempted
to solve the issue.

**Output or seal:** ~~~ WAX SEAL of the Guild: D3EB0E13 ~~~
```
```
**What it means:** I knew the loom processes were not working properly by watching their
lines/sec values collapse from ~1000 to less than five.I needed to search for the cause by running
test drills. The drills led me to the consumer process that prevented the loom, and its PPID, paper,
and appointment book showed the time and reason why this process overtakes the loom. This process 
(along with some others) has higher priority because it has a lower nice value, and the process
doesn't even do any valuable work. Thus I had to strike it out to allow the looms to function,
and then renice the processes to ensure all of the processes get CPU time.

## Milestone 3
**What I did:** I discovered the two governers of processes: cGroup quota and FIFO

**Output or seal:** ~~~ WAX SEAL of the Guild: E0EF418A ~~~
```
```
**What it means:** FIFO processes outrank all others, and the highest FIFO has the greatest priority.
The quota caps the allowed CPU% for every individual process. I would trust the quota in a 
public demonstration because it has authority over FIFO processes and can limit the CPU%
regardless of status, so the looms will receive CPU time even if they are not the highest priority.

> Fewer or more milestones this week? Copy a block above as needed.

## Reflection

1. **(Prompt 1 from the work order):** The cGroup quota could have protected the looms
because it could have limited the higher priority process's total allowed CPU percent to use.
This is probably the best option, but less work would get done in total because the CPU is switching
jobs more frequently and working on less urgent jobs. FIFO could also have solved this if the 
looms were given special FIFO priority, but this could have then starved all other processes
that would still need to run. The last option I would choose is ensuring the loom processes
have the lowest nice value (to ensure priority). It has no drawbacks except that any processes
that somehow come in with a FIFO rank will force them to starve. We cannot allow any of these to
overtake the looms when the public is watching.
2. **(Prompt 2 from the work order):** At the bottom of the queue, the scheduler was promising
the looms they would get to run eventually (and "proved" this by letting them run some lines 
occasionally), but they were being starved. Courtesy 19 is a good setting for a job you love
if there is a quota to allow lower priority processes to still be fed, or you know that all
other processes also have a courtesy value of 19.

## Sources and help

Anyone or anything that helped you this week — a classmate, a man page,
a Stack Overflow answer, an AI assistant. One line each: who or what,
and what you used it for. This is **not graded and never costs points**;
it is the habit professional engineers keep, and the syllabus asks for
it under *Academic integrity* and *Use of AI tools*.

- *(example)* Worked through the `fork` ordering with Sam in studio.
- *(example)* Used an AI assistant to explain what `EAGAIN` means in the trace.

*Nothing to report? Write "None" — that's a perfectly normal week.* None

## Time spent

Roughly how long this took, start to finish: ___2____ hours
*No wrong answer — this just helps calibrate future work orders.*
