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
**Week:** 1
**Work Order No.:** 1851-01

## Milestone 1
**What I did:**
1. I prompted the kernel to state its name using the uname -a command.
2.I counted all of the command system's call, which means the system called various commands 
and checked the time, total calls, and total errors for each system call.
3. I asked for the current C compiler version.
4. I opened and closed manual 2 with the man 2 command.
**Output or seal:**
``` ~~~ WAX SEAL of the Guild: 918F632F ~~~
```
**What it means:**
1. My powershell is running Ubuntu correctly, and my system is set up to run linux commands.
2. I can tell which system calls are running correctly and I can now compare call times and their efficiency.
3. My C compiler version is updated and accurate.
4. My man 2 linux command works correctly and I can read manual 2.
## Milestone 2
wc -l counts lines: twelve rows, the standard height of a punched card. 
**What I did:** I explored the four different rooms (inbox, ledger, machinery, spool) 
of the enginehouse through various commands. There was an inbox message for me
that I needed to read I must evaluate it with help from the noticeboard and linux
commands provided. 

**Output or seal:**
```~~~ WAX SEAL of the Guild: EE2D2911 ~~~
```
**What it means:** 
Some of the information is not yet accessible to me, but I am now able to list my 
rooms (directories) and explore them by listing their contents with ls.
I can ask what provided files are with file to ensure I am meant to open them, and
read/examine them with cat. wc -1 will be important to help me find the meaning of 
this punch card.
## Milestone 3
**What I did:**
I explored different write sections of the manual with different write functions,
as well as the cron section.
**Output or seal:**
```~~~ WAX SEAL of the Guild: 22664701 ~~~
1. write - send a message to another user
2. write - write to a file descriptor
Cron. crontab - maintain crontab files for individual users (Vixie Cron)
```
**What it means:**
Write one has to do with messaging other users who are also logged in by copying
lines in one users' terminal and pasting to the other. Write two deals with
writing to a file descriptor and counting up the bytes within that file as there may
be a size limit on the file. The crontab helps manage installing and deinstalling files

> Fewer or more milestones this week? Copy a block above as needed.

## Reflection

1. **(Prompt 1 from the work order):**
The OS connects the software of the coded commands to the hardware where the memory 
is stored. It does this safely by having a kernel only approve requests that will not
hurt the hardware. This is shown with ls as the software command of ls is given a list from
memory stored in hardware through the OS and the kernel will not permit a command from the
shell that hurts the hardware.
2. **(Prompt 2 from the work order):**
Having a sanctioned manuals is sensible as it allows users to know how the system works
and which commands to use for certain tasks (that will not hurt the hardware). I used
the manual to learn more about certain commands such as the distinction between write 1
and write 2. This saved me time as I didn't have to search an external source to find
what these commands do. It was as easy as typing in the man command from the same location
I do the rest of my coding in.
## Sources and help

Anyone or anything that helped you this week — a classmate, a man page,
a Stack Overflow answer, an AI assistant. One line each: who or what,
and what you used it for. This is **not graded and never costs points**;
it is the habit professional engineers keep, and the syllabus asks for
it under *Academic integrity* and *Use of AI tools*.

None

- *(example)* Worked through the `fork` ordering with Sam in studio.
- *(example)* Used an AI assistant to explain what `EAGAIN` means in the trace.

*Nothing to report? Write "None" — that's a perfectly normal week.*

## Time spent 

Roughly how long this took, start to finish: ___2____ hours
*No wrong answer — this just helps calibrate future work orders.*
