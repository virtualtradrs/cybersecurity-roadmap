# Your first four weeks

A concrete starting plan for Stages 1–3 of the roadmap for someone who has not opened a terminal or a
packet capture before. It assumes **about one hour a day, five days a week** — roughly 20 hours — and it
is a *starting* plan, not a syllabus: it exists so that week one is not spent deciding what to do.

Nothing here is a shortcut past the roadmap. When the four weeks are over you should still be in Stage 1
or heading into Stage 2, with notes you can point at.

**Before you start:** use a virtual machine for anything hands-on. A free hypervisor plus a Linux VM
(and a Windows VM if you have a licence) means mistakes cost you a snapshot, not a laptop. Never practise
on a work machine, a school network or someone else's system.

---

## Week 1 — Get the ground under you

**Goal:** you can describe what happens between typing a URL and seeing a page, and you can move around a
Linux shell without copying commands you do not understand.

| Day | Do this |
|---|---|
| 1 | Install a hypervisor and one Linux VM. Snapshot it before you change anything. Note the VM's IP, gateway and DNS settings. |
| 2 | Read the HTTP overview in Stage 1 of the [README](../README.md#stage-1--networking-and-os-fundamentals). In the VM, use `curl -v` against two sites and write down the request line, three response headers and the status code. |
| 3 | Trace DNS: `dig` (or `nslookup`) a domain, then dig its nameserver, then its `TXT` record. Write down what each answer means in your own words. |
| 4 | Shell basics in the VM: `ls`, `cd`, `man`, `grep`, `find`, `chmod`. Create a user, a directory and a file, then lock and unlock permission on it. |
| 5 | Write week 1 up: one page in Markdown, including the commands, the output and one thing that confused you. |

**Checkpoint:** explain out loud what a status code is, what a DNS `A` record is, and what `chmod 600`
does. If you cannot, redo the day you are least sure about.

## Week 2 — See the traffic

**Goal:** packets stop being abstract. You can capture, filter and read a simple exchange.

| Day | Do this |
|---|---|
| 1 | Install a packet analyser (Wireshark is in Stage 4 of the README) and capture your own `curl` request from week 1. Find the TCP handshake and the DNS lookup. |
| 2 | Practise display filters until you can isolate one host and one port. Filter for DNS and note how many queries a single page load triggers. |
| 3 | Capture on the command line with `tcpdump` in the VM, save to a file, and open that file in the analyser. This is how you work on a server with no desktop. |
| 4 | Read your capture in the analyser, following one TCP stream from start to close. Write a five-line summary of the exchange: who, what, how much data, encrypted or not. |
| 5 | Write up week 2 with a screenshot of the filtered capture and the summary. |

**Checkpoint:** from an unfamiliar capture, you can say which hosts talked, on which ports, and whether
anything looked unusual — with the filter you used shown as evidence.

## Week 3 — Learn to read a host

**Goal:** when something happens on a machine, you know where to look.

| Day | Do this |
|---|---|
| 1 | Linux processes and services: list running processes, find which process owns a listening port, and show that service's definition and logs. |
| 2 | Linux logging: locate the system, authentication and service logs. Find one failed login attempt and one successful one, and quote both lines. |
| 3 | Windows (if you have a VM): list autoruns and services, then look at one process's parent and command line. If you have no Windows VM, read the Sysinternals overview and write down which tool answers which question. |
| 4 | Windows event logs (same caveat): find one logon event and one service-start event; note the event ID and the fields you would alert on. |
| 5 | Write up week 3 as "where I would look for evidence of X on Linux and on Windows" — five rows, one per question you would ask. |

**Checkpoint:** given a suspicious process name, you can find it on the host, find what started it, and
say where it would appear in the logs.

## Week 4 — Start scripting and writing

**Goal:** you have automated one boring thing and published one piece of work. Both matter more later
than they feel like they do now.

| Day | Do this |
|---|---|
| 1 | Python basics (Stage 3 of the README): variables, lists, dicts, loops, functions, files. Type the examples; do not paste them. |
| 2 | Read a text log line by line in Python, split it, and count the most common source address. Get it working with a file of 20 lines before a file of 20,000. |
| 3 | Add error handling and logging to that script, then run it on a real log from your VM. Commit both versions to a Git repository. |
| 4 | Rewrite one manual step of your week as a bash script, and run a shell linter over it until it is clean. |
| 5 | Publish: turn your four weekly writeups into four Markdown pages in a public repository (GitHub Pages is linked in Stage 8 of the README). Fix the typos. Then write down what you will do in month two and pick your next stage. |

**Checkpoint:** two scripts in version control, four published writeups, and a chosen next stage. Keep
the writeups short and accurate; "I did not understand X, here is what I tried" is a legitimate and
useful thing to publish.

---

## What good practice looks like from here

- **One thing at a time.** A lab you finished and wrote up teaches more than five you started.
- **Keep an evidence habit.** Commands, raw output, then interpretation — in that order, in every writeup.
- **Break your lab on purpose.** Delete a config, mis-configure a permission, watch what the logs say.
- **Stay inside your lab.** Everything above is your own VM, on a host-only network. If you want to test
  something that is not yours, get written permission first, in writing, with a scope — that is the whole
  rule this repository is built around.
