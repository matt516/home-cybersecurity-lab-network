## 🛡️ SIEM Server – Wazuh Monitoring & Detection Node

### 📌 Overview

This system was configured as a centralized Security Information and Event Management (SIEM) server within a segmented cybersecurity lab environment. It is responsible for collecting, analyzing, and correlating logs from multiple systems across different VLANs.

The SIEM server provides visibility into network activity and is used to detect and analyze simulated attack behavior originating from the Attack VLAN.

---

### 🧱 Lab Role & Placement

**Network Role:** SIEM / Logging & Detection Server

**VLAN:** Server VLAN (VLAN 20)

**Subnet:** 10.0.20.0/24

**Assigned IP:** 10.0.20.70 (Static / DHCP Reservation)

This system is strategically placed within the Server VLAN to receive logs from internal systems while remaining protected by firewall segmentation.

---

### ⚙️ Installation & Configuration

Ubuntu Desktop was deployed on Dell hardware to support SIEM functionality with sufficient resources for log processing and visualization.

**Key configuration steps:**

* Installed Ubuntu Desktop with full GUI support
* Updated system packages and dependencies
* Installed and configured Wazuh SIEM components
* Verified service operation and system resource usage
* Ensured network connectivity across VLANs for log ingestion

---

### 📊 SIEM Functionality (Wazuh)

The system is configured to provide centralized monitoring and detection capabilities.

**Core functions:**

* Log collection from multiple systems (planned/implemented)
* Event correlation and analysis
* Detection of suspicious activity
* Visualization of alerts and system events

**Monitored activity includes:**

* Network scans (e.g., Nmap from Attack VLAN)
* Authentication events
* Service access attempts
* System-level logs

---

### 🔍 Detection Use Cases

This SIEM server is used to validate detection capabilities within the lab.

**Example scenarios:**

* Detecting reconnaissance activity from Kali Linux
* Identifying repeated connection attempts or scanning behavior
* Correlating events across multiple systems
* Verifying that simulated attacks generate observable alerts

---

### 🌐 Networking & Integration

* Connected to Server VLAN via managed switch (802.1Q VLAN tagging)
* Receives traffic/logs based on firewall rules configured in pfSense
* Communication allowed from:

  * Management VLAN (administration)
  * Server VLAN (internal systems)
  * Controlled traffic from Attack VLAN (for detection testing)

**Security controls:**

* Firewall rules restrict unnecessary inbound access
* Only required ports/services exposed for SIEM functionality

---

### 🔐 Security Considerations

* Centralized logging improves visibility but must be protected
* SIEM server is isolated within Server VLAN to reduce exposure
* Access limited to administrative systems
* Designed to demonstrate:

  * Defense-in-depth
  * Monitoring and detection strategies
  * Secure placement of critical infrastructure

---

### 🧠 Key Skills Demonstrated

* SIEM deployment and configuration (Wazuh)
* Log analysis and event correlation
* Network segmentation awareness
* Detection of simulated attack activity
* Linux system administration
* Security monitoring concepts

---

### ⚠️ Challenges & Lessons Learned

* SIEM systems require proper placement to collect meaningful data
* Logging without analysis provides limited value
* Detection depends on both:

  * Proper log ingestion
  * Correct rule/configuration tuning
* Resource constraints must be considered for log-heavy systems
* Firewall rules must balance:

  * Accessibility for logging
  * Security of the SIEM server itself

---

### 🚀 Future Improvements

* Deploy Wazuh agents across all lab endpoints
* Tune detection rules to reduce false positives
* Implement dashboards for improved visualization
* Simulate more advanced attack scenarios (brute force, lateral movement)
* Integrate additional data sources (network logs, system metrics)

---

### ⚠️ Disclaimer

This system exists solely within a controlled lab environment.
All IP addresses, hostnames, and configurations are fictional and used for cybersecurity training purposes only.

---

