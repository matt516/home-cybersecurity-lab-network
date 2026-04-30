# 🛡️ Cybersecurity Home Lab – Network Segmentation, Detection & Attack Simulation
## ⚠️STILL IN PROGRESS

## 📌 Overview

This project is a hands-on cybersecurity lab designed to simulate a segmented enterprise network. It demonstrates both offensive and defensive security concepts, including network segmentation, firewall configuration, reconnaissance, and centralized logging with a SIEM.

The lab was built to reinforce real-world skills aligned with **Security+ (SY0-701)** and entry-level cybersecurity roles such as SOC Analyst.

---

## 🧱 Lab Architecture

The environment is segmented using VLANs and controlled by a central firewall.

### Network Design

* **Management VLAN (10.0.10.0/24)**

  * Administrative systems
* **Server VLAN (10.0.20.0/24)**

  * Internal systems and SIEM
* **Attack VLAN (10.0.30.0/24)**

  * Kali Linux attacker machine

Traffic between VLANs is controlled using **pfSense firewall rules** following a least-privilege model.

---

## 🔧 Technologies & Tools

* **Firewall:** pfSense
* **SIEM:** Wazuh
* **Offensive Tools:** Kali Linux (Nmap, Netcat)
* **Systems:**

  * Ubuntu Server (Raspberry Pi)
  * Ubuntu Desktop (Mac hardware)
  * SIEM Server (Dell – Ubuntu Desktop)
  * Admin Workstation
  * Kali Linux (Mac hardware)

---

## 🔍 Key Features

### 🔐 Network Segmentation

* VLAN-based isolation of systems
* Controlled inter-VLAN communication
* Reduced attack surface and lateral movement prevention

---

### 🛡️ Firewall Configuration

* Rule-based access control (allow specific ports only)
* Implicit deny for all other traffic
* Validation using real attack simulation

---

### 🔎 Reconnaissance & Enumeration

* Host discovery and port scanning using Nmap
* Manual service testing with Netcat
* Interpretation of scan results (open, closed, filtered)

---

### 📊 SIEM & Detection (Wazuh)

* Centralized log collection
* Detection of simulated attack activity
* Visibility into network and system events

---

### 🧪 Attack Simulation

* Kali Linux used to simulate attacker behavior
* Scanning and probing internal systems
* Validation of firewall and detection mechanisms

---

### 🛠️ Troubleshooting & Debugging

* Diagnosed DHCP, DNS, and routing issues
* Resolved VLAN misconfigurations
* Debugged firewall rule behavior
* Identified hardware-related networking issues

---

📂 Project Structure

* `/docs` → Overview and planning
* `/network-design` → Diagrams and IP schemes
* `/setup` → Installation steps
* `/security` → Firewall rules and hardening
* `/testing` → Validation and results
* `/troubleshooting` → Issues and fixes

---

## 🧠 Skills Demonstrated

* Network segmentation (VLANs)
* Firewall rule design and validation
* Offensive security (reconnaissance & scanning)
* Defensive security (logging & detection)
* SIEM deployment and usage
* Linux system administration
* Network troubleshooting and debugging

---

## 🚀 Future Improvements

* Full Wazuh agent deployment across all systems
* Advanced attack simulations (brute force, lateral movement)
* Dashboard and alert tuning for SIEM
* Additional services for deeper enumeration testing

---

## ⚠️ Disclaimer

This project was built in a controlled lab environment for educational purposes only.
All IP addresses, systems, and configurations are fictional and do not represent a production network.

---

## 📬 Contact

Feel free to reach out or connect:

* GitHub: https://github.com/matt516
* LinkedIn: www.linkedin.com/in/matt-hartley-170521354

---
