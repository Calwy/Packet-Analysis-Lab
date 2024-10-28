# Threat Intelligence Lab
Security Onion based server used for analysis malicious activities based on packet captures

## High-Level Diagram
![Untitled Diagram drawio (6)](https://github.com/user-attachments/assets/a3ddaf5a-bf8e-4cfd-890a-c6551c60fd6c)



## Overview
These lab was used to setup and practice commonly used tools to ingest online packet captures and detect, monitor and investigate malicious activity by utilizing Security Onion's comprehensive suite and Wireshark's packet-level inspection capabilites

### 1. **High Level Process:**
- Packet Capture files are taken from external online sources
- These files are then ingested into Security Onion and Wireshark
- They are then analysed by Suricata and Zeek which is then displayed on Security Onion's dashboard using the ELK stack (Elastic Search, Logstash and Kibana)
- Wireshark was used inspect packets on a closer level to map attack timelines

### 2. **Data Ingestion Pipeline**
   - **Source**: Online network captures or live packet streams.
   - **Ingestion Process**: Captures are transferred into the lab environment for analysis.
   - **Data Routing**: Traffic is routed to both **Security Onion** for SIEM-level analysis and **Wireshark** for deep packet inspection (DPI).

### 3. **Core Analysis Tools**
   - **Security Onion**:
     - Functions as the central hub for detection, logging, and investigation.
     - Integrates **Suricata** for signature-based threat detection and **Zeek** for behavior analysis.
     - **Strelka** analyzes extracted files for potential malware indicators.
   - **Wireshark**:
     - Used for detailed packet analysis and inspecting individual packets.
     - Assists in pinpointing specific attack vectors or anomalies within network captures.

### 4. **Analysis Workflow**
   - **Initial Capture Analysis**:
     - Network captures are ingested and processed by Security Onion’s IDS tools (Suricata & Zeek).
     - Wireshark is used for granular inspection to confirm findings or explore traffic anomalies.
   - **Dashboard and Alerting**:
     - Security Onion’s **Kibana dashboard** visualizes data flows, alert timelines, and threat indicators.
     - Alerts are organized by severity, attack type, and impacted hosts for prioritized investigation.

### 5. **Threat Detection and Visualization**
   - **Detection**:
     - Suricata and Zeek generate logs and alerts based on signatures, threat intelligence feeds, and heuristic analysis.
     - Custom scripts or Zeek policies can be added to tailor threat detection to specific patterns or behaviors.
   - **Visualization**:
     - The **Kibana** dashboard displays real-time alerts, IP connections, geolocation, and packet statistics.
     - Analysts can follow timelines to understand the stages of detected attacks and monitor network behavior over time.

## Key Components and Tools

| Component       | Purpose                                              |
| --------------- | ---------------------------------------------------- |
| **Security Onion** | Provides SIEM capabilities, including IDS, IPS, and full packet capture |
| **Suricata**    | Signature-based detection for known threats          |
| **Zeek (Bro)**  | Behavioral analysis, anomaly detection, and logging  |
| **Strelka**     | File analysis framework for detecting malware patterns |
| **Wireshark**   | Packet-by-packet analysis for deep inspection        |
| **Kibana Dashboard** | Real-time monitoring and timeline visualization of attack data |

## Benefits of the Lab Setup
- **Comprehensive Threat Detection**: Combines signature, behavioral, and heuristic analysis for broad coverage.
- **Detailed Investigation**: Security Onion dashboards and Wireshark allow layered analysis from packet to attack timeline.
- **Scalability**: Easily ingest and analyze additional packet captures or live traffic streams.

## Future Enhancements
- **Automation**: Implementing automated alerts and scripts for continuous monitoring.
- **Expanded Threat Feeds**: Integrating additional threat intelligence sources for more comprehensive detection.
- **Machine Learning Integration**: Applying ML models for anomaly detection and improved alerting precision.

## References:
- **Source for packet captures:** https://malware-traffic-analysis.net/
- **Security Onion:** https://securityonionsolutions.com/
- **ELK Stack:** https://www.elastic.co/elastic-stack
---

This structure enables in-depth threat detection and analysis, creating a well-rounded environment for proactive cybersecurity analysis and training.
