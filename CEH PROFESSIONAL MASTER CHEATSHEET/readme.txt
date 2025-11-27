
THE PROFESSIONAL & METHODOLOGICAL FOUNDATION

1. PRE-ENGAGEMENT RULES OF ENGAGEMENT
- Scope Definition: Exactly what IPs, domains, and applications are in scope. What is explicitly OFF-limits.
- Authorization Documentation: The signed "Get Out of Jail Free" document. Keep it accessible at all times.
- Rules of Engagement: Agreed-upon testing windows (e.g., after business hours), allowed techniques (e.g., Are DoS attacks permitted?), and points of contact for emergency shutdown.
- Communication Protocols: How and when to report critical findings immediately.

2. THE FORMAL METHODOLOGIES
You need to know these frameworks by name and structure. They are the checklist for a thorough test.
- OWASP Testing Guide: For web applications. It's the bible for web app pentesting.
- OWASP Top 10: The list of the most critical web application security risks. You MUST be able to find and test for all of these.
- MITRE ATT&CK Framework: A knowledge base of adversary tactics and techniques based on real-world observations. This is how you plan and describe your post-exploitation activities.
- NIST Cybersecurity Framework: Especially SP 800-115, the technical guide to information security testing.
- Penetration Testing Execution Standard (PTES): Provides a standard for performing a penetration test.

3. THE "GETTING CAUGHT" KIT & INCIDENT HANDLING
- Emergency Contact Info: Phone numbers and emails for your primary client contact. If an IDS flags you or a system crashes, you need to call them BEFORE they call you.
- "I'm a Friendly" Script: A pre-written, client-approved statement you can provide if security staff confronts you.
- Evidence of Authorization: A digital and physical copy of your signed scope document.

4. THE NOTE-TAKING & EVIDENCE SYSTEM
This is non-negotiable. Your notes are your primary deliverable and your legal protection.
- Structured Note-Taking: Use a tool like Obsidian, KeepNote, or OneNote. Organize by phase (Recon, Scanning, etc.) and by target.
- Command Logging: Use `script` command to automatically log all your terminal activity. Example: `script -a pentest-session.log`
- Screenshot Everything: Not just proof of exploitation, but also of tools, configurations, and errors. Timestamp everything.
- File Naming Convention: `[Date]_[Target]_[Service]_[Finding].png` e.g., `20231025_WebApp_Login_SQLi_Proof.png`
- Password Database: A secure, encrypted database (like KeePass) to store all credentials found or created during the test.

5. THE REPORTING TEMPLATE
Start with the end in mind. Know what you need to document for your final report.
- Executive Summary: For non-technical management. Explain the risk in business terms, not technical jargon.
- Technical Findings: A detailed, repeatable breakdown for each vulnerability.
  - Vulnerability Title
  - CVSS Score: Standardized severity rating (Critical, High, Medium, Low).
  - Affected Host/URL
  - Description: What is the issue?
  - Proof of Concept: Step-by-step how to reproduce it. Include commands and screenshots.
  - Impact: What could an attacker achieve? (e.g., "This allows for full system compromise.")
  - Remediation: Specific, actionable advice on how to fix it.
- Raw Data Appendices: Full nmap scans, tool outputs, etc.

6. THE ETHICAL & LEGAL MINDSET
- Data Handling: What will you do with the sensitive data you exfiltrate? It must be securely destroyed after the engagement.
- Proportionality: Don't use a sledgehammer if a tap will do. If you have admin access, you don't need to run a destructive exploit.
- "First, Do No Harm": Your goal is to find flaws, not to disrupt business. Avoid techniques that might crash production systems unless explicitly authorized.

7. THE LAB & PRACTICE ENVIRONMENT
- Home Lab: A dedicated, isolated network where you can practice safely. Use VMware or VirtualBox.
- Practice Platforms: Active subscriptions to Hack The Box, TryHackMe, or VulnHub machines. These are your training grounds.
- Tool Familiarity: You don't need to know every tool, but you need deep knowledge of the core ones (nmap, Burp Suite, Metasploit, etc.).

8. THE "SECONDARY" SKILLSETS
- Networking Deep Dive: TCP/IP, subnetting, routing, firewall rules. You can't attack what you don't understand.
- Basic System Administration: For both Windows and Linux. You need to know how they work normally to spot misconfigurations.
- Scripting: Python or Bash to automate repetitive tasks, create custom exploits, or parse tool output.

CRITICAL COMMANDS & TECHNIQUES YOU MISSED

- **Traffic Relays / Pivoting:**
  - `ssh -D 1080 user@target.com` (Create a SOCKS proxy through the target)
  - Metasploit's `autoroute` and `socks4a` module
  - `proxychains` to route tools through a proxy

- **Privilege Escalation Checklists:**
  - Linux: `linpeas.sh` (The most comprehensive enumerator)
  - Windows: `winpeas.bat` or `PowerUp.ps1`

- **Password Cracking Workflow:**
  - Identify hash type: `hash-identifier`
  - Crack with rules: `hashcat -m 1000 hashes.txt /usr/share/wordlists/rockyou.txt -r /usr/share/hashcat/rules/best64.rule`

- **Web Application Proxy Mastery:**
  - Burp Suite: Target Scope, Repeater, Intruder, and Scanner.
  - Intercepting and modifying mobile app traffic.

In essence, the crucial missing piece is the **professional wrapper** around the technical hacking skills. Anyone can run a tool; a professional knows why, when, and how to run it responsibly, and how to communicate the results in a way that actually improves the client's security.