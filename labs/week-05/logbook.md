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
**Week:** 5
**Work Order No.:** 1851-05

## Milestone 1
**What I did:** I set up two looms that run concurrently to view their combined entries.

**Output or seal:**
``` ~~~ WAX SEAL of the Guild: AB2DDCB5 ~~~
```
**What it means:** The Loom North and Loom South entries both are 200,000 entries that should
all be run by the CPU and thus the total line below should be 400,000. This total line happens
to be running short by 100,000-150,000 entries. The two independent looms should be trusted as
their entries are totaled before the looms processes combine (and totals could be
overwritten at times), and the repetition of the incorrect
total proves something must be wrong with the totaling function of the process.

## Milestone 2
**What I did:** I fixed the two looms total counter.

**Output or seal:**
```~~~ WAX SEAL of the Guild: 8D7A745E ~~~
```
**What it means:** The two entries were going into the same counter at the same time (total++),
and so many entries were getting overwritten. The added lines ensure only one loom enters the
guarded total section at a time, so every total is accounted for. The woven command stayed outside
because it belongs to one loom, so putting it inside would just add unnecessary run time, which is
a downside of guarded runs.

## Milestone 3
**What I did:** I explored differences in losses and balance depending on which source 
I asked for the values, or if I did it myself.

**Output or seal:**
```~~~ WAX SEAL of the Guild: 70DAB71D ~~~
```
**What it means:** The engine computed has .518 loss and 214.08 balance, while the fair copy
has .517 losses and 214.06 balance along with the engine measured.
My final loss found was .517 and final balance sum was
214.06, meaning my work corresponded with the fair copy, and both disagreed with the engine
computed as the engines values were .001 extra loss and .02 extra balance. 
This occurred because figures should be added before rounding, which the engine clearly is not obeying.

> Fewer or more milestones this week? Copy a block above as needed.

## Reflection

1. **(Prompt 1 from the work order):** Five runs doesn't prove that the data race is gone
from a critical section, as certain cases (particularly smaller) can slip through the cracks,
but the more test cases ran means the more likely the data race is gone. Unguarded runs would
have incorrect totals as values running concurrently through a data section will miss count updates.
A proof to avoid a data race would have to ensure passing through a guard in the critical section,
and the tests passing every time with large enough data sets to avoid error.
2. **(Prompt 2 from the work order):** I would be willing to tell the board that the machine
engines numbers are incorrect with more than one source of inconsistency. I would want to see
a consistent error in the sums, and would reject just one run with difference or only one source
in disagreement. In this case, I must at least approach the board and inform them of value
inconsistencies so there are not missed numbers later on.

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

Roughly how long this took, start to finish: _2______ hours
*No wrong answer — this just helps calibrate future work orders.*
