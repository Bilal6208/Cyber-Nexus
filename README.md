# Cyber-Nexus
An AI chat bot answering queries related to cyber related issues.

Introduction:
Students learning cybersecurity must memorise a large number of terms — protocols, Linux commands and attack types — and usually have to search several websites to find short, reliable explanations. This project provides a simple offline tool where a user can type a question in plain English and instantly receive a definition and an example from a fixed, curated dataset. The project is written in C so that it reinforces the fundamentals taught in this course: variables, conditionals, loops, arrays of strings, functions split across multiple source files, pointers, and reading data from a file. A web front end was added so the same program can be demonstrated through a graphical interface.

Test Cases:
Case 1: How to start conversation to load data into memory?
Expected output: using "Hey", "Hi", "Hello"
Case 2: Normal
What is DNS?
Expected output: DNS definition and example displayed 
Case 3: Wrong input
What is xyzeb?
Expected output: “Sorry, xyzabc I am unable to answer this question…” 
Case 1: How to end conversation?
Expected output: using "Bye"

CyberNexus User Guide

1. Getting started
Run cybernexus.exe (console) or Run_GUI.bat (browser GUI, needs Node.js).
Greet it first by typing hi, hello or hey. Nothing else works until you do, because this is what loads the dataset.
When you see You:, type your question and press Enter.
To leave, type exit, quit or bye.

2. What you can ask
Category	Example terms
Networking	DNS, DHCP, IP Address, MAC Address, Subnet Mask, Router, Switch, Firewall, NAT, TCP, UDP, HTTP/HTTPS, VPN, VLAN, OSI Model, Latency, Bandwidth
Linux Commands	ls, cd, pwd, mkdir, grep, chmod, chown, sudo, ps, top, kill, df, curl, wget, systemctl
Cyber Threats	Phishing, Ransomware, Spyware, Trojan Horse, Rootkit, Keylogger, Botnet, SQL Injection, XSS, CSRF, DDoS, Man-in-the-Middle Attack, ARP Spoofing, Brute Force Attack, Zero-Day Exploit, Social Engineering

3. How to ask
Single term: write a natural question or just the term.
what is dns
explain what is router
what does mkdir do
phishing

Comparison (two terms): put two terms in one question.
compare tcp and udp
tcp vs udp
The output shows [01] and [02], each with a definition and an example.

4. What the output looks like
[CyberNexus]: Router
  Definition : ...
  Example    : ...

5. Things to keep in mind
Unknown terms (e.g. xyzabc) give an "unable to answer" message. Only terms in the dataset work. Maximum of two terms per question. If you mention more, only the first two matched ones are used.
Spelling matters. There is no fuzzy matching, so fierwall won't work. Keep it under 256 characters.Avoid exit words inside a question. If your text contains exit, quit or bye anywhere, the bot ends the session. Short keywords can match inside longer words. For example id, ls and ip can trigger false matches, which the report lists as a known limitation. Keywords are picked in the order of the program's keyword list, not the order you type them. For a comparison, mention just the two terms you want.

6. Quick example session
hi
You: what is dns
You: compare tcp and udp
You: what does grep do
You: bye
