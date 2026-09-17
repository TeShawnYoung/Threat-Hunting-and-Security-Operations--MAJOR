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
- 📄 [Scenario Creation](https://github.com/TeShawnYoung/threat-hunting-scenario-tor-/blob/main/threat-hunting-scenario-tor-event-creation.md)

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
