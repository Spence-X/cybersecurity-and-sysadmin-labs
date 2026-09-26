# <p align="center">🛡️ Module 1: Introduction to Ethical Hacking and Penetration Testing</p>

<p align="center">
  <img src="https://img.shields.io/badge/Course-Cisco_Networking_Academy-1BA1E2?style=flat-square&logo=cisco&logoColor=white" alt="Cisco">
  <img src="https://img.shields.io/badge/Status-100%25_Complete-2ea44f?style=flat-square" alt="Status">
  <img src="https://img.shields.io/badge/Module-01_Foundations-blueviolet?style=flat-square" alt="Module">
</p>

---

## 🎯 1. Understanding Ethical Hacking & Threat Landscapes

> **Core Concept:** An ethical hacker employs the exact same tools, techniques, and mindsets as malicious actors, but operates under explicit authorization to uncover vulnerabilities and harden infrastructure[cite: 4].

### 🔍 Key Objectives & Definitions
* **Proactive Defense:** Identifying paths of compromise before malicious actors can exploit them, evaluating the real-world strength of defensive security controls[cite: 4].
* **Threat Actor Taxonomy:**
  * 🌐 **Organized Crime:** Financially driven syndicates and cartels.
  * 📢 **Hacktivists:** Ideologically or politically motivated groups.
  * 🏛️ **State-Sponsored Attackers:** Advanced Persistent Threats (APTs) executing espionage or strategic cyber warfare.
  * 👤 **Insider Threats:** Trusted personnel (employees/contractors) with authorized access who misuse privileges maliciously or accidentally.

---

## 🗺️ 2. Penetration Testing Methodologies & Frameworks

> **Why Methodology Matters:** Applying a structured procedure prevents **scope creep** and guarantees repeatable, exhaustive testing[cite: 5].

### 📋 Testing Types & Scopes
| Category | Types & Perspectives | Description |
| :--- | :--- | :--- |
| **Target Infrastructure** | **Network / Apps / Cloud** | Assessing routers, firewalls, web software, and cloud-native IAM permissions[cite: 5]. |
| **Testing Scope** | **Black-Box (Unknown)** | Zero prior knowledge provided; simulates realistic external attacks[cite: 5]. |
| | **White-Box (Known)** | Full disclosure of source code, architecture, and documentation[cite: 5]. |
| | **Grey-Box (Partial)** | Limited credentials or partial visibility (simulating lower-privileged internal users)[cite: 5]. |

### 📚 Industry Standards & Frameworks
* 🛠️ **MITRE ATT&CK:** Knowledge base of real-world adversary tactics and techniques.
* 🌐 **OWASP WSTG:** Standard for web application security vulnerability testing.
* 📘 **NIST SP 800-115:** Technical guide for information security testing and assessment.
* 📖 **OSSTMM:** Open Source Security Testing Methodology Manual.
* 📋 **PTES:** Penetration Testing Execution Standard.
* 📑 **ISSAF:** Information Systems Security Assessment Framework.

---

## 💻 3. Building Your Own Lab Environment

> ⚠️ **The Golden Rule:** Never test tools or techniques directly against live production networks without authorization. Always validate inside a controlled sandbox first[cite: 6].

### 🏗️ Essential Lab Architecture
* 🔒 **Closed Network:** Complete isolation to prevent accidental leakage or outbound malicious traffic[cite: 6].
* ⚙️ **Hardware & Resource Allocation:** Sufficient CPU, RAM, and disk space to handle multiple operating systems simultaneously[cite: 6].
* 📸 **Health Monitoring & Recovery:** Snapshots and backups enabling instant restoration when an exploit crashes a target system[cite: 6].
* 🎯 **Practice Targets & Tools:** Safe intentionally vulnerable machines paired with a categorized suite of utilities (network scanners, web proxies, automated vulnerability tools, and mobile sandbox emulators)[cite: 6].

---
