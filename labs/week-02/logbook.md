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
**Week:** 2
**Work Order No.:** 1851-02

## Milestone 1
**What I did:**
1. The compiler caught an error of a missing header file when I tried to run the program.
2. The compiler suggests I am missing a character in my compare operation.
3. ASan recognized that my for loop was repeating too many times.
4. Valgrind stated I was attempting to use an uninitialized value.
**Output or seal:**
``` ~~~ WAX SEAL of the Guild: B641F0B1 ~~~
```
**What it means:**
1. I needed to add the #include <string.h> at the top.
2. I needed to add an equal sign in my if statement to make it comparison rather than assignment.
3. I needed to reduce the loop duration by one by changing <= comparison to just <.
4. I needed to initialize the total variable to start at 0.

## Milestone 2
**What I did:**
I made sure my program was running correctly by checking errors with -c strace. 
I was then directed to use -e strace for a more detailed description of my errors.

**Output or seal:**
```~~~ WAX SEAL of the Guild: 1BEC440E ~~~
```
**What it means:**
The count table showed I had 1 Openat error (out of 5 calls) and one write error (out of 2 calls). 
-e trace proved I had an error opening the card reader file, and that a 77 byte file was
written to without the program telling me. 
## Milestone 3
**What I did:** 
I checked the system-call record and compared it with the program's printed output to
see if there were any differences.

**Output or seal:**
``` ~~~ WAX SEAL of the Guild: A6D355D8 ~~~
```
**What it means:**
The system-call record is a truer account to follow than the printed output as the system call has the
ability to go into kernel mode, which is where more private information is kept hidden from the user unless 
permission is granted to access it. This differs from printed output as user mode can only give what the program
has access to, which sometimes misses calls that interact with other programs or hardware.
> Fewer or more milestones this week? Copy a block above as needed.

## Reflection

1. **(Prompt 1 from the work order):** The kernel's record is the authoritative one
because kernel mode (which it runs in) can access all programs and hardware. The print output
may only access that program (being in user mode) and thus cannot see underlying system calls
that involve hardware or other programs.
2. **(Prompt 2 from the work order):** C needs all three checkers because it allows more access
to kernel mode which can easily affect the hardware if bad code is unchecked. In other languages,
much of the under-the-cover tools that can affect hardware are hidden and not seen in user mode, so
less safety checks are necessary.

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
