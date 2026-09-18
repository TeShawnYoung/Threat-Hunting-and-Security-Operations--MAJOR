# Threat Hunting & Security Operations

## Project Overview

This repository showcases **proactive threat hunting** work conducted using endpoint detection and response (EDR) telemetry and Kusto Query Language (KQL) to investigate suspected policy violations and potential security incidents.

Each scenario includes the hunting hypothesis, the KQL queries used to search for indicators of compromise, a chronological event timeline reconstructed from the evidence, and a documented response.

---

## Core Threat Hunting Scenarios

### 1. 🕵️ Threat Hunt Report: Unauthorized TOR Usage <a href="https://github.com/TeShawnYoung/threat-hunting-scenario-tor-/tree/main"><img src="https://img.shields.io/badge/--555555?style=flat&logo=github&logoColor=white" height="20"/></a>

**Focus:** Investigating suspected use of the Tor Browser to bypass network security controls, based on unusual encrypted traffic patterns and connections to known Tor entry nodes.

**Platforms and Languages Leveraged:**

- Windows 10 Virtual Machines (Microsoft Azure)
- EDR Platform: Microsoft Defender for Endpoint
- Kusto Query Language (KQL)
- Tor Browser

**Key Capabilities:**

- File event analysis to detect Tor installer downloads and related artifacts
- Process event analysis to identify silent installation and browser execution
- Network event analysis to confirm connections to the local Tor SOCKS proxy and known Tor ports
- Chronological timeline reconstruction from cross-table EDR evidence
- Incident response coordination, including endpoint isolation and manager notification

**Resources:**

