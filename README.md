# SOC-Lab-Wazuh-SIEM-XDR-Real-Time-Threat-Detection&Response

This project showcases the design and implementation of a lightweight, functional Home Security Operations Center (SOC) built from scratch to simulate enterprise-grade monitoring and incident detection.

The lab environment serves as a practical test for security event collection, log analysis, and threat detection. It utilizes Wazuh deployed as an open-source SIEM/XDR solution to monitor a dedicated Ubuntu endpoint acting as the target agent. To validate the detection capabilities, multiple real-world attack scenarios were executed using Kali Linux, allowing for the observation and analysis of alerts in real time via the Wazuh dashboard.

🏗️ Lab Architecture & Setup
Wazuh Server (SIEM/XDR): Centralized management server responsible for log aggregation, threat intelligence, and dashboard visualization.

Wazuh Agent (Ubuntu Endpoint): Installed on a target virtual machine to monitor system activities, file changes, and service logs.

Attacker Machine (Kali Linux): Used to launch simulated cyberattacks against the target endpoint.

🔬 Simulated Attack Scenarios & Detection
SSH Brute-Force Attack & Active Response:
Execution: Simulated password-guessing and credential-stuffing attacks targeting the SSH service using Hydra from Kali Linux with multiple consecutive failed login attempts.
Detection: Wazuh successfully detected multiple authentication failures and triggered real-time alerts.
Active Response: Configured automated mitigation inside the Wazuh manager configuration file utilizing Active Response to automatically trigger network-level blocks (`iptables`) against the malicious IP address.

File Integrity Monitoring (FIM):

Execution: Unauthorized modifications, creations, and deletions were performed on system files of Ubuntu endpoint.

Detection: Wazuh FIM tracked the file changes in real time, capturing exact timestamps, user details, and the specific checksum differences.

SQL Injection (SQLi) with Apache:

Execution: Targeted a web application hosted on the Apache server by injecting malicious SQL payloads from Kali Linux to manipulate backend queries.

Detection & Remediation:Wazuh monitored web server access and error logs to flag anomalous web traffic patterns and SQLi intrusion attempts, and successfully triggered an Active Response to automatically mitigate the threat at the network/host level.

                References : 
https://documentation.wazuh.com/current/proof-of-concept-guide/index.html

https://documentation.wazuh.com/current/user-manual/capabilities/active-response/index.html
