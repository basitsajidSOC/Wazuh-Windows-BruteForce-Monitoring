# Wazuh SIEM: Windows Brute Force & Logon Monitoring Lab

## 🚀 Project Overview
This project demonstrates setting up a Security Information and Event Management (SIEM) environment using **Wazuh** to monitor Windows security events. The primary objective is to detect unauthorized login attempts (Brute Force attacks) and successful user authentication activities on a virtualized Windows endpoint.

## 🛠️ Lab Architecture & Environment
- **SIEM Manager:** Wazuh Server (deployed on Ubuntu Virtual Machine)[span_3](start_span)[span_3](end_span)
- **Endpoint Agent:** Windows 10 Virtual Machine (`DESKTOP-G8FE4UE`, IP: `192.168.1.43`)[span_4](start_span)[span_4](end_span)[span_5](start_span)[span_5](end_span)
- **Virtualization:** Oracle VirtualBox

## 🔍 Implementation & Testing Steps

### 1. Failed Login / Brute Force Simulation
- Intentionally entered incorrect passwords multiple times on the Windows lock screen to trigger security auditing policies.
- **Windows Event ID Generated:** `4625` (An account failed to log on)[span_6](start_span)[span_6](end_span)
- **Wazuh Rule Triggered:** Rule ID `60122` ("Logon failure - Unknown user or bad password") with a severity level of `5`[span_7](start_span)[span_7](end_span)[span_8](start_span)[span_8](end_span).
- **MITRE ATT&CK Mapping:** `T1078` (Valid Accounts), `T1531` (Account Access Removal)[span_9](start_span)[span_9](end_span).

### 2. Successful Authentication & Logoff Monitoring
- Verified successful logons (`Windows workstation logon success`) and session terminations (`Windows User Logoff`) to ensure complete visibility over endpoint user activity[span_10](start_span)[span_10](end_span).

## 📷 Screenshots
*(Check the `screenshots/` folder in this repository for visual documentation of the Wazuh dashboard alerts and event logs).*

## 📌 Conclusion
Successfully integrated a Windows endpoint with Wazuh SIEM, validated real-time security event collection, and confirmed detection mechanisms for failed authentication attempts.
