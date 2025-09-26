# Setup-and-use-a-Firewall-on-Windows-Linux-

This project demonstrates foundational firewall management skills and an understanding of network traffic filtering using Windows Firewall. Instead of blocking a specific port (as originally intended), this walkthrough blocks a **specific program (Google Chrome)** using **inbound and outbound rules**, showcasing similar concepts of traffic control.

---

## 📚 Tasks & Table of Contents

1. [Open the firewall configuration tool](#1-open-firewall-configuration-tool)
2. [List current firewall rules](#2-list-current-firewall-rules)
3. [Block inbound and outbound traffic for Chrome](#3-block-inbound--outbound-traffic-for-chrome)
4. [Test the rule](#4-test-the-rule)
5. [Remove the test block rule](#5-remove-test-block-rule-to-restore-original-state)
6. [Summary of firewall traffic filtering](#-firewall-traffic-filtering-summary)
7. [License](#-license)

---

## 🛠️ Steps Performed

### 1. Open Firewall Configuration Tool
- Open **Windows Defender Firewall with Advanced Security** via Start Menu or Control Panel.

### 2. List Current Firewall Rules
- Navigate to **Inbound Rules** and **Outbound Rules** to view existing entries.
<img width="1193" alt="1" src="https://github.com/user-attachments/assets/4a6dc4c9-245d-4dcb-8ddb-2eb5c8571ecc" />

### 3. Block Inbound & Outbound Traffic for Chrome
- Go to **Inbound Rules > New Rule**.
- Select **Program**, then browse and select `chrome.exe`.
<img width="1243" alt="2" src="https://github.com/user-attachments/assets/815594e2-432f-4095-8548-84fc6742b4f9" />
- Choose **Block the connection**.
<img width="1260" alt="3" src="https://github.com/user-attachments/assets/d1b93dfb-f36e-4dff-9505-bed07a01800d" />
<img width="1251" alt="4" src="https://github.com/user-attachments/assets/d67f9ed3-ea93-4fd5-a524-609068b737d7" />
<img width="1238" alt="5" src="https://github.com/user-attachments/assets/77e6c22a-d38f-489c-881d-271f168cf140" />
<img width="1214" alt="6" src="https://github.com/user-attachments/assets/28e1bde9-25cc-4865-86fa-9c2ab26e7e9d" />
- Apply the rule to **Domain, Private, and Public** profiles.
- Name the rule (e.g., `ChromeIn`).
<img width="1214" alt="7" src="https://github.com/user-attachments/assets/db6d1090-ca3a-4de4-b4d8-e4370c665543" />
- Repeat the process in **Outbound Rules** to block outgoing connections.
<img width="1247" alt="8" src="https://github.com/user-attachments/assets/74b2baf2-4593-46e8-983e-088225f8fcaf" />

### 4. Test the Rule
- Open Google Chrome and try accessing a website.
- The connection should fail due to the rule blocking network traffic.
<img width="986" alt="9" src="https://github.com/user-attachments/assets/58510fba-395c-4c88-abe6-12f8fa208baa" />

### 5. Remove test block rule to restore original state.
- Go to the inbound and outbound rules and simply delete the rules you have created.
- And now, the program should gain access to the internet again


#### 🚫 Blocking a Specific Port (Example with Port 25 - Telnet)
*Same steps as above, but select "Port" instead of "Program" in the rule creation process.*
![Block Port 25 for SMTP]
<img width="1200" alt="10" src="https://github.com/user-attachments/assets/0c0b4e4b-005b-4541-99ed-cecd3906cd3b" />
<img width="1176" alt="11" src="https://github.com/user-attachments/assets/2ff91b2d-2a07-4b6a-8678-abc2b1ae7575" />


---

## 🧠 Firewall Traffic Filtering Summary
Firewalls act as a barrier between your computer and potential threats from the internet. They use **rules** to determine whether to **allow or block** incoming and outgoing traffic based on:

| Filter Criteria   | Description                                |
|-------------------|--------------------------------------------|
| Program Path      | Blocks or allows apps by their executable  |
| Port Number       | Filters traffic by specific TCP/UDP ports  |
| Protocol          | Applies rules to TCP, UDP, or both          |
| IP Addresses      | Controls traffic from/to specific IPs       |
| Network Profiles  | Applies to Domain, Private, or Public networks |
