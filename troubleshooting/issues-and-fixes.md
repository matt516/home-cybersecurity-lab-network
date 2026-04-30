## 🛠️ Troubleshooting & Debugging – Lab Environment

### 📌 Overview

This section documents real-world issues encountered while building and operating a segmented cybersecurity lab environment. It highlights the troubleshooting process, root cause analysis, and resolutions.

These scenarios demonstrate practical problem-solving skills across networking, system configuration, and security validation.

---

### 🌐 Issue 1: No Internet Connectivity (Kali Linux)

**Symptoms:**

* Unable to reach external websites
* `ping 8.8.8.8` failed or showed packet loss
* `ping google.com` failed with DNS resolution error

**Diagnosis Steps:**

* Verified interface configuration:

  ```bash
  ip a
  ip route
  ```
* Tested connectivity by IP vs domain
* Checked DHCP lease status
* Reviewed DNS configuration

**Root Cause:**

* DNS misconfiguration and/or missing resolver settings

**Resolution:**

* Updated DNS settings
* Verified connectivity:

  ```bash
  ping 8.8.8.8
  ping google.com
  ```

**Lesson Learned:**
A system can have network connectivity but still fail due to DNS issues.

---

### 📡 Issue 2: DHCP Failure (No IP Assignment)

**Symptoms:**

* System not receiving IP address
* Error: “No response from port 68 (DHCP Discover)”
* Interface showed no valid IPv4 address

**Diagnosis Steps:**

* Checked DHCP server configuration (pfSense)
* Verified VLAN assignment on switch
* Compared working vs non-working systems
* Used packet capture to observe DHCP traffic

**Root Cause:**

* Misconfigured VLAN or DHCP scope mismatch

**Resolution:**

* Corrected VLAN tagging
* Ensured DHCP server was enabled for correct subnet
* Renewed DHCP lease

**Lesson Learned:**
DHCP issues are often related to VLAN misconfiguration rather than the client itself.

---

### 🔌 Issue 3: Unstable Network via USB Ethernet Adapter

**Symptoms:**

* Intermittent connectivity
* Packet loss
* Inconsistent interface naming (e.g., `eth0`, `enx...`)

**Diagnosis Steps:**

* Tested connectivity across different devices
* Checked interface status:

  ```bash
  ip a
  ```
* Compared behavior with direct Ethernet connection

**Root Cause:**

* USB Ethernet adapter driver instability and hardware limitations

**Resolution:**

* Replaced or stabilized adapter usage
* Adjusted network configuration as needed

**Lesson Learned:**
Hardware reliability can significantly impact network performance and troubleshooting accuracy.

---

### 🔍 Issue 4: Nmap “Host Seems Down”

**Symptoms:**

* Nmap reports: “Host seems down”
* Expected systems not appearing in scan results

**Diagnosis Steps:**

* Verified target system is powered on
* Tested direct connectivity using `ping`
* Ran scans with different options:

  ```bash
  nmap -sn <target-subnet>
  nmap -Pn <target-ip>
  ```

**Root Cause:**

* ICMP blocked or filtered by firewall

**Resolution:**

* Used `-Pn` flag to skip host discovery
* Confirmed firewall behavior aligns with security rules

**Lesson Learned:**
“Host seems down” often indicates filtering, not absence of a system.

---

### 🔐 Issue 5: Expected Open Ports Not Showing

**Symptoms:**

* Ports configured as allowed in firewall not appearing open in scans

**Diagnosis Steps:**

* Verified firewall rule order and placement
* Confirmed correct source/destination VLAN
* Tested from correct network perspective (Attack VLAN)
* Ran targeted scans:

  ```bash
  nmap -sS -p 80,443 <target-ip>
  ```

**Root Cause:**

* Incorrect firewall rule order or source network mismatch

**Resolution:**

* Adjusted rule placement (above block rules)
* Ensured correct source/destination configuration
* Re-tested with Nmap

**Lesson Learned:**
Firewall rules are order-dependent and must match the correct traffic direction.

---

### 🧠 Issue 6: pfSense Connectivity / IP Conflict

**Symptoms:**

* Network instability after introducing pfSense
* Devices unable to access internet
* DHCP inconsistencies

**Diagnosis Steps:**

* Checked LAN IP configuration on pfSense
* Verified presence of multiple DHCP servers
* Reviewed upstream router configuration

**Root Cause:**

* IP conflict and overlapping DHCP services between router and pfSense

**Resolution:**

* Disabled DHCP on upstream router OR adjusted network ranges
* Assigned unique LAN subnet to pfSense
* Renewed client leases

**Lesson Learned:**
Only one DHCP server should control a subnet to avoid conflicts.

---

### 🧠 Key Skills Demonstrated

* Network troubleshooting (DHCP, DNS, routing)
* VLAN configuration and validation
* Firewall rule debugging and analysis
* Use of diagnostic tools (`ping`, `ip`, `nmap`, `nc`)
* Root cause analysis and systematic problem solving
* Understanding of real-world infrastructure issues

---

### 🚀 Continuous Improvement Approach

* Compare working vs non-working systems
* Test from multiple network perspectives (different VLANs)
* Validate assumptions using multiple tools
* Document issues and resolutions for future reference

---

### ⚠️ Disclaimer

All issues and resolutions occurred within a controlled lab environment designed for cybersecurity training.
Configurations and IP addressing are fictional and do not represent a production network.

---

