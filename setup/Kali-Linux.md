## 🐉 Kali Linux – Offensive Security Workstation (Lab Build)

### 📌 Overview

This system was configured as part of a segmented cybersecurity lab environment to simulate an attacker workstation. The goal of this setup is to perform reconnaissance, validate firewall rules, and test network segmentation controls against isolated VLANs.

Kali Linux is deployed as the primary offensive security platform within the **Attack VLAN**, allowing safe and controlled testing of network defenses.

---

### 🧱 Lab Role & Placement

**Network Role:** Attacker / Red Team Simulation

**VLAN:** Attack VLAN (VLAN 30)

**Subnet:** 10.0.30.0/24

**Assigned IP:** 10.0.30.50 (Static / DHCP Reservation)

This system is intentionally isolated from other VLANs and must traverse the firewall to reach target systems, enabling validation of segmentation and access control policies.

---

### ⚙️ Installation & Configuration

Kali Linux was installed on dedicated hardware to allow full control over networking and performance.

**Key configuration steps:**

* Performed graphical installation with UEFI support
* Rufus partitioning GPT in DD mode
* Configured network interface for VLAN-based environment
* Connected via Ethernet
* Verified DHCP functionality and manually troubleshot lease issues
* Adjusted package sources to use official Kali repositories only
* Resolved installation issues related to missing packages and repository conflicts

---

### 🌐 Networking Setup & Troubleshooting

Significant effort was spent diagnosing and resolving real-world networking issues:

* Identified and resolved **DHCP failures** (no response on port 68)

* Troubleshot **packet loss and lack of internet connectivity**

* Diagnosed **DNS resolution failures** despite successful IP routing

* Tested connectivity using:

  * `ping` (IP vs domain testing)
  * `ip a` / `ip route`
  * manual interface resets

---

### 🔍 Reconnaissance & Network Discovery

Kali Linux is used to simulate attacker behavior within the lab.

**Techniques practiced:**

* Host discovery across subnets:

  ```bash
  nmap -sn 10.0.30.0/24
  ```

* Port scanning and service enumeration:

  ```bash
  nmap -sS -p- 10.0.20.50
  ```

* Validation of expected open ports (e.g., 53, 80, 443)

* Identification of filtering behavior:

  * “Host seems down” scenarios
  * Silent drops vs rejected traffic

---

### 🔐 Firewall Validation Testing

Kali Linux is used to verify pfSense firewall rules and segmentation policies.

**Tests performed:**

* Confirmed allowed traffic from Attack VLAN → Server VLAN (specific ports only)
* Verified blocked lateral movement between VLANs
* Tested rule order and implicit deny behavior
* Used scan results to confirm:

  * Open ports match allow rules
  * All other traffic is dropped or filtered

---

### 🧠 Key Skills Demonstrated

* Network troubleshooting (DHCP, DNS, routing)
* VLAN-aware testing and segmentation validation
* Offensive security fundamentals (recon + scanning)
* Firewall rule verification and analysis
* Real-world debugging of unstable network environments

---

### ⚠️ Challenges & Lessons Learned

* A system can have **IP connectivity but still fail DNS resolution**
* USB network adapters can introduce **driver and interface inconsistencies**
* Misconfigured DHCP or multiple DHCP sources can break connectivity entirely
* Firewall rules must be tested from the **correct network perspective (source VLAN matters)**
* “Host seems down” in Nmap often indicates filtering, not absence

---

### 🚀 Future Improvements

* Integrate with SIEM (Wazuh) for attack detection visibility
* Perform controlled exploitation scenarios (within lab scope)
* Automate scanning and logging workflows
* Expand testing to include web application enumeration tools

---

### ⚠️ Disclaimer

This system exists solely within a controlled lab environment.
All IP addresses, systems, and configurations are simulated for cybersecurity training purposes and do not represent a production network.

---


