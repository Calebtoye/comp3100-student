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
**Week:** 3
**Work Order No.:** 1851-03

## Milestone 1
**What I did:**
I coded the process that the OS shell uses to run commands.

**Output or seal:**
```~~~ WAX SEAL of the Guild: BA055E04 ~~~
```
**What it means:**
1. Fork created a copy of the calling process. It returns 0 to the child (showing
the fork worked correctly) and the child's PID to the parent to help the parent locate 
the child.
2. Execvp replaces the current running program with another.
3.Waitpid blocks the program from continuing until the child returns with its state.
## Milestone 2
**What I did:**
I explored the idea of a zombie in the OS.
**Output or seal:**
```~~~ WAX SEAL of the Guild: BBDB3293 ~~~
```
**What it means:**
The Z line showed process 1674 in a zombie (uncollected, but finished) state. The 
/proc/<pid>status gave me its parent ID in addition to the name and state. The task one
pantograph does not make Zombie's because its child process continues to run. Since it doesn't
terminate, there cannot be a finished process with data still to be collected (a zombie).
## Milestone 3
**What I did:**
I looked to find and investigate the undeclared job,and the patron responsible.
**Output or seal:**
```~~~ WAX SEAL of the Guild: CC62BF35 ~~~
```
**What it means:**
I found the job by following the child's parent IDs back to their original source. The parentage
lacked a shell as user jobs should have, and the original parent of the loom is gone (the loom tender
is an orphan). Luckily, the system overseer PID 1 picked the loom up and I could investigate it.
This led me to the loom and its table, where I learned everything was done neatly and accurately.
This revealed that a real person is behind the unaccounted work, as the loom doesn't format it,
people do.
> Fewer or more milestones this week? Copy a block above as needed.

## Reflection

1. **(Prompt 1 from the work order):** Splitting fork() and execvp() prevents
the new program from overwriting the current one as the shell can redirect the 
current process elsewhere.
2. **(Prompt 2 from the work order):** A zombie holds no data, but retains its exit 
status that is supposed to be sent back to the parent (which could be cleared with wait).
This causes uncollected table entries will limit the finite tables PID's and can cause crashes after the
zombies accumulate. Orphans are less harmful. They are processes whose parent has been terminated,
and thus they run on their own (undesired), yet are quickly collected and cleaned up by init (PID 1).

## Sources and help

Anyone or anything that helped you this week — a classmate, a man page,
a Stack Overflow answer, an AI assistant. One line each: who or what,
and what you used it for. This is **not graded and never costs points**;
it is the habit professional engineers keep, and the syllabus asks for
it under *Academic integrity* and *Use of AI tools*.

- *(example)* Worked through the `fork` ordering with Sam in studio.
- *(example)* Used an AI assistant to explain what `EAGAIN` means in the trace.

*Nothing to report? Write "None" — that's a perfectly normal week.*
None
## Time spent

Roughly how long this took, start to finish: ___2____ hours
*No wrong answer — this just helps calibrate future work orders.*
