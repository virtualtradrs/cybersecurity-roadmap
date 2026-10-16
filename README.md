# Cybersecurity Roadmap — a curated path into security roles

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Links: hand-checked](https://img.shields.io/badge/links-hand--checked-brightgreen.svg)](#link-health)

A curated, step-by-step cybersecurity roadmap: **what to learn in order, and the best free or low-cost
resource for each step**, built for people entering security work — SOC analyst, security engineer,
blue team and adjacent roles. Eight stages, each with a "done when" test you can actually pass or fail,
and every link checked with `curl` before it was published.

**What this is:** a learning path and a resource collection. It is defensive-first by design — the
offensive material appears only as *authorized practice* (CTF platforms, deliberately vulnerable
applications, wargames, or a lab you built yourself), because that is how working defenders learn what
attacks look like from the inside.

**What this is not:** a certification dump, and not a toolkit. There is no exploit code, no payloads,
no target lists and no evasion recipes here. Certifications appear in Stage 8 with their real cost and
prerequisites stated, because a certificate is evidence you studied, not a substitute for the labs.

---

## Contents

- [How to use this roadmap](#how-to-use-this-roadmap)
- [Roadmap at a glance](#roadmap-at-a-glance)
- [Stage 1 — Networking and OS fundamentals](#stage-1--networking-and-os-fundamentals)
- [Stage 2 — Security fundamentals](#stage-2--security-fundamentals)
- [Stage 3 — Programming and scripting for security](#stage-3--programming-and-scripting-for-security)
- [Stage 4 — Network security and monitoring](#stage-4--network-security-and-monitoring)
- [Stage 5 — Defensive security and blue team work](#stage-5--defensive-security-and-blue-team-work)
- [Stage 6 — Cloud and application security](#stage-6--cloud-and-application-security)
- [Stage 7 — Offensive basics for defenders](#stage-7--offensive-basics-for-defenders)
- [Stage 8 — Roles, careers and certifications](#stage-8--roles-careers-and-certifications)
- [Companion pages](#companion-pages)
- [Link health](#link-health)
- [Contributing](#contributing)

## How to use this roadmap

Work the stages in order; each one assumes the one before it. None of them is a course you must
"finish" — the point of Stages 1–3 is that they stop you from running commands and reading logs you do
not understand.

- **Time is rough, not a promise.** The estimates below are typical *part-time* figures for someone
  studying 6–10 hours a week with a keyboard in front of them. Full-time study compresses them; a
  busy job stretches them. Nobody can tell you a date, and anyone who does is selling something.
- **Labs beat videos.** Watching a walkthrough feels like progress and is not. Budget at least half of
  every stage for hands-on work in a lab you control.
- **Write everything down.** Notes in Markdown with the commands, the raw output and your reasoning.
  That habit becomes your incident reports in Stage 5 and your portfolio in Stage 8.
- **Two gates.** Every stage ends with a **Done when** test. If you cannot do it from memory with the
  docs open, the stage is not finished — go back two links.
- **Blue team is the through-line.** Stages 4–6 are where real entry roles live, and they reward
  patience with logs far more than they reward cleverness.

### Companion pages

- [Your first four weeks](docs/YOUR-FIRST-FOUR-WEEKS.md) — a day-by-day starting plan for Stages 1–3 if
  week one would otherwise be spent deciding what to do.
- [SOC analyst: what the job actually is](docs/SOC-ANALYST-PRIMER.md) — the most common entry role,
  described honestly: what a shift contains, what the job is not, and how to practise before you have it.

## Roadmap at a glance

| # | Stage | Focus | Typical part-time time |
|---|-------|-------|------------------------|
| 1 | [Networking and OS fundamentals](#stage-1--networking-and-os-fundamentals) | IP, DNS, HTTP, TCP/IP, Linux and Windows from a security angle | 6–10 weeks |
| 2 | [Security fundamentals](#stage-2--security-fundamentals) | CIA triad, risk, threat modelling, control frameworks, common attacks | 4–6 weeks |
| 3 | [Programming and scripting for security](#stage-3--programming-and-scripting-for-security) | Python, bash, working with logs and APIs, reading unfamiliar code | 8–12 weeks |
| 4 | [Network security and monitoring](#stage-4--network-security-and-monitoring) | Firewalls, segmentation, packet analysis, IDS/IPS, log collection | 6–10 weeks |
| 5 | [Defensive security and blue team work](#stage-5--defensive-security-and-blue-team-work) | SOC workflow, SIEM, detection engineering, incident response | 10–16 weeks |
| 6 | [Cloud and application security](#stage-6--cloud-and-application-security) | OWASP Top 10, cloud provider security, containers and IaC | 8–12 weeks |
| 7 | [Offensive basics for defenders](#stage-7--offensive-basics-for-defenders) | CTFs and authorized labs — red team concepts from the defender's seat | 6–10 weeks |
| 8 | [Roles, careers and certifications](#stage-8--roles-careers-and-certifications) | Which roles exist, what certifications cost, portfolio, community | ongoing |

**Reading the whole path end to end is a multi-year project, not a weekend.** Doing Stages 1–5
properly is a realistic 12–18 month part-time effort before you are competitive for an entry analyst
role. That is a rough planning figure for the sequence above, not a claim about any specific person's
outcome.

---

## Stage 1 — Networking and OS fundamentals

You cannot triage what you cannot describe. This stage is the vocabulary the rest of the roadmap
assumes: how a packet gets from a host to a service, what a name resolves to, and where the evidence
of any of it is recorded on Linux and Windows.

### What you will learn

- The TCP/IP model in practice: addressing, subnets, routing, ports and the TCP handshake.
- What DNS, HTTP/HTTPS and TLS actually do on the wire, and which of their artefacts show up in logs.
- Linux at the command line: processes, permissions, services, logs, package management.
- Windows in a security context: processes, services, autoruns, event logs, PowerShell basics.

### Resources

- <https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview> — the clearest neutral explanation of
  HTTP requests, responses, headers and status codes; almost every web log line you will ever read is
  one of these.
- <https://www.digitalocean.com/community/tutorials/an-introduction-to-dns-terminology-components-and-concepts> — the DNS vocabulary and resolution path in plain
  language, which is what you trace when a domain is newly registered or a look-alike.
- <https://developer.mozilla.org/en-US/docs/Learn_web_development/Howto/Web_mechanics/How_does_the_Internet_work> — what "the
  internet" actually is underneath a page load: a good first read before you meet encapsulation diagrams.
- <https://www.rfc-editor.org/rfc/rfc1918.html> — the private address ranges, straight from the source;
  explains why "internal" traffic is a boundary you have to know.
- <https://www.rfc-editor.org/rfc/rfc1035.html> — the DNS specification. Skim, do not memorise: knowing
  the record types (A, AAAA, MX, TXT, CNAME) makes DNS analysis far easier.
- <https://tldp.org/LDP/intro-linux/html/index.html> — a free, complete introduction to the Linux
  shell, filesystem and permissions, aimed at a beginner rather than at a sysadmin.
- <https://ubuntu.com/server/docs> — official docs for the server distribution you are most likely to
  meet in a lab or a job; the service and networking chapters are the useful ones.
- <https://www.gnu.org/software/bash/manual/bash.html> — the authoritative Bash reference. Keep it
  open in a tab while you work.
- <https://wiki.archlinux.org/title/Main_page> — unusually good technical documentation; the best
  explanation of Linux internals you will find in one place, whatever distribution you run.
- <https://man7.org/linux/man-pages/man5/systemd.service.5.html> — how Linux services are defined and
  started; "which service runs this and as whom" is a daily question in host triage.
- <https://learn.microsoft.com/en-us/sysinternals/> — the Sysinternals suite (Autoruns, Process
  Explorer, TCPView and friends), the standard free toolkit for looking inside a Windows host.
- <https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands> —
  the reference for Windows command-line tools; use it to look up a tool instead of copying a
  one-liner you do not understand.
- <https://pages.cs.wisc.edu/~remzi/OSTEP/> — *Operating Systems: Three Easy Pieces*, a free textbook.
  Not required to finish; invaluable when you want to know why privilege escalation and isolation work
  the way they do.

### Done when

You can, without a tutorial: explain what happens between typing a URL and the page rendering; capture
a TCP handshake in a packet analyser on two machines you own; on Linux, find which process is listening
on a port, show its service definition and where it logs; and on Windows, list autorun entries and
read a process tree.

---

## Stage 2 — Security fundamentals

The vocabulary of risk, and the map of what actually gets attacked. This stage is what turns "I know
Linux" into "I can talk about security work in an interview".

### What you will learn

- Confidentiality, integrity and availability, plus authentication, authorization and accounting — and
  why they are the questions you ask about any system.
- Risk in the technical sense: asset, threat, vulnerability, likelihood, impact, control.
- Threat modelling: trust boundaries, attacker goals, and the cheap questions that find real bugs.
- The common attack classes — phishing, credential abuse, exploitation, web injection, ransomware —
  and the control families that address them.
- The frameworks employers use as shared language: NIST CSF, CIS Controls, MITRE ATT&CK, CVSS.

### Resources

- <https://csrc.nist.gov/glossary> — NIST's glossary of security terms. When two people disagree about
  what "risk" or "control" means, this is the tie-breaker.
- <https://www.nist.gov/cyberframework> — the Cybersecurity Framework (Identify, Protect, Detect,
  Respond, Recover): the structure most organisations map their programme to, and a good outline for
  your own notes.
- <https://www.cisecurity.org/controls> — the CIS Critical Security Controls, i.e. the safeguards
  organisations actually implement first, in priority order. Useful for knowing what "good" looks
  like.
- <https://attack.mitre.org/> — MITRE ATT&CK, the catalogue of adversary tactics and techniques. You
  will use this to name what you detected; skim a handful of techniques rather than all of them.
- <https://attack.mitre.org/resources/getting-started/> — how to read ATT&CK without drowning: start
  from a technique, not from the matrix.
- <https://www.cve.org/> — the CVE Program, the authoritative record of publicly disclosed
  vulnerabilities; learn to read a CVE record and its references.
- <https://www.first.org/cvss/> — the CVSS specification and its scoring logic, so you can read a
  severity score and know what it does and does not tell you.
- <https://csrc.nist.gov/pubs/sp/800/30/r1/final> — NIST SP 800-30, *Guide for Conducting Risk
  Assessments*: the method behind the vocabulary.
- <https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final> — NIST SP 800-53, the control catalogue. Read
  the structure and a couple of control families; do not read it cover to cover.
- <https://owasp.org/www-project-top-ten/> — the OWASP Top 10 web application risks, the shared
  starting point for application security conversations in Stage 6.
- <https://nvd.nist.gov/vuln> — the National Vulnerability Database: the authoritative record of
  scored, published vulnerabilities. Use it to check whether a version you run has an open CVE.
- <https://www.professormesser.com/> — free video courses covering the fundamentals (and the entry
  certification objectives); good for filling a specific gap, not a substitute for lab work.
- <https://www.comptia.org/certifications/security> — **paid certification**. Listed because its
  published objectives are a free, concrete syllabus for "security fundamentals"; the exam itself has a
  fee and requires no work experience.

### Done when

You can define the CIA triad plus AAA in your own words; walk a threat model of a small web app (assets,
trust boundaries, attacker goals, cheapest control); take three recent CVEs from the NVD and explain, for each, which
ATT&CK technique it enables and what would have detected it; and explain the
difference between a vulnerability, an exploit and a risk.

---

## Stage 3 — Programming and scripting for security

Security work is data work: parsing logs, enriching indicators, automating the boring 90%. This stage
is not about becoming a software engineer, it is about being able to read code you did not write and
write a script you can trust.

### What you will learn

- Python syntax, data structures, files, exceptions and virtual environments.
- Regular expressions and structured parsing (JSON, CSV, log lines) — the core of log analysis.
- HTTP from code: calling APIs, handling failures, and never trusting the response.
- Bash for glue: pipelines, exit codes, `set -euo pipefail`, and linting your own scripts.
- Reading unfamiliar code for security-relevant patterns (unsafe input handling, secrets in source).

### Resources

- <https://www.py4e.com/> — *Python for Everybody*, a free full course with exercises; the fastest
  honest route from zero to useful Python.
- <https://automatetheboringstuff.com/> — free-to-read book aimed squarely at the automation skills
  this job needs (files, spreadsheets, web requests).
- <https://docs.python.org/3/howto/regex.html> — the official regex how-to; you will use it the first
  time a log format refuses to cooperate.
- <https://docs.python.org/3/library/logging.html> — the standard logging module, so your scripts leave
  evidence of what they did instead of silently half-failing.
- <https://requests.readthedocs.io/en/latest/> — the de facto Python HTTP client; needed for every API
  enrichment or threat-intel lookup you script.
- <https://tldp.org/LDP/abs/html/> — the Advanced Bash-Scripting Guide: opinionated and long, but the
  loops, conditionals and exit-code material is solid.
- <https://www.shellcheck.net/> — paste a shell script in and get its bugs back. Run it on everything
  before you put a script in front of anyone else.
- <https://git-scm.com/book/en/v2> — *Pro Git*, free: version control for your scripts, notes and
  writeups, which Stage 8 depends on.
- <https://google.github.io/styleguide/pyguide.html> — a readable Python style guide; adopt it early so
  your code reads like something a reviewer can trust.
- <https://semgrep.dev/docs/> — how static analysis rules are written and what they catch; the practical
  version of "read other people's code for security bugs".

### Done when

You can write, unaided, a Python script that parses a log file (or a JSON export), extracts the top
source addresses or events, deduplicates, writes CSV output, and logs its own errors; a bash script with
`set -euo pipefail` that passes ShellCheck; and, given a small unfamiliar code sample, point out two
security-relevant problems in it and say why they matter.

---

## Stage 4 — Network security and monitoring

The network is where a defender gets the most durable evidence, because an attacker has to talk to the
target to succeed. Here you learn to place sensors, read packets without a GUI, and turn raw traffic
into something you can alert on.

### What you will learn

- Packet-level analysis: reading a capture, following a TCP stream, spotting unusual DNS or TLS
  behaviour.
- Firewalls and segmentation: default-deny, zones, rule hygiene, and why perimeter-only thinking fails.
- Host and network hardening from a published baseline, plus least privilege.
- IDS/IPS concepts and NSM (network security monitoring) logging: what Zeek and Suricata produce, and
  what each is good for.
- Centralised log collection: getting logs off the box and into something searchable.

### Resources

- <https://www.wireshark.org/docs/wsug_html_chunked/> — the Wireshark User's Guide; the packet
  analyser is free and this is its manual, including the capture and filter chapters you will live in.
- <https://www.tcpdump.org/manpages/tcpdump.1.html> — `tcpdump`'s manual page: capture on a headless
  server where no GUI will ever exist.
- <https://www.securityonion.net/> — Security Onion, a free platform that bundles the Zeek and Suricata
  sensors with Elasticsearch and its own console; the quickest way to stand up a whole NSM stack in a
  lab, and its documentation shows what each sensor's logs look like in practice.
- <https://docs.suricata.io/en/latest/> — Suricata's documentation: signatures (including the
  open Emerging Threats ruleset), protocol parsing and file extraction.
- <https://docs.netgate.com/pfsense/en/latest/> — the pfSense documentation for building a real
  firewall/router in a lab or small network; useful for segmentation exercises.
- <https://docs.opnsense.org/> — OPNsense documentation, the same exercise with a different platform;
  reading two vendors' docs teaches you what is generic to firewalls.
- <https://www.cisecurity.org/benchmarks> — the CIS Benchmarks: free hardening baselines for operating
  systems, applications and cloud platforms. Start with a Linux benchmark on your own VM.
- <https://man7.org/linux/man-pages/man7/capabilities.7.html> — Linux capabilities, the kernel-level
  version of least privilege; explains why "just run it as root" is a design failure.
- <https://www.elastic.co/guide/en/beats/filebeat/current/index.html> — Filebeat, one of the most common
  log shippers; the concepts (inputs, modules, pipelines) transfer to any collection tool.
- <https://docs.graylog.org/> — Graylog's documentation for a self-hosted log platform, including
  search syntax and streams: a practical lesson in making logs answerable.
- <https://nmap.org/book/> — the Nmap book. Read it to understand what a scan looks like *on the wire*,
  which is how you recognise one in your own logs.

> **Authorized testing only.** Everything hands-on in this stage — scanning, firewalls, captures —
> belongs in a lab you own or on systems you have written permission to test. Port-scanning networks you
> do not control is not practice; in many countries it is an offence.

### Done when

You can build a small lab (a firewall plus two hosts), capture traffic between them, and explain what
you see; from one capture, identify one benign and one suspicious flow and justify both calls; write
three working Zeek or Suricata detections and explain what each would miss; and produce a
default-deny firewall ruleset you can read line by line.

---

## Stage 5 — Defensive security and blue team work

This is the stage that maps most directly onto an entry-level SOC job: an alert queue, a set of
dashboards, a runbook, and a shift that ends with a written record of what you decided and why. Most of
the time you will be wrong about something; the discipline is in documenting it clearly enough that the
next analyst can fix it.

### What you will learn

- SOC workflow: alert triage, escalation criteria, runbooks, shift handover, and metrics that are not
  vanity metrics.
- SIEM fundamentals: ingesting logs, normalising fields, writing searches and correlation rules.
- Detection engineering: turning attacker behaviour into a rule that fires on it, and testing the rule.
- Endpoint telemetry in practice: what Sysmon gives you on Windows, and what auditd gives you on Linux.
- Incident response fundamentals: preparation, identification, containment, eradication, recovery,
  lessons learned — and why the last step is the one teams skip.

### Resources

- <https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf> — NIST SP 800-61, the
  incident handling guide. Dated in places, still the shared reference for the response lifecycle.
- <https://www.first.org/standards/frameworks/csirts/> — FIRST's CSIRT services framework: what a
  response team is expected to provide, which is useful vocabulary when you describe your own work.
- <https://thedfirreport.com/> — real intrusion write-ups with the telemetry shown. The single best
  free source for "what an incident actually looks like in the logs".
- <https://www.elastic.co/guide/en/security/current/index.html> — Elastic Security docs: SIEM detection
  rules, timelines and case management in an open-source stack you can run locally.
- <https://docs.splunk.com/Documentation/Splunk> — Splunk's documentation; Splunk is the tool whose
  syntax appears in a large share of job adverts, and the free tier is enough to learn the search
  language.
- <https://sigmahq.io/> — Sigma: the vendor-neutral format for detection rules. Writing one rule in
  Sigma teaches you what a SIEM rule actually is.
- <https://github.com/SigmaHQ/sigma> — the Sigma rule repository; read a few rules for a technique you
  understand and follow the field mappings.
- <https://research.splunk.com/> — public, peer-reviewed detection content with the reasoning shown,
  including per-technique analytics you can adapt.
- <https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon> — Sysmon: the Windows endpoint
  telemetry that makes process-level detection possible.
- <https://github.com/olafhartong/sysmon-modular> — a modular Sysmon configuration, useful because a
  badly configured Sysmon either floods you or sees nothing.
- <https://learn.microsoft.com/en-us/azure/sentinel/overview> — Microsoft Sentinel, a cloud SIEM;
  useful as a worked example of connecting sources, analytics rules and incidents.
- <https://blueteamlabs.online/> — hands-on blue team challenges (phishing analysis, log analysis, memory
  forensics). Free tier with a paid option; the free challenges are enough to start.
- <https://www.cyberdefenders.org/> — blue team CTF-style challenges built from real artefacts; the free
  challenges arrive with a question set and a time limit.
- <https://letsdefend.io/> — a SOC-analyst practice platform with simulated alerts and a free tier; the
  closest thing to a shift in an alert queue you can get without a job.
- <https://isc.sans.edu/> — the SANS Internet Storm Center: free daily handler diaries about live
  attacks. Reading one a day builds pattern recognition faster than any course.

### Done when

You can take a set of alerts, triage them in writing (true/false positive, evidence, decision,
escalation) and produce an incident report with a timeline, indicators, containment steps and a
detection rule for the technique involved; and you can explain what your rule will *not* catch, which is
the part that separates a detection engineer from a rule copier.

---

## Stage 6 — Cloud and application security

Most new systems are web applications running on someone else's computers, configured by code. This
stage is where a defender learns the two boundaries that generate the most incidents: the application
and the cloud account.

### What you will learn

- The OWASP Top 10 as risk categories, with the fix for each — not just the name.
- Secure application requirements (ASVS), and how to check a dependency set for known vulnerabilities.
- The security model of a major cloud provider: identity and access management, network controls,
  logging, and the shared responsibility line.
- Containers and orchestration from a security angle: images, runtime isolation, and the workload
  controls that actually matter.
- Infrastructure as code and scanning it before it is deployed, plus supply-chain basics.

### Resources

- <https://owasp.org/www-project-top-ten/> — the OWASP Top 10 categories: the shared vocabulary, and the
  starting point for a threat model of any web app.
- <https://cheatsheetseries.owasp.org/> — OWASP Cheat Sheet Series: short, practical, defensive guidance
  per topic (authentication, logging, secrets, file upload). The most-used page in this repository for
  people who have to write a recommendation.
- <https://owasp.org/www-project-application-security-verification-standard/> — ASVS: verifiable
  application security requirements by level. Use it to turn "make it secure" into a checklist.
- <https://owasp.org/www-project-dependency-check/> — Dependency-Check: find known-vulnerable
  dependencies, which is where a large share of real application findings come from.
- <https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html> — the AWS Security
  Pillar: how one large provider expects identity, detection, infrastructure protection, data protection
  and incident response to fit together.
- <https://learn.microsoft.com/en-us/azure/security/fundamentals/overview> — Azure security
  fundamentals, including the shared responsibility model explained provider-side.
- <https://cloud.google.com/docs/security> — Google Cloud's security documentation: IAM, encryption and
  logging concepts, useful as a third implementation of the same ideas.
- <https://kubernetes.io/docs/concepts/security/> — Kubernetes security concepts: pod security, network
  policies, secrets and admission control.
- <https://docs.docker.com/engine/security/> — Docker's own security documentation: the container threat
  model, image trust and daemon configuration.
- <https://github.com/aquasecurity/trivy> — Trivy: scan container images, filesystems, IaC and SBOMs in
  one tool; the fastest way to *see* a misconfiguration rather than read about one.
- <https://www.checkov.io/> — Checkov: static analysis for Terraform, CloudFormation, Kubernetes and
  more, with a policy catalogue worth reading on its own.
- <https://developer.hashicorp.com/terraform/intro> — Terraform's introduction, so you can read the
  infrastructure code you will be asked to review without treating it as magic.
- <https://slsa.dev/> — the SLSA supply-chain framework: levels, provenance and build integrity, the
  vocabulary now used for "can we trust this artefact".
- <https://owasp.org/www-project-juice-shop/> — OWASP Juice Shop, an intentionally vulnerable web
  application you run yourself. Use it to see how the Top 10 categories look from the attacker's side.
- <https://portswigger.net/web-security> — PortSwigger's free Web Security Academy: the best free
  structured web-exploitation labs, each paired with the underlying explanation. The crawl-and-exploit
  labs are what turn a category name into a memory.

> **Authorized testing only.** Juice Shop, PortSwigger's labs and every other practice target here are
> built to be attacked, and they are the *only* web targets this roadmap points you at. Testing a site
> you do not own or have written permission to test is a crime in most jurisdictions, whatever the
> intent.

### Done when

You can review a small Terraform or Docker Compose project and list its misconfigurations with reasons;
run an image or IaC scan and explain each finding; for five OWASP Top 10 categories, describe a realistic
exploit and a defensive fix; and state which ASVS level a given application would plausibly meet and why.

---

## Stage 7 — Offensive basics for defenders

Defenders who have never taken a system apart miss obvious things. This stage exists so you can recognise
attacker behaviour in telemetry — not so you can break into anything. Every resource here is a lab that
is designed to be attacked, or code you run against your own machines.

### What you will learn

- How a vulnerable service is enumerated and exploited, so the logs an exploit leaves mean something.
- Recognising attacker behaviour in telemetry: what MITRE ATT&CK techniques look like at the host and
  network level.
- Testing your own detections: deliberately emulating a technique in your lab and checking whether your
  rules fire.
- Writing findings up honestly, including what you did not find and where your method was weak.

### Resources

- <https://tryhackme.com/> — guided, browser-based rooms with learning paths; free rooms plus optional
  paid subscriptions, and the blue team paths overlap Stages 4–5 well.
- <https://picoctf.org/> — free beginner CTF competition and practice archive; excellent first taste of
  structured problem-solving.
- <https://blueteamlabs.online/> — listed again in this stage on purpose: the challenges here are the
  defender's half of the same skills, and they pair well with an offensive lab.
- <https://pwn.college/> — free educational wargames with lectures; the systems-exploitation modules
  teach memory and privilege concepts that make exploit reports readable.
- <https://www.root-me.org/> — free-tier challenges across web, system and crypto with a scoring board;
  the challenges are self-contained and legal.
- <https://www.hackthebox.com/> — labs and machines, free tier with paid options; treat the machines as
  practice artefacts to write up, not as a score to chase.
- <https://portswigger.net/web-security/all-labs> — the full lab list from the Academy in Stage 6; work
  these before any general-purpose CTF if your interest is application security.
- <https://owasp.org/www-project-vulnerable-web-applications-directory/> — a directory of deliberately
  vulnerable applications you can run locally, with the language and purpose listed for each.
- <https://www.vulnhub.com/> — downloadable vulnerable virtual machines for offline practice; build them
  on a host-only network with no route to the internet.
- <https://atomicredteam.io/> — Atomic Red Team: small, documented tests for specific ATT&CK techniques.
  The point is to run one against your own lab and see whether your detection fires.
- <https://github.com/mitre/caldera> — MITRE Caldera: automated adversary emulation for a lab you own,
  useful for generating controlled telemetry at volume.
- <https://owasp.org/www-project-juice-shop/> — Juice Shop again: the most forgiving target to learn
  against when you want to try a technique for the first time.
- <https://nmap.org/book/man.html> — the `nmap` manual page, so you understand exactly what each scan
  type sends. Read it before you point it at anything.

> **Authorized testing only — the rule for this stage and this repository.** Point every tool here at a
> target that is designed to be attacked, at a lab you built, or at a system you own / have explicit
> written permission to test. Curiosity, good intentions or "white hat" framing are not permission.
> This repository contains no exploit code, no payloads, no credential dumps, no evasion techniques and
> no target lists, and contributions that add any of them are declined.

### Done when

You can complete three labs from different platforms and write one page each — objective, what you did,
evidence, what the defender would see, and which ATT&CK technique it maps to; and you have emulated one
technique in your own lab and shown whether your Stage 5 detection rule fired, including the case where
it did not.

---

## Stage 8 — Roles, careers and certifications

There is no certificate that hires you and no shortcut that replaces lab work you can show. What works
is unglamorous: learn the fundamentals, build things you can demonstrate, write them up, and apply
steadily to roles that match where you actually are.

### The roles, honestly

| Entry route | What the day is mostly | Typical first step |
|---|---|---|
| SOC analyst / security operations | Alert triage, investigation, escalation, documentation, shift work in many organisations | Stages 1–5, a couple of platform accounts, one entry certification is common but not universal |
| IT / systems / helpdesk with security duties | Patching, identity and access, endpoint tooling, incident tickets | Often the realistic first job; it builds the operational instincts SOC teams want |
| Security engineering / automation | Building and tuning tooling, log pipelines, hardening as code | Needs Stage 3 plus Stage 4 or 6 depth |
| GRC / security analyst (policy, risk) | Questionnaires, control evidence, policy work, audit support | Good fit if you prefer writing and process to terminals; Stage 2 matters most |

Job titles overlap and change between employers; read the posting, not the title. The
[NICE Workforce Framework](https://www.nist.gov/itl/applied-cybersecurity/nice) is the reference for
what tasks actually belong to which work role, and
[CyberSeek](https://www.cyberseek.org/) publishes free labour-market data on role and skill demand.

### Getting a first role without experience

- **Show work, not intentions.** Three to five written-up labs or investigations, each with evidence and
  reasoning, beat a certificate listing. Host them free with
  [GitHub Pages](https://pages.github.com/) and write them in Markdown — the
  [GitHub Markdown documentation](https://docs.github.com/en/get-started/writing-on-github) covers
  everything you need, including code blocks for command output.
- **Do the boring adjacent job.** Helpdesk, IT support, NOC and junior sysadmin roles are the most common
  on-ramp; ask for the security-adjacent tickets and document them.
- **Be accurate about what you have done.** "I built a lab and detected X" is a stronger interview answer
  than a vocabulary list, and it survives follow-up questions.
- **Apply more than feels reasonable.** Rejections are normal and usually say nothing about you; entry
  hiring is slow and often automated. No one can promise you a job, a timeline or a salary — anyone who
  does is selling something.
- **Use the free community.** <https://isc.sans.edu/> for daily threat notes,
  <https://www.bleepingcomputer.com/> and <https://krebsonsecurity.com/> for industry reporting,
  <https://www.first.org/> for the incident-response community, and the platforms in Stage 5 for
  practical groups and challenges.

### Certifications, with the costs stated

Certifications are worth having when they are (a) required by a filter you keep hitting, or (b) genuinely
structured study material for a stage you are on. None of them replaces the labs above. Prices are set by
the vendors and change; check the official page before budgeting.

| Certification | Level | Cost reality |
|---|---|---|
| [CompTIA Security+](https://www.comptia.org/certifications/security) | Entry | **Paid exam voucher**; no work experience required; generous published objectives make it a free syllabus |
| [ISC2 Certified in Cybersecurity (CC)](https://www.isc2.org/certifications/cc) | Entry | **Paid exam**; entry-level by design; ISC2 has periodically offered free self-paced training — check the current page |
| [AWS Certified Cloud Practitioner](https://aws.amazon.com/certification/certified-cloud-practitioner/) | Entry (cloud) | **Paid exam**; foundation-level |
| [Microsoft SC-900](https://learn.microsoft.com/en-us/credentials/certifications/security-compliance-and-identity-fundamentals/) | Entry (cloud) | **Paid exam**; the free Learn modules are usable on their own |
| [Linux Foundation training](https://training.linuxfoundation.org/) | Entry–intermediate | **Paid exams**; some courses and many resources are free — start with the free material |
| [GIAC (SANS)](https://www.giac.org/certifications/) | Intermediate–advanced | **Paid, expensive**, usually employer-funded; the associated SANS material is the real value |
| [OSCP (OffSec)](https://www.offsec.com/courses/pen-200/) | Advanced practitioner | **Paid course and exam**; hands-on, lab-based, and aimed at offensive roles — only worth it after Stage 7 |

If you cannot pay, that does not stop you: the free resources in Stages 1–7 cover more ground than any
single certification, and a documented portfolio is what a hiring manager can actually evaluate.

### Done when

You have a public page with at least three written-up labs, a one-page CV that states what you built and
where, a shortlist of ten real postings you match or nearly match, and a note of which certification (if
any) is blocking you — with the vendor's current price written next to it. Then you start applying.

---

## Link health

Every external link in this repository was checked with `curl` (following redirects, with a browser
user-agent) before publishing, on **2026-10-16**. Links that returned a hard failure were removed or
replaced rather than shipped, and a few sources that answer automated checks with a bot challenge were
replaced by an equivalent page that answers `200`, rather than shipped unverified. One host
(`docs.zeek.org`) answers repeated automated requests with `429 Too Many Requests`; its material is
covered by the Security Onion entry in Stage 4, which links the same tooling. There are no affiliate, referral or tracking links, no link shorteners,
and nothing here is paywalled-only without that being said in its own entry. Popularity, salary and
outcome numbers are not claimed anywhere — where a figure appears, it is a rough part-time *planning*
estimate and labelled as such.

Re-check everything at any time:

```bash
grep -ohE 'https://[^)"< ]+' README.md docs/*.md | sort -u |
  xargs -P 12 -I{} sh -c 'c=$(curl -sIL -o /dev/null -w "%{http_code}" --max-time 25 \
  -A "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/124 Safari/537.36" \
  "{}"); echo "$c {}"' | sort
```

### Documented exception

`portswigger.net` answers `HEAD` requests with `404` for pages under `/web-security/*` while `GET`
returns `200`. The PortSwigger entries above were therefore confirmed with a `GET` request. This is a
server behaviour, not a dead link; if you re-run the check, verify those URLs with `curl -sL` (no `-I`)
before reporting them broken.

## Contributing

Corrections, better free resources and new verified links are welcome — and fixing a dead link is the
most valuable contribution of all. Read [CONTRIBUTING.md](CONTRIBUTING.md) first: it sets out the
link-check requirement, the no-affiliate rule, the structure rules and the ethics rule (defensive-first;
any offensive material only in the context of authorized testing).

## License

Licensed under the [MIT License](LICENSE). Copyright (c) 2026 Virtual Traders.