- 📄 [Threat Hunt Report](https://github.com/TeShawnYoung/threat-hunting-scenario-tor-/blob/main/README.md)
- 🔎 [KQL Queries & Steps Taken](https://github.com/TeShawnYoung/threat-hunting-scenario-tor-/blob/main/README.md#steps-taken)
- 🗓️ [Chronological Event Timeline](https://github.com/TeShawnYoung/threat-hunting-scenario-tor-/blob/main/README.md#chronological-event-timeline)
- 🛠️ [Response Taken](https://github.com/TeShawnYoung/threat-hunting-scenario-tor-/blob/main/README.md#response-taken)
- 📄 [Scenario Creation](https://github.com/TeShawnYoung/threat-hunting-scenario-tor-/blob/main/threat-hunting-scenario-tor-event-creation.md)

---

### 2. 📤 Threat Hunt Report: Suspected Data Exfiltration from PIP'd Employee <a href="https://github.com/TeShawnYoung/Suspected-Data-Exfiltration-from-PIPd-Employee"><img src="https://img.shields.io/badge/--555555?style=flat&logo=github&logoColor=white" height="20"/></a>

**Focus:** Investigating a disgruntled employee's device, following a performance improvement plan (PIP), for signs of data staging and potential exfiltration of proprietary information.

**Key Capabilities:**

- File event analysis to detect archive (`.zip`) creation and movement patterns
- Process event analysis to uncover silent installation and use of archive utilities via PowerShell
- Network event analysis to check for evidence of data leaving the host
- MITRE ATT&CK mapping of staging, execution, and potential exfiltration behavior

**Resources:**

- 📄 [Threat Hunt Report](https://github.com/TeShawnYoung/Suspected-Data-Exfiltration-from-PIPd-Employee/blob/main/README.md)
- 🔎 [KQL Queries & Steps Taken](https://github.com/TeShawnYoung/Suspected-Data-Exfiltration-from-PIPd-Employee/blob/main/README.md#steps-taken)
- 🗓️ [Timeline Summary & Findings](https://github.com/TeShawnYoung/Suspected-Data-Exfiltration-from-PIPd-Employee/blob/main/README.md#timeline-summary-and-findings)
- 🎯 [MITRE ATT&CK Mapping](https://github.com/TeShawnYoung/Suspected-Data-Exfiltration-from-PIPd-Employee/blob/main/README.md#mitre-attck-ttp-alignment)
- 🛠️ [Response Taken](https://github.com/TeShawnYoung/Suspected-Data-Exfiltration-from-PIPd-Employee/blob/main/README.md#response-taken)

---

### 3. 🌐 Threat Hunt Report: Devices Accidentally Exposed to the Internet <a href="https://github.com/TeShawnYoung/Devices-Accidentally-Exposed-to-the-Internet"><img src="https://img.shields.io/badge/--555555?style=flat&logo=github&logoColor=white" height="20"/></a>

**Focus:** Investigating VMs in a shared services cluster that were mistakenly exposed to the public internet, checking for brute-force login attempts and potential account compromise.

**Key Capabilities:**

- Internet-exposure verification using device inventory telemetry
- Logon event analysis to identify brute-force patterns from external IP addresses
- Cross-referencing failed and successful logons to confirm whether any brute-force attempt succeeded
- MITRE ATT&CK mapping of external access and credential access techniques

**Resources:**

- 📄 [Threat Hunt Report](https://github.com/TeShawnYoung/Devices-Accidentally-Exposed-to-the-Internet/blob/main/README.md)
- 🔎 [KQL Queries & Steps Taken](https://github.com/TeShawnYoung/Devices-Accidentally-Exposed-to-the-Internet/blob/main/README.md#steps-taken)
- 🗓️ [Timeline Summary & Findings](https://github.com/TeShawnYoung/Devices-Accidentally-Exposed-to-the-Internet/blob/main/README.md#timeline-summary-and-findings)
- 🎯 [MITRE ATT&CK Mapping](https://github.com/TeShawnYoung/Devices-Accidentally-Exposed-to-the-Internet/blob/main/README.md#mitre-attck-ttp-alignment)
- 🛠️ [Response Taken](https://github.com/TeShawnYoung/Devices-Accidentally-Exposed-to-the-Internet/blob/main/README.md#response-taken)

---

### 4. 🐌 Threat Hunt Report: Sudden Network Slowdowns <a href="https://github.com/TeShawnYoung/Sudden-Network-Slowdowns"><img src="https://img.shields.io/badge/--555555?style=flat&logo=github&logoColor=white" height="20"/></a>

**Focus:** Investigating internal network performance degradation to determine whether an internal host was scanning or otherwise abusing the local network.

**Key Capabilities:**

- Network event analysis to identify hosts generating excessive failed connections
- Chronological connection analysis to detect sequential port-scanning patterns
- Process event analysis to identify the scanning script and its execution context
- MITRE ATT&CK mapping of reconnaissance, discovery, and execution techniques

**Resources:**

- 📄 [Threat Hunt Report](https://github.com/TeShawnYoung/Sudden-Network-Slowdowns/blob/main/README.md)
- 🔎 [KQL Queries & Steps Taken](https://github.com/TeShawnYoung/Sudden-Network-Slowdowns/blob/main/README.md#steps-taken)
- 🗓️ [Timeline Summary & Findings](https://github.com/TeShawnYoung/Sudden-Network-Slowdowns/blob/main/README.md#timeline-summary-and-findings)
- 🎯 [MITRE ATT&CK Mapping](https://github.com/TeShawnYoung/Sudden-Network-Slowdowns/blob/main/README.md#mitre-attck-ttp-alignment)
- 🛠️ [Response Taken](https://github.com/TeShawnYoung/Sudden-Network-Slowdowns/blob/main/README.md#response-taken)

---

## Technical Architecture & Workflow

1. **Hypothesis Development**
   A hunting hypothesis is formed based on reported anomalies, such as unusual encrypted traffic or behavioral reports, to guide the investigation.

2. **IoC Discovery Planning**
   Relevant EDR tables (`DeviceFileEvents`, `DeviceProcessEvents`, `DeviceNetworkEvents`) are identified based on the expected artifacts of the suspected activity.

3. **Query Development & Evidence Collection**
   KQL queries are written and refined to surface file, process, and network artifacts tied to the suspected activity on the target device.

4. **Timeline Reconstruction**
   Evidence from multiple tables is correlated into a chronological sequence of events to establish an accurate narrative of what occurred.

5. **Response & Reporting**
   Findings are summarized, confirmed activity is documented, and appropriate response actions (e.g., endpoint isolation, stakeholder notification) are taken and recorded.

---

## Skills Demonstrated

* **Threat Hunting:** Hypothesis-driven investigation using EDR telemetry
* **KQL:** Query development across file, process, and network event tables
* **EDR Analysis:** Microsoft Defender for Endpoint log interpretation
* **Timeline Reconstruction:** Correlating multi-table evidence into a coherent event sequence
* **Incident Response:** Isolation, notification, and documentation of confirmed findings
* **Security Reporting:** Communicating investigative findings and outcomes clearly
