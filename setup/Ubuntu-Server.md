## 🖥️ Ubuntu Server – SIEM & Logging Node

### 📌 Overview

This system was deployed on a Raspberry Pi as part of a segmented cybersecurity lab environment. It functions as a lightweight server used for centralized logging, monitoring, and service hosting.

The primary purpose of this node is to simulate a production-style server environment and support **defensive security operations**, including log collection and analysis.

---

### 🧱 Lab Role & Placement

**Network Role:** Server / Blue Team Infrastructure

**VLAN:** Server VLAN (VLAN 20)

**Subnet:** 10.0.20.0/24

**Assigned IP:** 10.0.20.20 (Static / DHCP Reservation)

This system resides in an isolated server network and is protected by firewall rules that restrict access to only required services.

---

### ⚙️ Installation & Configuration

Ubuntu Server was installed on a Raspberry Pi to provide a low-power, always-on system for lab services.

**Key configuration steps:**

* Installed Ubuntu Server (headless) using imaging tools
* Enabled SSH for remote administration
* Configured static IP addressing within VLAN
* Updated system packages and repositories
* Hardened base system by minimizing unnecessary services

---

### 🔐 System Hardening

Basic security measures were implemented to simulate a production-ready server:

* Disabled unused services and ports
* Applied system updates and security patches
* Limited exposure to only required ports via firewall rules (pfSense)

---

### 📊 SIEM & Logging (Wazuh Integration)

This system is used to support centralized logging and monitoring within the lab.

**Functionality:**

* Acts as a logging node / SIEM component
* Receives and processes logs from other systems (planned/implemented)
* Provides visibility into:

  * Network activity
  * Authentication events
  * Potential attack indicators

**Use case in lab:**

* Detect activity originating from the Attack VLAN (Kali Linux)
* Correlate scan activity (e.g., Nmap) with logged events
* Validate detection capabilities against simulated attacks

---

### 🌐 Networking & Connectivity

* Connected to Server VLAN through managed switch (802.1Q tagging)
* Communication controlled by pfSense firewall rules
* Only specific traffic allowed from:

  * Management VLAN (admin access)
  * Attack VLAN (for testing detection scenarios)

**Testing performed:**

* Verified connectivity between VLANs
* Confirmed firewall restrictions are enforced
* Ensured server accessibility only on intended ports

---

### 🧠 Key Skills Demonstrated

* Linux server deployment (headless environment)
* Network segmentation and VLAN design
* Secure remote access (SSH configuration)
* SIEM/logging concepts (Wazuh integration)
* Firewall rule validation and traffic control
* System hardening fundamentals

---

### ⚠️ Challenges & Lessons Learned

* Headless systems require strong understanding of **network configuration and remote access**
* Misconfigured IP addressing or VLAN tagging can completely block access
* Firewall rules must allow **management access without overexposing services**
* Logging systems are only valuable if properly placed within the network architecture

---

### 🚀 Future Improvements

* Complete full Wazuh deployment with agents across all lab systems
* Implement log forwarding and alerting dashboards
* Add intrusion detection capabilities (HIDS/NIDS integration)
* Harden SSH further (fail2ban, port changes, stricter policies)
* Automate updates and monitoring tasks

---

### ⚠️ Disclaimer

This system exists solely within a controlled lab environment.
All IP addresses, hostnames, and configurations are fictional and used for cybersecurity training purposes only.

---

