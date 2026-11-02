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

**Name:** Caleb
**Week:** Toye
**Work Order No.:** 1851-11

## Milestone 1
**What I did:** Inode: 37567

**Output or seal:**
```~~~ WAX SEAL of the Guild: ECCC5D52 ~~~
```
**What it means:**
ln creates a new directory entry that points to the same inode as the original.
ln -s creates a new file with its own unique inode number.
rm deletes the directory entry.
The pointer broke because it was pointing to a path that no longer existed, but it was
fixed when the file path was recreated.
Physical disk space is not freed by rm alone. The link count must equal zero and
no running process can have an open file descriptor.
## Milestone 2
**What I did:** Type: ext2 
Block Size: 1024
21 shared inode
Links: 2   

**Output or seal:**
```~~~ WAX SEAL of the Guild: 8CFE54A2 ~~~
```
**What it means:**
I went the archivists route. A loop device allows you to mount disk images directly. A
read-only mount prohibits writing that can modify the file (and thus prevent unwanted
deletions).
2 drwxr-xr-x 6 ubuntu ubuntu  1024 Oct 24 10:00 from ls -lai
2   40755 (2)   1000   1000    1024 24-Oct-2026 10:00 from debugfs -R "ls -l /"
## Milestone 3
**What I did:**
 Type|Weekday|Date|Time|Page
-rw-r--r-- 1 ubuntu ubuntu 632 Wed 2026-09-16 19:22:05 table-ix-1848-q1.txt
-rw-r--r-- 2 ubuntu ubuntu 631 Fri 2026-09-18 19:07:40 table-ix-1848-q2.txt
-rw-r--r-- 1 ubuntu ubuntu 636 Wed 2026-09-23 19:36:12 table-ix-1848-q3.txt
-rw-r--r-- 1 ubuntu ubuntu 635 Wed 2026-10-14 19:41:27 table-ix-1848-q4.txt
The clocks agree across l, lu, lc, but differ based on the page.
HOUSE RULE. The ledger halls and the reading room close at the
  bell, six o'clock (18:00). Visiting days are Wednesdays and Fridays.

  A cabinet under audit is read, and never written.

Cabinet folders:
total 16
-rw-r--r-- 1 ubuntu ubuntu   764 Sat 2026-10-24 10:00:00 README-cabinet.txt
drwxr-xr-x 3 ubuntu ubuntu  1024 Sat 2026-10-24 10:00:00 correspondence
lrwxrwxrwx 1 ubuntu ubuntu    28 Sat 2026-10-24 10:00:00 current-quarter -> ledgers/table-ix-1848-q4.txt
drwxr-xr-x 3 ubuntu ubuntu  1024 Sat 2026-10-24 10:00:00 index
drwxr-xr-x 2 ubuntu ubuntu  1024 Sat 2026-10-24 10:00:00 ledgers
They all hold the same time, day, and date, but are different than the pages.
drwx------ 2 root   root   12288 Sat 2026-10-24 10:00:00 lost+found

**Output or seal:**
```~~~ WAX SEAL of the Guild: F7A8DA13 ~~~
```
**What it means:** 1848 is only the pages words. It could not have been a printed inode
because any timed number before 1970 is negative, and inodes are positive.

## Milestone 4
**What I did:** <15>,<16>,<17>: 40, 48, 912

<23> (28) 1848-q1-table-ix.txt
<24> (28) 1848-q2-table-ix.txt   
<25> (28) 1848-q3-table-ix.txt
<26> (28) 1848-q4-table-ix.txt
7 deleted inodes found.
Time deleted
    23   1000 100644    632      1/     1 Wed Sep 16 19:22:05 2026
    24   1000 100644    631      1/     1 Fri Sep 18 19:07:40 2026
    25   1000 100644    636      1/     1 Wed Sep 23 19:36:12 2026
    26   1000 100644    635      1/     1 Wed Oct 14 19:41:27 2026
    15   1000 100644   1242      2/     2 Fri Dec 13 14:45:52 1901
    16   1000 100644    882      1/     1 Fri Dec 13 14:45:52 1901
    17   1000 100644    852      1/     1 Fri Dec 13 14:45:52 1901
    
debugfs 1.47.0 (5-Feb-2023)
1,2c1,2
< To the Honourable the Board of the Waterworks
< 14 March 1848
---
> WATERWORKS -- TABLE IX -- MARCH QUARTER, 1848
> Brassbridge Waterworks, ledger of the quarter
4c4,5
< Gentlemen,
---
>   reservoir head, feet ............ 39.86
>   mains draw, million gallons ..... 7.940
6,7c7,16
< I beg leave to lay before the Board a small matter of method in the
< Engine's working of Table IX, which I fear will not stay small.
**Output or seal:**
```~~~ WAX SEAL of the Guild: 7D1C68B7 ~~~
```
**What it means:**

> Fewer or more milestones this week? Copy a block above as needed.

## Reflection

1. **(Prompt 1 from the work order):** rm doesn't erase the data blocks, it only deletes
the directory entry of the file's name and decreases the link count inside the file's inode
(how the file is found). The block storage is only freed when the link count drops to zero (no one
is reading the file) and that storage can be overwritten by new data.
2. **(Prompt 2 from the work order):** Saving or creating a new file would be a careless action
that would overwrite all of the recovered data. Overwritten data is gone forever, and you
would have no hope to retrieving it.

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

Roughly how long this took, start to finish: ___2.5____ hours
*No wrong answer — this just helps calibrate future work orders.*
