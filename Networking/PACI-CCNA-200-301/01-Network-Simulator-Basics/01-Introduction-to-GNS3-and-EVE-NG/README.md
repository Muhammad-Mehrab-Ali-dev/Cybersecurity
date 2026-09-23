# 01 — Introduction to GNS3 and EVE-NG

## 🎯 Objective

Understand the purpose of network emulation platforms and how tools such as **GNS3** and **EVE-NG** are used to build, configure, test, and troubleshoot network topologies.

---

## 🌐 What is GNS3?

**GNS3 (Graphical Network Simulator-3)** is an open-source network emulator that allows users to create virtual network topologies and work with different network devices.

It can be used to:

* Build virtual network topologies
* Configure routers and switches
* Test network configurations
* Troubleshoot connectivity problems
* Practice networking without requiring physical hardware
* Work with multiple network vendors and technologies

GNS3 originally focused heavily on Cisco device emulation through **Dynamips**, but has evolved to support many different virtual appliances and technologies.

🔗 [GNS3 Marketplace](https://gns3.com/marketplace/appliances)

---

## 🖥️ What is EVE-NG?

**EVE-NG (Emulated Virtual Environment – Next Generation)** is a multi-vendor network emulation platform.

It allows virtual network devices to be placed into a topology and configured through their normal interfaces, making it useful for networking education, certification preparation, testing, and troubleshooting.

EVE-NG supports different types of virtual network devices, including:

* Cisco routers
* Cisco switches
* Cisco IOL/IOU devices
* Cisco QEMU-based appliances
* Firewalls
* Linux appliances
* Other vendor virtual appliances

### EVE-NG Editions

EVE-NG provides:

* **Community Edition**
* **Professional Edition**

For this project, I use the **EVE-NG Community Edition** as my primary networking lab environment.

---

## ⚖️ GNS3 vs EVE-NG

| Feature                      | GNS3                     | EVE-NG                   |
| ---------------------------- | ------------------------ | ------------------------ |
| Network emulation            | ✅                        | ✅                        |
| Multi-vendor devices         | ✅                        | ✅                        |
| Virtual topologies           | ✅                        | ✅                        |
| Cisco devices                | ✅                        | ✅                        |
| Open-source/community option | ✅                        | ✅                        |
| Web-based lab interface      | Limited/depends on setup | ✅                        |
| Used in this project         | Studied                  | **Primary lab platform** |

> **Note:** GNS3 was studied as part of the PACI introduction to network simulators. EVE-NG was selected as the primary lab environment and was actually installed, configured, and verified for this project.

---

## 🔐 Why Network Emulation Matters for Cybersecurity

A cybersecurity professional needs to understand how networks actually operate.

Network emulation provides a safe environment where network behavior can be practiced without depending entirely on physical hardware.

It allows me to:

```text
Build Topology
      ↓
Configure Devices
      ↓
Generate Network Traffic
      ↓
Test Connectivity
      ↓
Troubleshoot Problems
      ↓
Understand Network Behavior
      ↓
Apply Network Security Concepts
```

This foundation will later support areas such as:

* Network security
* Traffic analysis
* Firewalls
* ACLs
* VLAN security
* Routing security
* IDS/IPS
* Network troubleshooting
* Incident investigation

---

## 🧪 My Lab Environment

For this project, **EVE-NG is the primary network emulation platform**.

The environment includes:

* VMware Workstation
* EVE-NG Community Edition
* Cisco IOL switch images
* Cisco Dynamips router images
* Cisco QEMU-based images
* WinSCP for file transfer
* PuTTY/SSH for administration

GNS3 was studied conceptually but was **not installed** as part of this lab environment.

---

## 📸 Evidence

### EVE-NG Interface

The EVE-NG interface was successfully accessed as part of the lab environment preparation.

![EVE-NG Interface](./screenshots/eve-ng-interface.png)

---

## 🧠 Key Takeaways

* **GNS3** and **EVE-NG** are network emulation platforms used to build and test virtual network environments.
* Network emulation reduces the need for physical networking hardware during learning and testing.
* EVE-NG supports multiple vendors and different types of virtual appliances.
* EVE-NG Community Edition is being used as my primary networking lab environment.
* Understanding network behavior is an important foundation for cybersecurity.
* The next step is to prepare and verify the EVE-NG environment for practical Cisco networking labs.

---

## 📚 PACI

**Program:** PACI Cybersecurity Program
**Module:** CCNA 200-301
**Section:** 01 — Network Simulator & Basics
**Lecture:** 01 — Introduction to GNS3 and EVE-NG

**Status:** ✅ Completed

