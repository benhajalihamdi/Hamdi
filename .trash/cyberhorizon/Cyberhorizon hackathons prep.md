---
tags:
aliases:
date/time: "2026-03-11 13:12"
---
# [[Hackathons|HACKATHON]] PREPARATION

* Learn to explain technical ideas clearly.
* Practice documenting findings.
* Learn to communicate discoveries quickly.
* Practice dividing tasks among teammates.
* Prepare a short explanation style for pitching ideas.
## MENTAL STRATEGY

* Accept that many challenges will seem impossible at first.
* If stuck for 15–20 minutes, change approach.
* Ask teammates for input.
* Use hints and research instead of brute forcing blindly.

## EXTRA (VERY USEFUL)

* Learn basic Git usage with Git.
* Learn how APIs work.
* Learn how JSON data is structured.
* Practice reading logs.
* Learn how to quickly set up a testing environment.


*******************************************************************************

## [[Reconnaissance and enumeration]]

* Perform a **full enumeration workflow** on a target machine (ports → services → versions → vulnerabilities).
* Run advanced scans with [[Nmap]] (`-A`, `-sC`, `-sV`, `--script vuln`) and interpret every result.
* Practice identifying **outdated services** and searching for related CVEs.
* Enumerate **subdomains** of a practice domain using multiple tools and compare results.
* Enumerate API endpoints by analyzing JavaScript files.
* Identify the **tech stack** of a website (framework, server, libraries).

## Web exploitation depth

### Using [[burpsuite|Burp Suite]]:

* Perform **[[parameter fuzzing]]*** to find hidden parameters.
* Manipulate JWT tokens and analyze their structure.
* Identify **[[IDOR (Insecure Direct Object Reference)]]** vulnerabilities.
* Test **rate-limit bypass techniques**.
* Automate repeated requests using Burp Intruder.
* Analyze [[**GraphQL endpoints**]] if present.
* Identify server-side vs client-side validation.

### [[Authentication]] and [[session analysis]]

* Inspect how [[session cookies are]] generated and maintained.
* Attempt [[session fixation]] or token reuse scenarios.
* Analyze password reset flows for weaknesses.
* Test whether session tokens expire correctly.

### [[Network analysis]] depth

* Analyze a complex `.pcap` file in Wireshark and reconstruct:

  * HTTP conversations
  * transferred files
  * DNS queries timeline
* Detect suspicious beaconing or periodic traffic.
* Extract objects from packet captures.
* Identify credentials transmitted in unusual formats.

## Binary and [[reverse engineering basics]]

* Open a binary in Ghidra and locate the main function.
* Identify hardcoded strings or credentials in the binary.
* Trace the logic of a simple password check.
* Patch a binary to bypass a validation condition.

## [[Privilege escalation]] practice

* Enumerate Linux privilege escalation vectors using scripts such as LinPEAS.
* Manually verify findings from automated enumeration.
* Identify writable services or cron jobs.
* Exploit misconfigured SUID binaries.

## [[Advanced scripting with Python]]

* Write a **custom HTTP fuzzer**.
* Automate login attempts with request throttling.
* Write a script to parse large log files and extract anomalies.
* Build a script that interacts with an API and enumerates endpoints.
* Write a small tool that automatically detects encoding types.

## Cryptography challenge practice

* Identify encryption vs hashing vs encoding in unknown data.
* Break simple **reused-key XOR encryption**.
* Write a script that performs frequency analysis on ciphertext.
* Recover plaintext from improperly implemented crypto schemes.

##  [[Forensics]] and [[artifact discovery]]

* Analyze disk images using Autopsy.
* Recover deleted files from an image.
* Extract browser history artifacts.
* Analyze suspicious PowerShell or shell scripts.

## Others
### Speed and methodology training

* Solve [[CTF challenges]] **with a strict 30–45 minute limit**.
* Practice building a [[structured workflow]]: recon → exploit → escalate → document.
* After solving a challenge, reproduce the solution without looking at notes.
* Write short post-mortems explaining the vulnerability and exploit chain.

### Competitive preparation

* Study past write-ups from major CTFs and replicate the techniques.
* Reproduce at least **3 full attack chains** (initial foothold → privilege escalation).
* Build a [[personal toolkit]]: scripts, wordlists, recon commands.
* Create a [[structured note system]] for vulnerabilities and techniques.


