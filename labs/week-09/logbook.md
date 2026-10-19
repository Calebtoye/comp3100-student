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
**Week:** 9
**Work Order No.:** 1851-09

## Milestone 1
**What I did:**
slip         (asked for while running)    0x57536a4142a0  :heap, memory asked for while running.
main         (the program's own routine)  0x5753307a41c9  :text, the programs own machine code
on_hand      (a variable inside main)     0x7ffde400a0fc  :stack, local variable called in main
tally_kept   (set before the start)       0x5753307a7010  :data, a value is given before start
spare_slips  (never set at all)           0x5753307a7040  :bss, an initialized variable set to 0 at program start.
slip         (asked for while running)    0x5d9171b162a0
main         (the program's own routine)  0x5d916b2a21c9
on_hand      (a variable inside main)     0x7fffb1151c2c
tally_kept   (set before the start)       0x5d916b2a5010
spare_slips  (never set at all)           0x5d916b2a5040

high to low run 1:
on_hand      (a variable inside main)     0x7ffde400a0fc
slip         (asked for while running)    0x57536a4142a0
spare_slips  (never set at all)           0x5753307a7040
tally_kept   (set before the start)       0x5753307a7010
main         (the program's own routine)  0x5753307a41c9

high to low run 2:
on_hand      (a variable inside main)     0x7fffb1151c2c
slip         (asked for while running)    0x5d9171b162a0
spare_slips  (never set at all)           0x5d916b2a5040
tally_kept   (set before the start)       0x5d916b2a5010
main         (the program's own routine)  0x5d916b2a21c9

**Output or seal:**
```~~~ WAX SEAL of the Guild: 8F513B1B ~~~
```
**What it means:**
The addresses of the runs changed, the order did not.
There is no column for heap and stack because their size cannot be known
until while the program is running because they wait on user input.

## Milestone 2
**What I did:** The 7 contexts:
==1791== Invalid write of size 1
==1791==    by 0x1092F1: enter (store-clerk.c:38)
==1791==  Address 0x4a760a7 is 0 bytes after a block of size 7 alloc'd
==1791==    by 0x109295: enter (store-clerk.c:33)

==1791== Invalid write of size 1
==1791==    by 0x1092F1: enter (store-clerk.c:38)
==1791==  Address 0x4a76158 is 0 bytes after a block of size 8 alloc'd
==1791==    by 0x109295: enter (store-clerk.c:33)

==1791== Invalid write of size 1
==1791==    by 0x1092F1: enter (store-clerk.c:38)
==1791==  Address 0x4a7620f is 0 bytes after a block of size 15 alloc'd
==1791==    by 0x109295: enter (store-clerk.c:33)

==1791== Invalid write of size 1
==1791==    by 0x1092F1: enter (store-clerk.c:38)
==1791==  Address 0x4a762bb is 0 bytes after a block of size 11 alloc'd
==1791==    by 0x109295: enter (store-clerk.c:33)


==1791== Invalid read of size 4
==1791==    at 0x1093F6: main (store-clerk.c:67)
==1791==  Address 0x4a76260 is 16 bytes inside a block of size 24 free'd
==1791==    by 0x109338: strike (store-clerk.c:48)


==1791== Invalid read of size 1
==1791==    by 0x10944D: main (store-clerk.c:71)
==1791==  Address 0x4a7620f is 0 bytes after a block of size 15 alloc'd
==1791==    by 0x109295: enter (store-clerk.c:33)


==1791== 102 (24 direct, 78 indirect) bytes in 1 blocks are definitely lost in loss record 6 of 6
==1791==    by 0x109249: enter (store-clerk.c:27)

The 3 faults:
==1791== Invalid write of size 1
==1791==    by 0x1092F1: enter (store-clerk.c:38)


==1791== Invalid read of size 4
==1791==    at 0x1093F6: main (store-clerk.c:67)


==1791== 102 (24 direct, 78 indirect) bytes in 1 blocks are definitely lost in loss record 6 of 6
==1791==    by 0x109249: enter (store-clerk.c:27)
**Output or seal:**
```~~~ WAX SEAL of the Guild: 1A6E8F38 ~~~
```
**What it means:**
strcpy copies the null terminator which goes into index 7.
The write report left because the null terminator issue was fixed, so writes could
be done successfully.The next error allowed the clerk to read what it needs before
it surrenders the slip. The third error needed the slips to hand their data back properly
to fix a data leak. The sixth report was an echo.

==2078== HEAP SUMMARY:
==2078==     in use at exit: 0 bytes in 0 blocks
==2078==   total heap usage: 9 allocs, 9 frees, 1,165 bytes allocated
==2078==
==2078== All heap blocks were freed -- no leaks are possible
==2078==
==2078== For lists of detected and suppressed errors, rerun with: -s
==2078== ERROR SUMMARY: 0 errors from 0 contexts (suppressed: 0 from 0)

## Milestone 3
**What I did:** store-siphon: 52 blocks drawn from the Store; none returned.
store-siphon: the cap is reached. Resting.
217 bytes in 4 blocks are definitely lost in loss record 1 of 2
by 0x109263: fair_copy (store-siphon.c:65)
(routine fair copy, line 65, average 217/4 = 54.25 bytes per block.)
196,608 bytes in 48 blocks are definitely lost in loss record 2 of 2
by 0x1091FE: draw_block (store-siphon.c:53)
(routine draw_block, line 53, average 196,608/48 = 4096)
==522== LEAK SUMMARY:
==522==    definitely lost: 196,825 (217+196,608) bytes in 52 blocks (48+4)
store-siphon: 52 blocks drawn from the Store; none returned. (52 blocks, all leaked)
cap: 48
The mallocs match.

**Output or seal:**
```~~~ WAX SEAL of the Guild: 95E9B758 ~~~
```
**What it means:** Many bytes of data are being borrowed from different mallocs and 
not returned back to the store.

## Milestone 4
**What I did:** 1:/* store-siphon -- draws from the Store and keeps what it draws.  -- E.K. */
6:/* Never more than this. The Engine shall not want for a block on my account.  -- E.K. */
13:/* The draft is kept in cipher on paper; the Store keeps the fair copy.  -- E.K. */
61:/* A fair copy is never written over. A new block for every hand.  -- E.K. */
All signed by E.k.
"To the Board of the Enginehouse, and to its guests at the Exhibition --"
"...they called our work superseded..."
"...they called our work obsolete..."
"A tool is obsolete. We were never the tool; we were the check upon it."

addresses and lines from valgrind and gdb with vgdb, monitor leak check, and x/s:
==862== 0x4AA6C40[72]
==862== 0x4AA6CD0[38]
==862== 0x4AA6D40[36]
==862== 0x4AA6DB0[71]
4 total leaked blocks.
**Output or seal:**
```~~~ WAX SEAL of the Guild: E3B07045 ~~~
```
**What it means:** These data leaks appear to be intentional efforts for E.K. to get
a message across.

> Fewer or more milestones this week? Copy a block above as needed.

## Reflection

1. **(Prompt 1 from the work order):** Heaped memory leaks as long as the process is running.
Thus, the leak is capped when the process ends, and so the longer it runs the more memory
that is leaked. Indirectly lost leaks are leaks caused from the main leak, and so the definitely]
lost memory is the memory that should be prioritized in ending to stop a data leak.
2. **(Prompt 2 from the work order):** A program that prints the right answer is not always correct.
Many test cases should be ran to ensure the program prints the right answer every time, even with
strange inputs. The program answer could also be correct and yet the high runtime or memory usage/lost
memory could hurt the hardware or efficiency of the software. I would want to check my program
could pass numerous test cases with an efficient runtime and memory usage without definitely lost
data leaks.

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
