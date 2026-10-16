# SOC analyst: what the job actually is

This page exists because most descriptions of "getting into cybersecurity" describe a job nobody does.
If you are aiming at a Security Operations Centre (SOC) analyst seat — the most common entry role in the
field — here is what the work looks like on a normal day, what it is *not*, and what to practise so your
first week is not a shock.

It is written from the published shape of the role (SOC workflows, incident-handling guides and public
incident write-ups linked in Stages 4–5 of the [README](../README.md#stage-5--defensive-security-and-blue-team-work)),
not from any one employer's internal process. Every organisation differs in tooling and maturity.

---

## The job in one sentence

You are the person who decides, many times a day, whether a generated alert is nothing or the start of
something — and then either closes it with a written reason or escalates it with enough evidence that
someone else can act.

## What a shift actually contains

- **An alert queue.** Alerts come from endpoint tools, network sensors, cloud platforms, identity
  systems and user reports. Your job is triage: gather context, decide, record the decision.
- **Detective work on boring inputs.** Grepping logs, checking whether a file hash is known, reading
  login patterns, asking who owns an asset, confirming whether a scheduled task was ever scheduled.
- **A lot of writing.** Ticket notes, escalation summaries, handover notes. Writing clearly is the
  single most transferable skill in this role, and the one candidates most often lack.
- **Repeat alerts you have seen before.** Most of your day is patterns, not novelty. Recognising the
  pattern quickly is the craft.
- **Escalation and handover.** When it is real: contain what you can within your authority, escalate with
  the evidence attached, and keep a timeline as you go — reconstructing one later is painful.
- **Sometimes, quiet.** Depending on the organisation, shifts vary between flood and nothing. Both have
  a failure mode: alert fatigue in one, missed detections in the other.

## What it is not

- **It is not penetration testing.** Different role, different day, occasional overlap in knowledge only.
- **It is not "watch the dashboards".** Dashboards prompt work; they do not do it.
- **It is not a hacking montage.** Nobody types with two hands on one keyboard. The excitement is
  rare and the logs are voluminous.
- **It is not firewall administration**, though in small teams you may inherit some of it.
- **It is not shift-free everywhere.** Many SOCs run 24×7, which can mean nights, weekends and public
  holidays. Ask about the rota in the interview, and mean it.

## The skills that actually transfer into the seat

1. **Reading logs confidently.** Every tool differs; the discipline of "what produced this line, what
   are the fields, what is normal for this system" does not.
2. **Host and network fundamentals.** You will be asked what a process is, what a port is, and whether a
   login was remote. Stages 1 and 3 of the roadmap, not memorised facts.
3. **Python or shell at a scripting level.** Not software engineering — enough to pull a field out of a
   log or call an API and finish the ticket faster than doing it by hand.
4. **A repeatable triage method.** For example: what fired → which asset → which user → what else
   happened around that time → known-good or not → decision and evidence.
5. **Writing.** Two paragraphs that a busy engineer can act on. This is where a portfolio of writeups
   pays off, because it is directly the job.

## How to practise before you have the job

The platforms linked in Stages 5 and 7 of the roadmap provide simulated alert queues, phishing analysis,
log and memory challenges. Use them the way the job works, not the way a course works:

- **Time yourself and decide.** Investigate for 20 minutes, then write the ticket: true or false
  positive, evidence, action, confidence.
- **Write what you would need to be sure.** "I could not confirm X because I do not have Y" is a
  professional answer and shows you know the limits of the evidence you have.
- **Turn one challenge into one detection.** If a technique appears in a challenge, write the rule that
  would have caught it, and note its blind spots.
- **Keep a triage log.** Your own running list of case → pattern → decision. After twenty cases, read it
  and you will see your own repeating mistakes; fixing those is the actual training.

## Questions worth asking in an interview

- What is the escalation path, and who owns the follow-up when something is confirmed?
- How are detections maintained, and who writes new rules when a threat report lands?
- What is the shift rotation, and how is handover done?
- What does success look like at 3, 6 and 12 months for this seat?
- How much of the queue is automated triage today?

Their answers tell you whether the SOC is a place where you will learn. That matters more than the job
title, and it is not something anyone can promise you from the outside.
