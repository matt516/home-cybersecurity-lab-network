# Project Overview

## Home Cybersecurity Lab

This project documents the design and implementation of a home cybersecurity lab built to simulate a segmented enterprise-style network.

The lab uses pfSense Community Edition as the primary firewall and router, with multiple internal networks created for different trust levels. The environment is designed to support hands-on practice for networking, firewall administration, segmentation, and cybersecurity concepts relevant to Security+ and entry-level roles.

## Goals

- Deploy a dedicated firewall using pfSense
- Create segmented networks using VLANs
- Practice firewall rule creation and rule ordering
- Prevent lateral movement between attacker and internal networks
- Build a home lab that can be expanded with IDS/IPS, SIEM, and vulnerable hosts

## Current Environment

### Core components
- Fiber internet connection
- Google Nest router upstream of pfSense
- pfSense CE installed on a Protectli Vault
- Araknis switch
- Laptop for administration and testing
- Raspberry Pi running Ubuntu Server
- Mac Desktop running Kali Linux
- Mac Desktop running Ubuntu Desktop
- Dell Laptop running Ubuntu Desktop

### Current network roles
- WAN: receives DHCP from upstream Nest router
- LAN: primary internal network
- ADMIN VLAN: trusted admin network
- ATTACK VLAN: isolated attacker/test network
- SERVERS VLAN: servers and "target" network

## What has been completed so far

- Installed pfSense CE
- Configured WAN and LAN interfaces
- Changed LAN subnet to a clean internal lab range
- Enabled DHCP for LAN
- Installed pfBlockerNG
- Created VLANs
- Created firewall rules to prevent lateral movement
- Began running nmap and nc tests
- Started wazuh setup and connected kali agent
  

## Skills learned so far

- Network interface assignment
- DHCP setup and troubleshooting
- Subnet planning
- VLAN creation
- Firewall rule design
- Rule order evaluation
- Troubleshooting connectivity and service failures
- Wazuh agent implementation
- Early nmap reconnaissance
