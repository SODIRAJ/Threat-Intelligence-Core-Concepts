# Cyber Threat Intelligence (CTI) Core Concepts

A quick reference guide documenting the core pillars, classifications, frameworks, and intrusion lifecycles utilized within modern Threat Intelligence operations.

---

## 🎯 The Three Pillars of Threat Intelligence

Understanding how different layers of intelligence serve different administrative and operational functions:

*   **Strategic Intelligence:** High-level overviews of the shifting threat landscape, adversary motivations, and geopolitical trends. It is tailored for executives and CISOs to make long-term business, budget, and policy decisions.
*   **Operational Intelligence:** Focuses on the "who, how, and why" of incoming campaigns. It provides context about specific threat actor groups, upcoming attack pretexts, and localized targeting to help SOC managers prepare defenses.
*   **Tactical Intelligence:** Involves the immediate, technical mechanics, behaviors, and methodologies used by an adversary during an active intrusion (TTPs). It allows frontline SOC analysts and threat hunters to recognize active attacks in progress.

---

## 🛡️ The MITRE ATT&CK Framework

The MITRE ATT&CK (Adversarial Tactics, Techniques, and Common Knowledge) framework is a globally accessible, living database of real-world adversary behaviors. It categorizes threat actions into structural matrices to help defenders track and mitigate risk.

### Core Components
*   **Tactics (The "Why"):** The adversary's tactical goal or objective during an attack phase (e.g., *Initial Access, Persistence, Defense Evasion, Exfiltration*).
*   **Techniques (The "How"):** The specific action or method the adversary uses to achieve their tactical goal (e.g., *Phishing, Account Manipulation, Process Injection*).
*   **Sub-techniques (The "What"):** A more granular breakdown describing the exact technical mechanism used to execute a technique (e.g., *Phishing: Malicious Links vs. Phishing: Spearphishing Attachment*).
*   **Procedures (The "Who"):** The specific, documented instance of an adversary group using a technique or tool in a real campaign.

---

## ⛓️ The Cyber Kill Chain

Developed by Lockheed Martin, this framework breaks down a cyberattack into seven distinct, sequential phases. Disrupting the adversary at *any* stage breaks the chain and stops the attack:

1.  **Reconnaissance:** Harvesting email addresses, identifying target technologies, and scouting corporate infrastructure.
2.  **Weaponization:** Pairing a malicious payload (like a macro or remote access tool) with an exploit or pretext to create a deliverable package.
3.  **Delivery:** Transmitting the weaponized payload to the victim (e.g., via a phishing email, a malicious link, or an infected USB drive).
4.  **Exploitation:** Triggering the malicious code, which takes advantage of a system vulnerability or user action to gain a foothold.
5.  **Installation:** Establishing persistence on the victim's asset by installing web shells, registry keys, or remote access trojans (RATs).
6.  **Command & Control (C2):** Opening a two-way communication channel between the infected host and the attacker's server to manage the intrusion.
7.  **Actions on Objectives:** Executing the ultimate goal of the campaign, such as data exfiltration, credential theft, or ransomware deployment.

---

## 🚦 Information Sharing & Sensitivity (Traffic Light Protocol)

The Traffic Light Protocol (TLP) ensures that threat intelligence is shared securely with the right audiences without leaking sensitive data:

*   🔴 **TLP:RED (Strictly Confidential):** Restricted exclusively to named participants in a specific meeting or project. Cannot be shared further.
*   🟡 **TLP:AMBER (Limited Distribution):** Restricted to the organization and its direct clients/constituents who need the data to protect themselves.
*   🟢 **TLP:GREEN (Community Wide):** Shared across the broader cybersecurity community, trusted sectors, or ISACs, but not public web pages.
*   ⚪ **TLP:CLEAR (Public):** No distribution restrictions. Safe for open web blogs, public repositories, and social platforms.

---

## 🔺 The Pyramid of Pain

A foundational concept illustrating how difficult it is for an adversary to change their attack markers when defenders implement blocks, ranked from easiest to hardest to disrupt:

1.  **Hash Values (Trivial):** File signatures can be changed instantly by an attacker altering a single bit of code.
2.  **IP Addresses (Easy):** Attackers can easily switch proxy servers, VPNs, or spinning infrastructure.
3.  **Domain Names (Simple):** Registering new malicious domains is fast and inexpensive.
4.  **Network/Host Artifacts (Annoying):** Distinguishing malicious traffic from benign activity requires modifying command and control software configurations.
5.  **Tools (Challenging):** Forcing an attacker to rewrite or switch their primary malware toolkit requires significant time and resource investment.
6.  **TTPs (Tough):** Overhauling their fundamental behavior, tactics, techniques, and procedures forces the adversary to completely relearn their operational methodology *(Mapped directly via MITRE ATT&CK)*.
