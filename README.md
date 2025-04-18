# 🚀 Cisco Static Routing Lab with Three Routers (R1, R2, R3)

![Cisco](https://img.shields.io/badge/Cisco-Lab-blue) ![Routing](https://img.shields.io/badge/Static-Routing-brightgreen) ![Status](https://img.shields.io/badge/Status-Completed-success)

Welcome to a practical Cisco routing lab setup using **static routing**! This simulation demonstrates how to configure **inter-router connectivity** across three routers using CLI-based configuration.

---

## 🗺️ Network Topology

```
       [LAN 1]
      192.168.1.0/24
          |
          |
        (R1)
     192.168.12.1/30
          |
     192.168.12.2/30
        (R2)
      /         \
192.168.2.0/24  192.168.13.1/30
   [LAN 2]           |
                  192.168.13.2/30
                      |
                    (R3)
                  [LAN 3]
               192.168.3.0/24
```

---

## 🔧 Devices and IP Addresses

| Router | Interface | IP Address         | Subnet Mask       | Description        |
|--------|-----------|--------------------|-------------------|--------------------|
| R1     | G0/0      | 192.168.1.100      | 255.255.255.0     | LAN1               |
| R1     | G0/1      | 192.168.12.1       | 255.255.255.252   | Link to R2         |
| R2     | G0/0      | 192.168.2.100      | 255.255.255.0     | LAN2               |
| R2     | G0/1      | 192.168.12.2       | 255.255.255.252   | Link to R1         |
| R2     | G0/2      | 192.168.13.1       | 255.255.255.252   | Link to R3         |
| R3     | G0/0      | 192.168.3.100      | 255.255.255.0     | LAN3               |
| R3     | G0/1      | 192.168.13.2       | 255.255.255.252   | Link to R2         |

---

## 🛠️ Key Configurations

- All routers are configured with:
  - Hostnames
  - IP addresses for LAN and serial interfaces
  - Static routes to reach other networks

📁 Full configuration can be found in [`config.txt`](./config.txt)

---

## 📡 Static Routing Summary

| From | Destination Network | Next Hop         |
|------|----------------------|------------------|
| R1   | 192.168.2.0/24       | 192.168.12.2     |
| R1   | 192.168.3.0/24       | 192.168.12.2     |
| R2   | 192.168.1.0/24       | 192.168.12.1     |
| R2   | 192.168.3.0/24       | 192.168.13.2     |
| R3   | 192.168.1.0/24       | 192.168.13.1     |
| R3   | 192.168.2.0/24       | 192.168.13.1     |

---

## ✅ How to Use

1. Open Cisco Packet Tracer or a similar simulator.
2. Create three routers and connect them as per the topology.
3. Assign IPs and configure static routes using `config.txt`.
4. Use `ping` or `show ip route` to verify connectivity.

---

## 📌 Notes

- Subnet `192.168.12.0/30` and `192.168.13.0/30` are used for point-to-point links.
- Static routing is ideal for small, predictable networks like this lab.
- You can expand this into a dynamic routing project using OSPF or EIGRP!

---


### 👨‍💻 Created with 💙 by Kaushalya Jayasekara

> *Feel free to fork, star ⭐ and contribute if you found this helpful!*
