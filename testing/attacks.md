## 🔍 Reconnaissance & Enumeration – Nmap and Netcat

### 📌 Overview

This section documents reconnaissance and enumeration activities performed within a segmented cybersecurity lab environment using Kali Linux. The goal of these exercises is to simulate attacker behavior, discover network assets, and validate the effectiveness of firewall rules and network segmentation.

All testing was conducted within a controlled lab environment across isolated VLANs.

---

### 🧱 Lab Context

**Source System:** Kali Linux (Attack VLAN – 10.0.30.0/24)
**Target Systems:**

* Ubuntu Desktop 
* Ubuntu Server
* SIEM Server (Wazuh)

All reconnaissance activity required traversal through pfSense firewall rules, making results dependent on access control configurations.

---

### 🛰️ Network Discovery (Host Enumeration)

Initial reconnaissance focused on identifying active hosts within target subnets.

```bash
nmap -sn 10.0.20.0/24
```

**Purpose:**

* Identify live systems without performing port scans
* Map available targets within the Server VLAN

**Key observations:**

* Hosts may appear “down” due to firewall filtering
* ICMP blocking affects host discovery results
* Discovery results vary depending on scan origin (VLAN perspective)

---

### 🔎 Port Scanning & Service Enumeration

Performed TCP SYN scans to identify open ports and services on target systems.

```bash
nmap -sS -p- 10.0.20.50
```

**Purpose:**

* Identify exposed services
* Validate firewall allow rules (e.g., ports 22, 80, 443)
* Detect unintended open ports

**Additional targeted scans:**

```bash
nmap -sS -p 22,80,443 10.0.20.50
```

**Key observations:**

* Open ports correspond directly to firewall allow rules
* Non-allowed ports appear as:

  * Filtered (no response)
  * Closed (actively rejected)
* “Host seems down” often indicates filtering, not absence

---

### 🔐 Firewall Rule Validation

Reconnaissance results were used to confirm correct firewall behavior.

**Validation approach:**

* Compare expected open ports vs scan results
* Confirm that only explicitly allowed traffic is reachable
* Verify implicit deny behavior for all other traffic

**Example findings:**

* Allowed ports (e.g., 80/443) successfully detected
* All other ports dropped or filtered
* Inter-VLAN access restricted as designed

---

### 📡 Netcat (nc) Testing

Netcat was used for manual connectivity testing and service validation.

**Basic connectivity test:**

```bash
nc -zv 10.0.20.60 80
```

**Listener setup (target system):**

```bash
nc -lvnp 4444
```

**Client connection (from Kali):**

```bash
nc 10.0.20.60 4444
```

**Purpose:**

* Validate whether specific ports are reachable
* Simulate simple client-server communication
* Test firewall behavior in real-time

---

### 🎯 Reconnaissance Use Cases

These tools were used to simulate realistic attacker behavior:

* Discovering unknown hosts within a subnet
* Identifying exposed services on internal systems
* Testing segmentation boundaries between VLANs
* Verifying access restrictions enforced by firewall rules
* Generating activity for SIEM detection (Wazuh)

---

### 📊 Detection & Visibility

Reconnaissance activity was correlated with SIEM monitoring:

* Nmap scans generated detectable patterns in logs
* Connection attempts (Netcat) produced observable events
* Used to validate that attack activity is:

  * Logged
  * Detectable
  * Correlated across systems

---

### 🧠 Key Skills Demonstrated

* Network reconnaissance and host discovery
* Port scanning and service enumeration
* Interpretation of scan results (open, closed, filtered)
* Firewall rule validation through offensive testing
* Manual connectivity testing using Netcat
* Understanding of attacker methodologies

---

### ⚠️ Challenges & Lessons Learned

* Firewall filtering can cause misleading scan results
* ICMP blocking affects host discovery accuracy
* Scan results depend heavily on **network position (VLAN origin)**
* Open ports must be verified against intended security policies
* Tools like Netcat provide deeper insight than automated scans alone

---

### 🚀 Future Improvements

* Expand scanning techniques (UDP scans, service/version detection)
* Automate reconnaissance workflows
* Integrate scan results with SIEM dashboards
* Simulate more advanced attack scenarios (lateral movement, exploitation)
* Perform enumeration against additional services (web, SSH, etc.)

---

### ⚠️ Disclaimer

All reconnaissance activities were performed in a controlled lab environment for educational purposes only.
No unauthorized scanning or testing was conducted against external or production systems.

---

