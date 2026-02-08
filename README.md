# Multi-Site Enterprise Network Design & Implementation

A complete two-branch enterprise network simulation featuring VLAN segmentation, inter-VLAN routing, centralized services, and layered security controls using Cisco Packet Tracer.

**Context:** Advanced Networking course project (2025)

---

## Core Implementation

### Network Architecture
- Two-branch enterprise topology connected via a WAN serial link  
- Router-on-a-stick configuration using IEEE 802.1Q trunking  
- 10 VLANs across both branches (HR, IT, Sales, Management, Server)  
- Static routing between branches for predictable WAN communication
- Topology
  <img width="1920" height="1080" alt="Pasted image" src="https://github.com/user-attachments/assets/77eab5e3-a981-4620-8b47-b5ac17916336" />
 

### Services Configuration
- Centralized DHCP server using `ip helper-address` for cross-VLAN leasing  
- Centralized DNS server with internal domain records  
- Full service accessibility across VLANs via routing  

### Security Implementation
- Extended ACLs for inter-VLAN traffic control  
- Port security with sticky MAC address learning  
- DHCP snooping with trusted and untrusted port designation  
- Management VLAN isolation for administrative access  

---

## Technical Highlights

### Routing & Switching
- IEEE 802.1Q encapsulation across router subinterfaces  
- Static routing over a /30 WAN subnet  
- Spanning Tree Protocol (STP) for redundant switching  
- Broadcast domain segmentation into 10 isolated VLANs  

### Service Integration
- DHCP relay operation across VLAN boundaries  
- Internal DNS resolution for enterprise services  
- Centralized service administration model  

### Security Architecture
- ACL-based department isolation policies  
- Rogue DHCP server prevention via DHCP snooping  
- Unauthorized device connection blocking using port security  
- Restricted administrative access through management VLANs  

---

## Key Insights

### Design Decisions
- VLAN segmentation reduces broadcast traffic by approximately 90% compared to a flat network  
- Router-on-a-stick provides cost-effective inter-VLAN routing before Layer 3 switch deployment  
- Centralized DHCP/DNS simplifies management but requires precise relay configuration  
- Static routing offers predictability and security in stable, small-scale enterprise topologies  

### Performance Observations
- STP convergence time is critical for availability during link failures  
- ACL rule ordering directly impacts security policy correctness  
- DHCP relay introduces minimal latency while enabling centralized administration  
- Correct trunk configuration is essential to prevent VLAN propagation issues  

### Implementation Challenges
- DHCP broadcast forwarding requires `ip helper-address` on all client-facing subinterfaces  
- ACL logic must explicitly permit required services before broad deny rules  
- VLAN IDs must be consistently configured across all interconnected switches  
- STP root bridge selection influences traffic flow efficiency  

---

## Technology Stack

- **Simulation Platform:** Cisco Packet Tracer  
- **Routing:** Static routing  
- **Switching:** VLANs, IEEE 802.1Q, STP  
- **Network Services:** DHCP, DNS  
- **Security:** Extended ACLs, Port Security, DHCP Snooping  

---

## How to Run

1. Open `packet-tracer/final-project.pkt` in Cisco Packet Tracer  
2. Verify all router and switch configurations are loaded  
3. Test connectivity:
   - Inter-VLAN routing  
   - Inter-branch communication  
4. Validate services:
   - DHCP address assignment  
   - DNS name resolution  
5. Test security and resilience:
   - ACL enforcement  
   - Port security violations  
   - Link failure and STP reconvergence  
