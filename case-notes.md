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
| 4: |  9|  9|  26| 14 15 * * * $HOME/enginehouse/machinery/amendment-314.sh # Dispatch Board Amendment No. 314 — by order of ███
#              Moved, seconded, and carried without division.
#                                        By order of ███  . Only a human could've written the 
amendment process so well. They would have to drop their pride of the guild (and as a professional)
to amend such processes in a sloppy or informal manner to fake their identity. They will not do this,
but instead have at least covered their name from being seen.This is not the way to hurt the house,
but it does make the loom look bad in public. Perhaps the human is attempting to make the machine
appear to fail more than it should, such that the guild should need to hire more self-computers again.
That might be the perfect solution for a fired computer who currently resides out of a job.
| 5: | 9 |  16|26  | computed loss, million gallons .. 0.518
  district balance, pounds ........ 214.08  (computed engine)
  as opposed to: computed loss, million gallons .. 0.517
  district balance, pounds ........ 214.06 (measured fair copy)
  My figures from adding (with awk and on paper to save the last decimal place) the culvert
  losses and district balances: 0.5170 loss, 214.060 balance.
  The annex's closing line (IX) : entered fair, in ink, from the working papers
  I believe the issue stems from a rounding error. Perhaps rounding before adding.
  The processes move together in the same way and proportionate size, making them 
  correspondent and perhaps linear processes that run very similarly.
| 6: |  9| 21 |26  | Oddly enough, the name spot for the 1849 UID declares that is does not
have a name, only a number. Strange it would have a name spot if no name could be given.
held by, uid ..... 1849
session opened: 1851-09-18 18:40
taken: 1851-09-21 04:12
 holder present ... no. Nothing of that hand is on the floor, and
                     nothing of that hand is running.
Roll's description field: computator:x:1849:100:Computing Room corps, pending archive transfer:/home/computator:/usr/sbin/nologin
For a lock to outlive the holder, the holder must have had an error or was unexpectedly terminated. It might
also have just not provided a function to unlock the CPU after it finished. Keeping the records
in separate places helps the culprit behind the machine questioning because the user has to dig
harder to find all of the information. Not much work generally happens this early, but perhaps
setup for the machine's running of the day. The chief Enginewright Marlowe should oversee this work. 
Based on these times, someone must be coming shortly before and after the workday is complete to edit
the machine, unless they are an inside worker who has been making unauthorized changes this entire time.
| 7: |  9|  30| 26 | day .............. Saturday, 26 September 1851

  Northgate ........ hold taken 1851-09-26 18:51:07
  Waterside ........ hold taken 1851-09-26 18:51:21
  Old Quarter ...... hold taken 1851-09-26 18:51:35
  Kiln Row ......... hold taken 1851-09-26 18:51:49
  
   Rule 2. The duty enginewright files a release order naming ONE box, and
     one only: the box whose claim is youngest -- that is, the box that
     took its hold last. It has held its lever the shortest while, and
     so it has the smallest share of the ring's work to lose by standing
     back.
     
     Kiln Row     release order honoured. Lever back to normal; waiting its turn.
  This does not appear to be an accident because all trains were to jam exactly 14 seconds
  after each other. Very precise, unlike most accidents. The manual was updated 3 days before the
  order, meaning that the machine should have known how to avoid this error. It does go to
  show that the manual is for humans to set up the machine, rather than the machine to interpret itself.
  Only a knowledgeable computer would know this regarding a signal frame, and this knowledge
  could allow them to really stop up the machine's work.
| 8: |  10| 14 |  26| store-siphon: 52 blocks drawn from the Store; none returned.
store-siphon: the cap is reached. Resting. ==862== 0x4AA6C40[72]
==862== 0x4AA6CD0[38]
==862== 0x4AA6D40[36]
==862== 0x4AA6DB0[71]1:/* store-siphon -- draws from the Store and keeps what it draws.  -- E.K. */
6:/* Never more than this. The Engine shall not want for a block on my account.  -- E.K. */
13:/* The draft is kept in cipher on paper; the Store keeps the fair copy.  -- E.K. */
61:/* A fair copy is never written over. A new block for every hand.  -- E.K. */
E.k. has ensured these lines stay leaked because he wants them to be noticed. The cap prevents
more data from being allocated. This means the engine can only borrow as much data that the store
allows to be rented. Next I would want to explore the draw-block malloc, and I would follow
a similar process of reading the lines with vgdb, monitor leak check, and x/s.
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
There appears to be many small errors or inconsistencies within many of the engines functions, yet
I am not entirely sure if the 'dilligent servant' is trying to solve these, or has secretly hid them
in. Whatever the case, they have been working odd hours and covered their tracks well.

---

*Tip: if two weeks' findings seem to point the same direction, say so
in a note — connecting your own dots across weeks is exactly the
skill this ledger is for.*
