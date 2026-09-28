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
**Week:** 6
**Work Order No.:** 1851-06

## Milestone 1
**What I did:** I changed a mutual exclusion mechanism to a conditional variable
to stop unnecessary checks.

**Output or seal:**
```~~~ WAX SEAL of the Guild: 883642FC ~~~
```
**What it means:** The CPU can now save power by resting, or perhaps focus more on other
processes. The engine still belongs to the OS scheduler (inside the kernel) that will 
decides when and what it will run. My figures recorded from my bench:
Broken- trains booked through: 120000
  crossings a second train came onto the line during: 77148
  day-book entries found in another hand: 101257
Fixed- trains booked through: 120000
  crossings a second train came onto the line during: 0
  day-book entries found in another hand: 0

## Milestone 2
**What I did:** I used a semaphore to stop overruns and empty reaches.

**Output or seal:** ~~~ WAX SEAL of the Guild: 2DA46117 ~~~
```
```
**What it means:** Room counts the number of free spaces open in the chute,
while cards-waiting counts the cards currently sitting in the chute. sem_wait(&room)
is outside the mutex to prevent a deadlock since it needs other process to run before
it goes to mutex. The mutex is still necessary to count the buffer slots accurately.
The bell proves that a card has been processed correctly.

## Milestone 3
**What I did:** I added a reader/writer lock.

**Output or seal:**
```~~~ WAX SEAL of the Guild: 85DAAF22 ~~~
```
**What it means:** The clerk's write column needed to be locked by one major lock to
ensure no district's data is overwritten. It is better to have six readers into a reader
lock rather than a mutex because multiple readers can read at once without overwriting data,
and a mutex would slow the process down. A torn read is a read error when th process is read
at the wrong time (often concurrently with another process) so the read is incomplete. A 
single mutex would pass a test case because there are no other reads, and starvation is when
a process is not executed because other processes take priority or must run before it.

## Milestone 4
**What I did:** I discovered an issue where processes become blocked by each other.

**Output or seal:** ~~~ WAX SEAL of the Guild: F4BE746C ~~~
```
```
**What it means:**Aurelia holds fork 0, she wants 1, which Bramwell holds.
Bramwell takes fork 1, he wants fork 2, which Cordelia holds.
Desmond has fork 3, wants fork 4, which Eustace holds.
Eustace takes fork 4, wants fork 0, which Aurelia holds.
Everyone holds a fork that someone else wants at the same time, which causes a block 
that cannot be broken.
## Milestone 5
**What I did:**

**Output or seal:** 
```~~~ WAX SEAL of the Guild: 2A5CA4EF ~~~
```
**What it means:**
Lever 07 is held.
The lock is owned by uid 1849 and nothing of that uid is running.
The roll has an entry for 1849, and its description says what that account was for.
Its login shell says whether anybody was meant to sign in as it.
Produced by: cat ~/enginehouse/interlocking/lever-07.lock
> Fewer or more milestones this week? Copy a block above as needed.

## Reflection

1. **(Prompt 1 from the work order):** Mutex allows a critical section of code to only work
one process at a time. This prevents overwrites, but can become not as efficient without a 
conditional variable to put it to sleep while it runs a process. Because it is running only
one process at a time, it can lead some processes to be starved (not ran).

The 2 semaphores work together as an increment and decrement counter that decide if a process
is to sleep or wake and run. The bounded buffer can prevent certain processes from taking up
too much CPU and helps prioritize the processes that are divided between consumer and producer.
Their numbering and bounded buffer make them unique and helps prevent more overruns.

The reader/writer lock differentiates between readers and writers in a critical section.
This is because readers cannot overwrite data, but writing can, making it crucial to manage
correctly. Starvation can occur if many readers are coming in and stop the writing of new data.
The reader/writer specialization is the unique feature here as it is an alternative to mutex
in preserving data regardless of updates.
2. **(Prompt 2 from the work order):** In testing, you want many inputs and trials to ensure
the finished product has very minimal error of failing. I would first run this many times with 
varying test cases, then have my colleagues look over my work. Following those checks,
I would be willing to present to the board as my code would've passed many trial runs and
intelligent individuals by that point, severely limiting the risk of failure.

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

Roughly how long this took, start to finish: ____3___ hours
*No wrong answer — this just helps calibrate future work orders.*
