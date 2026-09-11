# Case Notes

*Honourable Guild of Enginewrights — Ex Vapore, Ordo*

Copy this into your repo root as `case-notes.md` (or wherever your
work order says) and keep it running all semester. Add one row every
week for anything odd you notice while you work — even if you're not
sure it matters yet. Small, plain notes are more useful later than
you'd expect.

The skill this builds is noticing; explaining comes later, sometimes
weeks later. A half-formed note beats a tidy one you meant to write
and never did.

## The ledger

| Week | What I found | Where/how | What I think it means |
|---|---|---|---|
| 1: | 8 | 21 | 26 | I found that the shell is directly asking the kernel to fulfill commands,
and the kernel grants permission for hardware memory. I was showed this
as the kernel would reject my commands from the shell that were not formatted correctly, while it ran those
that were formatted correctly such as the manual commands. I believe this reason is to protect
my hardware from damage that could be caused from certain commands.
| 2: | 8 | 26  | 26  | Never ignore a warning, as it is a fault that will occur at runtime.An
error return is an answer, not a crash.Sometimes the program is unaware or fails to share
all of the errors occuring in the program, so we must check it with strace (using system-call).
wc -l ~/.ledger-annex was the hidden file. It stated: 12 June — 6 hrs computed by hand, uncompensated. — your diligent servant
Perhaps the uncompensated hours are from one of the fired computers seeking for more work and
pay from the machine, while doing it under the table to avoid conflict.

| 3: | 9 |3  |26  | TABLE OF PRODUCTS -- computed by hand, entered fair, in ink. This week
I found how to search for processes using
the parent ID, and explored both why zombies occur (when missing wait()) and that orphans can 
still be located through the system init (PID 1) when following the ancestry line of parents from a
process. This gave me the table (from the loom process) where I have found the neat work that
is unaccounted for, by patron E.K. The person who did this work was not a machine, and initialed E.K. 
They were trained and intentional in this programming as they deliberately made their program
an orphan whose information could not be obtained from the original parent.
| 4: |  |  |  |
| 4: |  |  |  |
| 4: |  |  |  |
| 4: |  |  |  |
| 4: |  |  |  |
| 4: |  |  |  |
| 4: |  |  |  |
| 4: |  |  |  |
| 4: |  |  |  |
| 4: |  |  |  |


Add more rows as the weeks go on. Keep entries short — a sentence or
two per column is plenty, and a note that turns out to be nothing
costs you nothing.

- **What I found** — the plain fact. Just what you saw.
- **Where/how** — the file, command, or tool that showed it to you.
- **What I think it means** — your own read on it. Guesses are fine;
  label them as guesses if you're unsure, and "no idea yet" is a
  perfectly legitimate entry.

## Current suspicions

*Free-write space. What's your running theory? What doesn't add up
yet? Revise this section any week — nobody's grading you on being
right early, only on citing your own notes later.*

(write here)
How does my system know to give me wax seals (and which to give) 
even though those aren't pre-installed into the powershell?
  After investigation of the loom, it seems there is a human doing unaccounted work 
for the engine. My suspicion is that the patron being E.K. has something to do with it
(perhaps initials of the person), and that they were an old programmer before the engine. 
Their motive, I am still unsure of. I don't think they are trying to hurt the machine (the work)
appears to be well done, and not a bug), but wonder why their work is hidden. My best guess is'
they are out of a job and somehow want to generate revenue either through payroll from the machine
or by taking some credit for it upon its release that will grant ownership/fame to generate income.
---

*Tip: if two weeks' findings seem to point the same direction, say so
in a note — connecting your own dots across weeks is exactly the
skill this ledger is for.*
