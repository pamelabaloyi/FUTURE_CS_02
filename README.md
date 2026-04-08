# FUTURE_CS_02
# 🛡️ Phishing Detection & Awareness System

Task:Future Interns Cyber Security Task 2 (2026)  
Role: Security Analyst / SOC Analyst  
Date: March 7, 2026  
Author: Mikateko baloyi


 📌 Project Overview

This project simulates the work of a real security analyst investigating real-world phishing emails and creating an employee awareness program. The deliverable is a professional phishing detection report that organizations can use for security training.

Why this matters: 90% of successful cyber attacks begin with a phishing email. Technical filters alone cannot stop all attacks. A trained, vigilant workforce is the last and most important line of defense.


 What I Accomplished

- ✅ Analyzed 4 real phishing email samples (including one from a legitimate government domain)
- ✅ Identified common phishing indicators (urgency, generic greetings, undisclosed recipients, authentication failures)
- ✅ Classified email risk using a standardized risk matrix (Safe / Suspicious / Phishing / Malicious)
- ✅ Created prevention guidelines for employees (Do's & Don'ts)
- ✅ Documented all findings in a client-ready report
- ✅ Built a printable office poster and LinkedIn carousel for awareness campaigns

 Email Samples Analyzed

| # | Sender Domain | Subject | Authentication | Risk Classification |
|---|---------------|---------|----------------|---------------------|
| 1 | micros0ft-support[.]net | "Urgent: Your Account Will Be Locked" | SPF: Fail | 🔴 Phishing |
| 2 | stayfriends.de | "Kochen ohne Chemie" | SPF: permerror, DKIM: none, DMARC: none | 🔴 Phishing (Spoofing) |
| 3 | **saps.gov.za** (legitimate domain) | "Quote Needed – PLURAL URINAL Order" | SPF: Pass, DKIM: Pass, DMARC: Pass, ARC: Fail | 🟠 Phishing (Compromised Account) |
| 4 | fake-hr[.]com | "Salary Update – Action Required" | SPF: Fail | 🟡 Suspicious |


Deep Dive: Sample #3 (SAPS Government Domain)

This email is the most interesting case in the analysis. It **passed SPF, DKIM, and DMARC** because it originated from a legitimate South African Police Service server. However, behavioral red flags revealed the attack:

| Red Flag | Why It Matters |
|----------|-----------------|
| 🔴 Undisclosed recipients (BCC only) | Legitimate business emails show recipients |
| 🔴 ARC failure | Email was forwarded or modified after delivery |
| 🔴 Unusual procurement request | "PLURAL URINAL Order" is not standard SAPS language |
| 🔴 Sender name format | "FS:Rouxville SCM" inconsistent with SAPS conventions |

**Critical Lesson:** Authentication does NOT equal trust. Attackers compromise real accounts to bypass technical filters.


🔬 Deep Dive: Sample #2 (StayFriends.de)

This email represents the opposite end of the spectrum  **obvious technical failures**:

| Failure | Implication |
|---------|--------------|
| ❌ SPF: permerror | Sending IP not authorized for stayfriends.de |
| ❌ DKIM: none | No cryptographic signature |
| ❌ DMARC: none | No policy defined |
| ⏱️ 12-minute delivery delay | Routing through suspicious servers |

Critical Lesson: Some phishing is easy to detect with technical controls — but not all.

 🛠️ Tools Used

| Tool | Purpose |
|------|---------|
| Google Messageheader Tool | Email header analysis (SPF, DKIM, DMARC, ARC) |
| MxToolbox Email Header Analyzer | Header validation and authentication checks |
| Manual Behavioral Analysis | Identifying urgency, generic greetings, undisclosed recipients |
| GitHub | Portfolio hosting and version control |


📊 Risk Classification Matrix

| Risk Level | Definition | Action Required |
|------------|------------|-----------------|
| 🟢 Safe | Known sender, expected content | Read normally |
| 🟡 Suspicious | Generic greeting, minor errors, unexpected | Hover links, verify via phone |
| 🟠 Phishing | Urgent tone, fake domain, requests credentials | Delete immediately, report to IT |
| 🔴 Malicious | Contains .exe, .scr, .js attachments | Do NOT open. Permanently delete |

