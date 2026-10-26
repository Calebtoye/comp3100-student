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
**Week:** 10
**Work Order No.:** 1851-10

## Milestone 1
**What I did:**
r, rw, r-x, r--s, anon, stack, heap
Storeroom:
gcc -Wall -Wextra -g -O0 -o storeroom storeroom.c
gcc -Wall -Wextra -g -O0 -o glutton glutton.c
storeroom: 256 pages (1024 KiB) requisitioned, nothing shelved yet.
  resident now: 1548 KiB
first round -- one item onto each of the 256 shelves:
  minor page faults: +267
  resident now:      +1276 KiB
second round -- over the same 256 shelves again:
  minor page faults: +0
  resident now:      +0 KiB
**Output or seal:**
```~~~ WAX SEAL of the Guild: ABB554A4 ~~~
```
**What it means:**
VmSize:     6212 kB
VmRSS:      5404 kB
The difference is due to demand paging where virtual memory is not being physically stored 
(virtual memory is promised but not yet being used).
## Milestone 2
**What I did:**
Governed run:
Running as unit: run-r04ad4548d0af4b41b9d059c85e34acf1.scope; invocation ID: 6017dfc31be34c6ba3a02be1c26ff812
taken: 16 MiB
taken: 32 MiB
taken: 48 MiB
Killed
Exit status: 137
Verdict:
Oct 19 20:05:53 Calebslaptop systemd[349]: run-r04ad4548d0af4b41b9d059c85e34acf1.scope: Failed with result 'oom-kill'.
Oct 19 20:05:53 Calebslaptop systemd[349]: app.slice: A process of this unit has been killed by the OOM killer.
**Output or seal:**
```~~~ WAX SEAL of the Guild: 457EB20E ~~~
```
**What it means:**
Failed with result 'oom-kill'; MemoryMax=64M.
The overseer stops the process to limit its memory usage.
## Milestone 3
**What I did:**
Name:   record-keeper
PPid:   1
Uid:    1849    1849    1849    1849
VmSize:     3584 kB
VmRSS:       284 kB

72edf3c33000-72edf3d33000 ---p 00000000 00:00 0

denied commands: 1. cat /proc/$PID/maps
2.  tr '\0' ' ' < /proc/$PID/cmdline; echo      # 1. what it was started as
grep -E '^(Name|Uid|PPid|VmSize|VmRSS):' /proc/$PID/status   # 2. who and what it is
tr '\0' '\n' < /proc/$PID/environ           # 3. what it was handed
/home/ubuntu/enginehouse/survey/record-keeper

**Output or seal:**
```~~~ WAX SEAL of the Guild: 1DD7F597 ~~~
```
**What it means:**
---p, 1024 -- KiB it belongs to another account, so its memory is
walled off from mine without the house keys.

## Milestone 4
**What I did:** My answers: uncut, 1830 1831 1831 1833 1834 1835 1836 1837 1838 1839 1840 1841
1842 1843 1844 1845 1846 1847 1848 1849 desk K,
KUREOS THISTLEWOOD


**Output or seal:**
```~~~ WAX SEAL of the Guild: 296321E9 ~~~
```
**What it means:** We received:
BRASSBRIDGE ENGINEHOUSE -- OLD COMPUTING ROOM
Preserved records of the computer corps, held whole for the
Exhibition archive, uncut, as the archivist received them.
  THE CHIEF COMPUTER'S RECORD
  KUREOS, I. M. -- Chief Computer, retired without pension, 1849.
  DESK-MARK ROSTER
  E.K. = East gallery, desk K -- the Chief Computer's station.
  Held by KUREOS, I. M., 1830-1849.
  WIND-DOWN ROTA
THISTLEWOOD, N. -- seconded 1848; desk K, East gallery, at the wind-down.
  -- entered by the archivist. No conclusion is drawn.

> Fewer or more milestones this week? Copy a block above as needed.

## Reflection

1. **(Prompt 1 from the work order):** The record states two members (Kureos/Thistlewood) who used to work for the engine
from 1830-1849, yet only one truly retired. This data was at desk K. We now know E.K.
is not a person, but rather a place. 
The record does not say the archivist after Thistlewood seconded the report.
2. **(Prompt 2 from the work order):** This record was walled off because somebody does
not want this record to be accessed. They likely are behind the machines abnormalities.
This process memory is much more temporary and difficult to access than RAM as it is not
physical memory.
3. **(Prompt 3 from the work order):** Next I would want to search for processes that may
give more information about the archivist. Perhaps grep could assist me in this.

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

Roughly how long this took, start to finish: __2_____ hours
*No wrong answer — this just helps calibrate future work orders.*
