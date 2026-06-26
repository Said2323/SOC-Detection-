# SOC & Detection Engineering Projects

Welcome to my repository! Here I store detection rules and analytical use-cases developed for SIEM systems during my preparation for the SOC Analyst L1 role.

##  Windows Detections

### 1. Targeted Brute Force Detection (Sigma Rule)
* **File:** `windows_bruteforce_detection.yml`
* **Goal:** Detects automated targeted brute-force attacks against Windows infrastructure.
* **Logic:** Triggers when more than 20 failed login events (`Event ID 4625`) with Network/RDP logon types (`LogonType 3/10`) occur for a single username within a 5-minute window.
  
## Linux Detections

### 1. SSH Brute Force Detection (Sigma Rule)
* **File:** `linux_ssh_bruteforce.yml`
* **Goal:** Detects automated SSH brute force attacks against Linux hosts.
* **Logic:** Triggers when more than 20 authentication failure events (`Failed password`) occur for a specific user account within a 5-minute window.
