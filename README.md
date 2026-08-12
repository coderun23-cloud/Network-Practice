# 🏢 Enterprise Multi-VLAN Network Architecture

<p align="center">
  <img src="https://img.shields.io/badge/Cisco_Packet_Tracer-v8.x-00599C?style=for-the-badge&logo=cisco&logoColor=white" alt="Packet Tracer" />
  <img src="https://img.shields.io/badge/Status-Complete-green?style=for-the-badge" alt="Status" />
  <img src="https://img.shields.io/badge/VLANs-5-B0B0B0?style=for-the-badge" alt="VLAN Count" />
</p>

This repository contains a full enterprise network simulation designed in Cisco Packet Tracer. The design demonstrates high-availability routing at the core/edge layers, robust network segmentation using VLANs, and integrated wireless access for department users.

---

## 🖼️ Network Topology Diagram

Below is the visual overview of the final network architecture. This is a high-resolution representation of the logical connections and department zones.

<p align="center">
  <img src="./topology.png" alt="Packet Tracer Network Topology" width="950"/>
</p>

### 🔍 Topology Map Breakdown

The network is split into six main visual zones, color-coded in the diagram above:

| Zone Color | Functional Area | Key Devices |
| :---: | :--- | :--- |
| **🔴 Red** | **WAN/Internet Core** | Edget Router 1, Core Router 0, Core Router 2, External Server 0 |
| **🩵 Light Blue** | **VLAN 10: IT Department** | Switch 0, Access Point 0, PC 0, Laptop 0, PC 4 |
| **💙 Dark Blue** | **VLAN 20: HR Department** | Switch 1, Access Point 1, PC 1, Laptop 1 |
| **🟢 Green** | **VLAN 30: Security** | Switch 3, Access Point 3, PC 2, Laptop 2 |
| **🟠 Orange** | **VLAN 40: Finance** | Switch 2, Access Point 2, PC 3, Laptop 3 |
| **🟩 Bright Green** | **VLAN 50: Server Farm** | Switch 4, Web Server, DNS Server |

---

## 📊 IP Addressing & VLAN Scheme

| Status | VLAN ID | Dept. Icon | Department | Subnet Range | Gateway |
| :---: | :---: | :---: | :--- | :--- | :--- |
| ✅ | **10** | 🖥️ | **IT Dept.** | `10.0.10.0/24` | `10.0.10.1` |
| ✅ | **20** | 👥 | **HR Dept.** | `10.0.20.0/24` | `10.0.20.1` |
| ✅ | **30** | 🛡️ | **Security** | `10.0.30.0/24` | `10.0.30.1` |
| ✅ | **40** | 💰 | **Finance** | `10.0.40.0/24` | `10.0.40.1` |
| ✅ | **50** | ☁️ | **Servers** | `10.0.50.0/24` | `10.0.50.1` |

---

## 🚀 Key Technical Implementation

*   **⚡ Core Switching:** Used a central Multilayer Switch (3650) as the L3 termination point for all department VLANs.
*   **🔗 Trunking:** Enabled 802.1Q trunking on all links between the Core Switch and the access switches (Switch0-4) to allow multi-VLAN traffic traversal.
*   **📡 Wireless Access:** Configured lightweight Access Points in each zone to provide 802.11 Wi-Fi connectivity, mapped to their respective departmental VLANs.
*   **🌐 WAN Edge:** Routers 0, 1, and 2 are configured with dynamic routing protocols and redundant links to simulate a reliable path toward external internet/cloud services.

---

## 🛠️ Requirements & How to View

1.  Requires **Cisco Packet Tracer (v8.0 or higher)**.
2.  Clone this repository to your local machine:
    ```bash
    git clone [https://github.com/yourusername/your-repo-name.git](https://github.com/yourusername/your-repo-name.git)
    ```
3.  Navigate to the directory and open the `.pkt` file inside Packet Tracer.