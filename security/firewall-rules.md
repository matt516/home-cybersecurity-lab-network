# Firewall Rules and Segmentation

## Objective

Create segmentation between internal lab networks so that the ATTACK network can access the internet but cannot access internal private networks such as LAN or LAB.

## Networks

- LAN: `192.168.10.0/24`
- LAB: `192.168.20.0/24`
- ATTACK: `192.168.30.0/24`

## ATTACK Rules

### Rule 1: Block internal/private network access
- Action: Block
- Interface: ATTACK
- Protocol: IPv4 any
- Source: ATTACK subnets
- Destination: `PRIVATE_NETS` alias

This rule prevents hosts in the ATTACK segment from reaching RFC1918/private address space, including the lab's internal subnets.

### Rule 2: Allow remaining traffic
- Action: Pass
- Interface: ATTACK
- Protocol: IPv4 any
- Source: ATTACK subnets
- Destination: any

This rule allows ATTACK systems to access the internet while preserving the block on internal networks due to rule order.

## LAB Rules

### Current LAB policy
- Action: Pass
- Interface: LAB
- Protocol: Any
- Source: LAB net
- Destination: Any

This allows LAB systems to function as a more trusted internal segment for testing and administration.

## Important Concept: Rule Order

pfSense processes rules from top to bottom. The ATTACK block rule must appear above the ATTACK allow rule. If the allow rule is placed first, segmentation fails because internal traffic is permitted before the block rule is reached.

## Security Benefit

These rules simulate enterprise-style segmentation and lateral movement prevention by isolating attacker systems from trusted internal networks.
