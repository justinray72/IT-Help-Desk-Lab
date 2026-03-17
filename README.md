# IT Help Desk Lab Using osTicket

A hands-on help desk simulation built by deploying osTicket on Ubuntu Server in VirtualBox. Configured a full ticketing environment from scratch, created realistic IT support scenarios, and worked each ticket through a complete lifecycle: intake, triage, documentation, and resolution.

---

## Tools & Environment

| Item | Details |
|---|---|
| Ticketing System | osTicket v1.18.3 |
| OS | Ubuntu 24.04 (VirtualBox VM) |
| Web Server | Apache2 |
| Database | MySQL |
| Language | PHP 8.x |
| Host Machine | Windows 11 |

---

## Objective

Simulate a real IT help desk environment to demonstrate ticket management, triage prioritization, and incident documentation skills. Each ticket scenario reflects common real-world IT support requests handled at the help desk and SOC level.

---

## Environment Setup

- Deployed Ubuntu 24.04 in VirtualBox on Windows 11
- Installed and configured a full LAMP stack (Linux, Apache, MySQL, PHP)
- Created a MySQL database and user for osTicket
- Installed and configured osTicket v1.18.3 via web installer
- Created custom help topics including **Security Incident** and **Account Access / Password Reset**
- Created an end user (Sarah Johnson) to simulate employee ticket submissions

---

## Ticket Scenarios

### Ticket #893295 — Unable to Login to My Account
**Category:** Account Access / Password Reset | **Priority:** High

**User Report:**
> Locked out of Windows account since this morning. Receives error stating account is locked. Needs access restored urgently due to scheduled meetings.

**Triage Notes:**
Account lockout confirmed. Checked Active Directory for failed login attempts and lockout source. No signs of malicious activity detected. Proceeded with account unlock and password reset.

**Resolution:**
Unlocked account and issued temporary password with forced reset on next login. User notified with instructions to change password immediately.

---

### Ticket #264314 — Suspicious Login Alert on My Account
**Category:** Security Incident | **Priority:** Emergency

**User Report:**
> Received an alert of an unauthorized login from an unfamiliar location at 2:00 AM. Did not authorize this access. Concerned credentials may be compromised.

**Triage Notes:**
Potential account compromise. Immediately disabled account to prevent further unauthorized access. Cross-referenced login timestamps and source IP against network traffic logs in Splunk. No additional suspicious accounts flagged. Monitoring for lateral movement.

**Resolution:**
Account temporarily disabled pending investigation. User notified of security incident status and instructed not to attempt login until cleared.

---

### Ticket #311022 — Laptop Running Slow, Possible Malware
**Category:** Report a Problem | **Priority:** High

**User Report:**
> Laptop extremely slow for two days. Random pop-ups appearing and browser redirecting to unknown websites. Believes something malicious may have been downloaded accidentally.

**Triage Notes:**
Symptoms consistent with malware infection — slow performance, pop-ups, and browser redirects. Remotely isolated machine from network to prevent potential spread. Running full scan with Windows Defender. Checking browser extensions and startup programs for suspicious entries. Reimaging flagged as contingency if malware cannot be fully remediated.

**Resolution:**
Machine isolated and scan initiated. User notified not to use device until further notice.

---

### Ticket #361350 — Unable to Connect to the Network
**Category:** Report a Problem | **Priority:** Normal

**User Report:**
> Cannot connect to company network or access internal resources. Wi-Fi shows connected but no internal sites or shared drives are reachable. Issue started approximately one hour ago.

**Triage Notes:**
Device showing connected but unable to reach internal resources. Checked router and switch logs for drops or configuration changes. Ran ipconfig — found APIPA address (169.254.x.x) indicating DHCP failure. Released and renewed IP address. Confirmed DNS resolution working. Internal resources now accessible.

**Resolution:**
DHCP issue resolved remotely. User confirmed able to access network and internal resources.

---

## Screenshots

**Open Ticket Queue — All 4 tickets assigned and prioritized**
<img width="1217" height="732" alt="ticket-lab-ss1" src="https://github.com/user-attachments/assets/6271b79b-fd9e-401e-9878-3433bfb9ef15" />

**Ticket #893295 — Account Lockout Resolution**
<img width="1213" height="766" alt="ticket-lab-ss2" src="https://github.com/user-attachments/assets/acc8de83-e6bb-4c1a-8b78-f2bb723e6261" />

**Ticket #264314 — Security Incident (Emergency Priority)**
<img width="1211" height="768" alt="ticket-lab-ss3" src="https://github.com/user-attachments/assets/5aee95cf-ea73-4fad-a701-0cd0e45d6115" />

**Ticket #311022 — Malware Report**
<img width="1219" height="763" alt="ticket-lab-ss4" src="https://github.com/user-attachments/assets/1ce3d44a-39c8-483f-a4b3-3b1fa1662f3e" />

**Ticket #361350 — Network Connectivity Issue**
<img width="1217" height="756" alt="ticket-lab-ss5" src="https://github.com/user-attachments/assets/c99f2fc2-b4ce-4e3d-a968-2a30a6fa9751" />

**Closed Ticket Queue — All 4 tickets resolved**
<img width="1214" height="753" alt="ticket-lab-ss6" src="https://github.com/user-attachments/assets/b83b6366-9e16-44b2-b802-09450b802a3c" />

---

## Skills Demonstrated

- **Help Desk Ticketing** — Managed full ticket lifecycle from intake to resolution using osTicket
- **Triage & Prioritization** — Assigned appropriate priority levels (Normal → Emergency) based on incident severity
- **Incident Documentation** — Wrote detailed internal notes and user-facing responses for each ticket
- **Security Incident Response** — Identified and escalated a potential account compromise, referenced Splunk for log correlation
- **Network Troubleshooting** — Diagnosed and resolved DHCP failure using ipconfig
- **Malware Response** — Isolated affected machine and initiated remediation process
- **Linux System Administration** — Deployed and configured full LAMP stack on Ubuntu from scratch

---

## Key Takeaways

- Proper ticket documentation is as important as the technical fix — every action needs a paper trail
- Priority assignment directly affects response time — correctly escalating a security incident to Emergency ensures it gets immediate attention
- Help desk and security operations overlap significantly — a suspicious login ticket requires the same investigative mindset as a SOC alert
- Connecting ticketing workflows with SIEM tools like Splunk creates a more complete incident response picture

---

## Related Projects

- [Network Traffic Analysis Using Wireshark](https://github.com/justinray72/Network-Traffic-Analysis-Using-Wireshark)
- [Security Monitoring Dashboard Using Splunk](https://github.com/justinray72/Security-Monitoring-Dashboard-Using-Splunk)
