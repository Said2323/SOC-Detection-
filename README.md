# SOC Detection Engineering Projects

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

##  Network Detections

### 1. Network Port Scanning Detection (Sigma Rule)
* **File:** `network_port_scan.yml`
* **Goal:** Detects aggressive network port scanning behavior from a single source IP.
* **Logic:** Triggers when a single source IP (`src_ip`) generates connection rejections (`action: 'reject'`) across more than 100 unique destination ports (`dest_port`) within a 1-minute window.

### 2. Network Sweeping Detection (Sigma Rule)
* **File:** `network_sweeping_detection.yml`
* **Goal:** Detects network sweeping (discovery) activity targeting multiple internal hosts.
* **Logic:** Triggers when a single source IP (`src_ip`) generates connection rejections against more than 50 unique destination IPs (`dest_ip`) within a 1-minute window.

##  Web Detections

### 1. Web SQL Injection Detection (Sigma Rule)
* **File:** `web_sqli_detection.yml`
* **Goal:** Detects an SQLi attempt from a malicious IP
* **Logic:** Triggers instantly when a single web request to Nginx access log contains SQL keywords ('UNION' and 'SELECT') inside the URL string.»
