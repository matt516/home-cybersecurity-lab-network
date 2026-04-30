## 💻 Ubuntu Desktop – Internal Workstation / Target System

### 📌 Overview

This system was deployed on Mac hardware running Ubuntu Desktop as part of a segmented cybersecurity lab environment. It functions as a general-purpose workstation within the Server VLAN and is used to simulate both a legitimate user system and a potential attack target.

The system plays a dual role:

* Supporting normal internal operations (user workstation behavior)
* Acting as a target for controlled attack simulations from the Attack VLAN

---

### 🧱 Lab Role & Placement

**Network Role:** Internal Workstation / Target System

**VLAN:** Server VLAN (VLAN 20)

**Subnet:** 10.0.20.0/24

**Assigned IP:** 10.0.20.60 (Static / DHCP Reservation)

This system resides in the same VLAN as other server resources, allowing testing of internal communication, access controls, and segmentation policies.

---

### ⚙️ Installation & Configuration

Ubuntu Desktop was installed on legacy Mac hardware to create a functional Linux workstation within the lab.

**Key configuration steps:**

* Installed Ubuntu Desktop with UEFI compatibility
* Configured network interface for VLAN-based connectivity
* Verified DHCP assignment and connectivity within Server VLAN
* Installed necessary system packages and updates
* Configured user environment for testing and administration

---

### 🌐 Networking & Connectivity

* Connected to Server VLAN via managed switch (802.1Q VLAN tagging)
* Receives IP addressing from VLAN-specific DHCP scope
* Communication controlled by pfSense firewall rules

**Access characteristics:**

* Accessible from Management VLAN for administration
* Restricted access from Attack VLAN (based on firewall rules)
* Allowed outbound traffic for updates and package management

---

### 🎯 Role in Security Testing

This system is used to simulate a real internal endpoint in security scenarios.

**Use cases:**

* Target for reconnaissance and scanning from Kali Linux
* Validation of firewall rules controlling inter-VLAN traffic
* Testing allowed services (e.g., HTTP, SSH if enabled)
* Observing system behavior during simulated attack activity

---

### 🔍 Validation & Testing

Testing was performed to confirm proper segmentation and access control:

* Verified visibility (or lack thereof) from Attack VLAN using:

  ```bash
  nmap -sn 10.0.20.0/24
  ```

* Tested port accessibility based on firewall rules:

  ```bash
  nmap -sS -p 22,80,443 10.0.20.60
  ```

* Observed differences between:

  * Open ports (explicitly allowed)
  * Filtered ports (blocked by firewall)
  * No response (silent drop behavior)

---

### 🔐 Security Considerations

* System exposure is controlled by upstream firewall (pfSense)
* Only required services are enabled for testing
* Acts as a demonstration of:

  * Least privilege access
  * Network segmentation effectiveness
  * Controlled attack surface

---

### 🧠 Key Skills Demonstrated

* Linux desktop deployment on non-native hardware
* VLAN-based network integration
* Endpoint role in network security architecture
* Reconnaissance validation from attacker perspective
* Firewall rule testing and interpretation

---

### ⚠️ Challenges & Lessons Learned

* Installing Linux on Mac hardware requires attention to:

  * UEFI boot configuration
  * Disk detection and partitioning
* Network issues can arise from:

  * Incorrect VLAN tagging
  * DHCP misconfiguration
* Endpoint systems must be tested from multiple network perspectives to validate security controls
* “No response” vs “filtered” behavior provides insight into firewall configuration

---

### 🚀 Future Improvements

* Deploy endpoint detection tools (EDR simulation)
* Generate and forward logs to SIEM (Wazuh)
* Configure additional services (web server, SSH hardening) for more advanced testing
* Simulate user activity to generate realistic log data

---

### ⚠️ Disclaimer

This system exists solely within a controlled lab environment.
All IP addresses, hostnames, and configurations are fictional and used for cybersecurity training purposes only.

---

