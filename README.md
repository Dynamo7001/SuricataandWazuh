
# 🛡️ EDR Basics: Detecting Suspicious Network Traffic
 
📅 Date: August 5, 2025  
🔗 [Project Link](https://github.com/0xrajneesh/30-Days-SOC-Challenge-Beginner/blob/main/Challenge%236/Day%2329%3A%20EDR%20Basics%3A%20Detecting%20Suspicious%20Network%20Traffic.md)

---

## 🧠 Objective
To detect and analyze **suspicious network traffic** using **Suricata IDS** and **Wazuh SIEM**, with a focus on port scans and malicious patterns.

---

## 🧪 Lab Setup

| Component         | Configuration                          |
|------------------|----------------------------------------|
| Attacker Machine | Kali Linux VM (`Kali-Hammed`)          |
| Defender Machine | Ubuntu VM with Wazuh agent (`Ubuntu-N`)|
| IDS              | Suricata (logs to `/var/log/suricata/eve.json`) |
| SIEM             | Wazuh manager                          |
| Hypervisor       | VMware Workstation                     |

---

## 🔍 Activities Performed

### 1. **Nmap Scanning (on Kali-Hammed)**
Executed several Nmap scans against `192.168.36.135` (Ubuntu-N):

``bash
nmap -sS -T4 192.168.36.135

## 🔍 Activities Performed

### 1. **Nmap Scanning**
Detected open ports:
- `22/tcp` (SSH)

Aggressive scans triggered multiple Suricata alerts.

---

### 2. **Suricata Detection**
Suricata generated multiple alerts such as:

- `ET SCAN Suspicious inbound to PostgreSQL port 5432`
- `ET SCAN Potential VNC Scan 5800-5820`
- `ET SCAN Suspicious inbound to MSSQL port 1433`
- `ET POLICY Possible Kali Linux hostname in DHCP Request Packet`

---

### 3. **Wazuh Integration**
Wazuh ingested Suricata logs and displayed alerts via its **Threat Hunting** dashboard.

📸 **Screenshots:**
<img width="1920" height="1080" alt="suri 1" src="https://github.com/user-attachments/assets/28b6f5cb-417c-451c-91f3-6364d4c2f9ad" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/bd156ca5-94ab-4b43-b529-e9705b91d591" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/94eaf5de-e6df-483d-9fa9-42dfb39669a3" />


<img width="1920" height="1080" alt="Suri2" src="https://github.com/user-attachments/assets/d1303814-5874-44d0-95ca-671fc6d10570" />

<img width="1920" height="1080" alt="Suri 3" src="https://github.com/user-attachments/assets/039d9c86-8d38-4f50-9067-33d5112bf1e1" />

<img width="1920" height="1080" alt="Suri 4" src="https://github.com/user-attachments/assets/1e09e6e9-03e5-4d74-b91a-ae071c6bff4e" />

---

## 📈 Observations

- IDS properly detected all scan attempts across major database ports.
- Wazuh provided real-time visibility of events.
- DHCP alert confirmed system identification attempt by Kali box.

---

## 🧰 Tools Used

- 🧪 **Suricata IDS**
- 🛡️ **Wazuh SIEM**
- 📡 **Nmap**
- 💻 **VMware Workstation**

---

## 🧠 Key Takeaways

- Port scanning is easily detectable with properly configured IDS rules.
- Suricata + Wazuh integration gives visibility into low-level network events.
- EDR and SIEM platforms are critical for **real-time intrusion detection** and **forensics**.

---

## 📌 Author

**Hammed Oluwole**  
🔗 [LinkedIn](https://www.linkedin.com/in/hammed-oluwole-194756a0/)  
📅 August 5, 2025

