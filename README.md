# SOC-Workflow-Automation-Elastic-SIEM-Jira
End--to-end SOC pipeline integrating Elastic SIEM with Jira for automated threat detection, incident management, and host isolation.

## 📌 Project Overview
This project demonstrates the implementation of a professional-grade Security Operations Center (SOC) workflow. By integrating **Elastic SIEM** with **Jira**, I built a functional pipeline that bridges the gap between real-time threat detection and structured incident response.

The lab replicates a real-world environment where security analysts move from **Detection** to **Escalation** and finally to **Remediation (Containment)**.

---

## 🏗️ System Architecture
* **SIEM:** Elastic Cloud (Detection & Analysis)
* **Ticketing/IM:** Jira Software (Incident Management & Accountability)
* **Endpoint Protection:** Elastic Defend (EDR) installed on Windows Target
* **Attack Source:** Powershell (Simulate Brute-Force attempts & unauthorised file discovery)
---

## 🔍 Detection Rule Logic & Tuning
To ensure high-fidelity alerts and minimize alert fatigue, I engineered custom KQL rules focused on common attack vectors. The technical logic and configuration proofs are documented below:
* 📄 [**Brute-Force Detection Logic**](./Detection_rules/brute_force_logic.txt) — *KQL logic for identifying rapid authentication failures.*
* 📄 [**File Search Discovery Logic**](./Detection_rules/file_search_logic.txt) — *Detects unauthorised reconnaissance patterns.*
* 🖼️ [**Rule Configuration Screenshots**](./Detection_rules/) — *Visual evidence of index patterns and alert suppression tuning.*

---

## 🚀 Key Workflow Phases

### 1. Threat Detection
I monitored the environment for suspicious activity. The rules were tuned to trigger on significant deviations from baseline activity.
> [**Evidence: Alert overview**](./Screenshots/Alert_overview.png)

### 2. Automated Incident Escalation
Validated true positives were escalated from Elastic to **Jira** via a custom connector. This ensured that every confirmed incident was tracked as a formal ticket with an assigned owner, maintaining clear audit trail for the response lifecycle.
> [**Evidence: Jira ticket**](./Screenshots/Jira_ticket.png)

### 3. Response & Containment
Leveraging **Elastic Defend**, I executed remote response actions to neutralize threats. By performing a **Host Isolation**, I effectively severed the attacker's connection and prevented lateral movement.
> [**Evidence: Host isolation**](./Screenshots/Host_isolation_success.png)

---

## ​💡Lessons Learned
* **Alert Tuning:** Learned the importance of suppression and specific KQL filtering to minimise "alert fatigue" and prioritise high-fidelity detections.
* **Incident Lifecycle:** Gained hands-on experience managing an incident from initial detection to containment, ensuring every stage was documented via ticket tracking for accountability.
*  **Integrations:** Developed a practical understanfing of how SIEM (Elastic) and IM (Jira) tools work together to bridge the gap between technical and business workflows.
