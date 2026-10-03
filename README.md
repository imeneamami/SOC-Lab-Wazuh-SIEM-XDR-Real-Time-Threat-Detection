# SOC-Lab-Wazuh-SIEM-XDR-Real-Time-Threat-Detection

This project showcases the design and implementation of a lightweight, functional Home Security Operations Center (SOC) built from scratch to simulate enterprise-grade monitoring and incident detection.

The lab environment serves as a practical test for security event collection, log analysis, and threat detection. It utilizes Wazuh deployed as an open-source SIEM/XDR solution to monitor a dedicated Ubuntu endpoint acting as the target agent. To validate the detection capabilities, multiple real-world attack scenarios were executed using Kali Linux, allowing for the observation and analysis of alerts in real time via the Wazuh dashboard.

🏗️ Lab Architecture & Setup
Wazuh Server (SIEM/XDR): Centralized management server responsible for log aggregation, threat intelligence, and dashboard visualization.

Wazuh Agent (Ubuntu Endpoint): Installed on a target virtual machine to monitor system activities, file changes, and service logs.

Attacker Machine (Kali Linux): Used to launch simulated cyberattacks against the target endpoint.

🔬 Simulated Attack Scenarios & Detection
To test the efficacy of the SIEM rules and real-time alerting, the following attack vectors were successfully executed and captured:

SSH Brute-Force Attack using Hydra and  multiple consecutive failed login attempts:

Execution: Simulated credential guessing attacks targeting the SSH service on the Ubuntu agent.

Detection: Wazuh successfully detected multiple authentication failures and triggered  alerts for potential brute-force activity.

File Integrity Monitoring (FIM):

Execution: Unauthorized modifications, creations, and deletions were performed on system files of Ubuntu endpoint.

Detection: Wazuh FIM tracked the file changes in real time, capturing exact timestamps, user details, and the specific checksum differences.

SQL Injection (SQLi) with Apache:

Execution: Targeted a web application hosted on the Apache server by injecting malicious SQL payloads from Kali Linux to manipulate backend queries.

Detection: Monitored web server access and error logs to flag anomalous web traffic patterns and suspicious request parameters.

                References : 
Configured and deployed following the official wazuh documentation https://documentation.wazuh.com/current/proof-of-concept-guide/index.html
