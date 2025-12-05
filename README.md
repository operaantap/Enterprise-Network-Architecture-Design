# **Enterprise Network Engineering Project – VLANs, Inter-VLAN Routing, DHCP, DNS, HTTP, and Multi-Layer Switching**

## **📌 Project Overview**

This project demonstrates the design and deployment of an enterprise-grade network using **Layer-3 switching, Layer-2 access switching, VLAN segmentation, Inter-VLAN routing, DHCP services, DNS resolution, HTTP hosting, and OSI-layer traffic simulation** in Cisco Packet Tracer.
It reflects the type of infrastructure used in real organizations—secure, segmented, scalable, and well-structured.

The project integrates everything from **network segmentation** to **automated IP addressing**, **cross-VLAN communication**, **traffic analysis**, and **device hardening**, making it an excellent portfolio piece for cybersecurity and network engineering roles.

---

## **🎯 Project Vision & Mission**

### **Vision**

To design a resilient, secure, and structured enterprise network that demonstrates real-world segmentation, routing, and core network services.

### **Mission**

To build a multi-service architecture combining VLANs, DHCP, DNS, HTTP, trunking, SVIs, inter-VLAN routing, and OSI-layer simulation to strengthen practical knowledge in modern network engineering and cybersecurity.

---

## **💡 Ideation Process**

The idea for this project grew from my desire to move from basic networking tasks to a realistic enterprise-level architecture.
Integrating DHCP, DNS, and HTTP allowed for automated IP management and centralized services—just like real companies use.
Using simulation mode helped me visualize traffic behavior across the OSI model, strengthening my troubleshooting skills.
Combining these elements resulted in a complete end-to-end network solution mirroring real corporate environments.

---

## **🛠 Creation Process**

* Designed the network topology by defining VLANs, IP subnets, trunk links, routing roles, and DHCP scopes.
* Configured core services—DHCP, DNS, and HTTP—on the server and set up dynamic IP allocation for all hosts.
* Deployed L3 switching, SVIs, trunking, inter-VLAN routing, secure SSH access, and VLAN-based segmentation.
* Validated the infrastructure using simulation mode to analyze OSI-layer traffic and troubleshoot all routing and VLAN challenges.

---

## **🏗 Network Architecture**

### **Components Used**

* 1 × Layer-3 Switch
* 1 × Layer-2 Switch
* 1 × Server (DHCP + DNS + HTTP)
* Multiple PCs (for VLAN-based departments)

### **VLANs Configured**

| VLAN | Name       | Subnet          | Gateway (SVI) |
| ---- | ---------- | --------------- | ------------- |
| 10   | MANAGEMENT | 192.168.10.0/24 | 192.168.10.1  |
| 20   | STAFF      | 192.168.20.0/24 | 192.168.20.1  |
| 30   | GUESTS     | 192.168.30.0/24 | 192.168.30.1  |

---

## **🌐 Core Services Configuration**

### **DHCP**

* DHCP pools created for each VLAN
* Default gateways assigned from respective SVIs

### **DNS**

* Configured to resolve internal hostnames
* Linked with internal server IP

### **HTTP**

* Hosted a simple webpage for testing
* Verified connectivity across VLANs

---

## **🔁 Inter-VLAN Routing (L3 Switch SVIs)**

SVIs were created on the L3 switch to route traffic between VLANs:

```
interface vlan 10
 ip address 192.168.10.1 255.255.255.0
interface vlan 20
 ip address 192.168.20.1 255.255.255.0
interface vlan 30
 ip address 192.168.30.1 255.255.255.0
```

Routing works as long as SVIs are **up** and each VLAN is reachable from its ports.

---

## **🔗 Trunking (L3 ↔ L2 Switch)**

```
interface Gig1/0/3
 switchport mode trunk
 switchport trunk allowed vlan 10,20,30
 switchport trunk native vlan 999
```

* Solved **Native VLAN mismatch** by ensuring both switches used VLAN 999.
* Ensured the trunk allowed all operational VLANs.

---

## **🧪 Testing & Verification Commands**

* `show vlan brief`
* `show ip interface brief`
* `show interfaces trunk`
* `ping` tests across VLANs
* OSI layer traffic simulation using Packet Tracer Simulation Mode

---

## **📈 Key Lessons Learned**

* Native VLAN consistency is critical on trunk links
* L3 SVIs must be UP (one active port per VLAN)
* DHCP scope and gateway alignment matter
* L2 switches **cannot** route—only SVIs or routers can
* Simulation mode is powerful for OSI-layer troubleshooting
* Central services strengthen enterprise network efficiency

---

## **📊 SWOT Analysis**

### **Strengths**

* Real-world enterprise network design with multiple services.
* Strong troubleshooting ability using OSI-layer reasoning.

### **Weaknesses**

* High learning curve for advanced routing and trunking logic.
* Scalability tests (redundancy, STP, HSRP) not yet included.

### **Opportunities**

* Expand into ACLs, firewall segmentation, and cybersecurity controls.
* Convert into a full portfolio series on GitHub + LinkedIn.
* Certification readiness for CCNA/CCNP.

### **Threats**

* Rapid industry evolution (SDN, automation, cloud networking).
* Misconfigurations in bigger infrastructures can cause outages.

---

## **🧭 Final Reflections & Future Steps**

This project strengthened my understanding of how real enterprise networks operate—from VLAN segmentation to inter-VLAN routing and service orchestration.
It also sharpened my troubleshooting approach through OSI-layer simulation.
Next, I plan to integrate redundancy (STP, HSRP), add ACL-based security, and begin automating parts of the topology using Python and Ansible.

---

## **📁 Repository Contents**

* `Enterprise-Network-Design.pdf`
* `README.md` (this file)
* Optional: configuration files, images, diagrams

---

## **👤 Author**

**Olayiwola Michael**
Cybersecurity & Network Engineering Enthusiast
LinkedIn: (https://www.linkedin.com/in/michael-olayiwola-9208a417b/)

