# TryHackMe: SOC Fundamentals

| Field | Details |
| :--- | :--- |
| **Platform** | TryHackMe |
| **Room** | SOC Fundamentals |
| **Category** | SOC Level 1 / Defensive Security (Blue Team) |
| **Date Completed** | August 24, 2026 |
| **Status** | ✅ Completed (7/7 Tasks, 128 Pts) |

---

## 📌 Overview
An introductory breakdown of a modern Security Operations Center (SOC), focusing on how organizations structure defense, monitor telemetry, and handle incident workflows.

---

## 🏛️ The Three Pillars of SOC Operations

### 1. People
* **Tier 1 (Triage / Junior SOC Analyst):** Monitors incoming alerts, filters false positives, and performs initial investigations.
* **Tier 2 (Incident Responder):** Conducts in-depth root-cause analysis, threat containment, and remediation.
* **Tier 3 (Threat Hunter / Senior Analyst):** Proactively searches for persistent or evasive threats across the enterprise.
* **Security / Detection Engineer:** Builds and tunes detection rules, manages SIEM infrastructure, and maintains security tooling.
* **SOC Manager:** Manages team operations, reporting, and incident escalations directly to the **CISO (Chief Information Security Officer)**.

### 2. Process
Incident handling and alert analysis follow the **5 Ws**:
* **Who:** Threat actor or targeted user/asset.
* **What:** Nature of the attack or anomalous event.
* **Where:** Impacted hostnames, IP addresses, or network segments.
* **When:** Exact timeline, initial compromise date, and detection timestamps.
* **Why:** The attacker's objective (e.g., data theft, persistence, lateral movement).

### 3. Technology
* **Detection:** Visibility via SIEM, EDR, and IDS/IPS logging anomalous network and endpoint telemetry.
* **Response:** Containment mechanisms including automated or manual firewall blocks, host isolation, and credential revocation.

---

## 💡 Lessons Learned & Blue Team Takeaway
* Solidified how structured triage workflows keep defensive operations organized during high-volume alert scenarios.
* Clarified the operational ladder from Tier 1 analyst up through CISO reporting.
* Reinforced personal motivation to specialize in the **Blue Team / SOC** career lane.