# Cybersec-task1-nmap-scan

# Cyber Security Internship - Task 1: Scan Your Local Network for Open Ports

## 🧭 Objective
Discover open ports on devices in my local network using **Nmap** to understand network exposure and basic security risks.

---

## 🛠 Tools Used
- **Nmap** (network scanner)  
- **Wireshark** (optional — packet capture and analysis)  
- **Windows Command Prompt**

---

## 🔍 Environment Details
- **Scanned Network Range:** `10.30.67.0/24`  
- **My Host IP (sample):** `10.30.67.100`  
- **Subnet Mask:** `255.255.255.0`

---

## 📋 Step-by-Step Instructions

### 1. Check local IP configuration
Run in Command Prompt:
```bash
ipconfig


Identify the IPv4 address and subnet mask to determine the network range.

2. Run a TCP SYN scan with Nmap

Run:

nmap -sS 10.30.67.0/24


This performs a stealthy TCP SYN scan across the subnet and lists hosts with open ports.

3. Save scan results

To save results to a text file:

nmap -sS 10.30.67.0/24 -oN scan_results.txt


To save XML (for later conversion):

nmap -sS 10.30.67.0/24 -oX scan_results.xml

4. (Optional) Capture packets with Wireshark

Start Wireshark on your network interface.

Start capture and run the Nmap scan.

Use filter tcp.flags.syn == 1 to view SYN packets used in the scan.

🧾 Example Output (sample)
Nmap scan report for 10.30.67.1
PORT     STATE SERVICE
22/tcp   open  ssh
80/tcp   open  http
443/tcp  open  https

Nmap scan report for 10.30.67.100
PORT     STATE SERVICE
139/tcp  open  netbios-ssn
445/tcp  open  microsoft-ds

⚠️ Common Port Risks
Port	Service	Risk
22	SSH	Brute-force attacks if weak auth
21	FTP	Unencrypted credentials/data
80	HTTP	Vulnerable web apps/exposed services
139/445	SMB	Ransomware/unauthorized file access
3389	RDP	Remote desktop brute force/exploits
🔐 Recommended Mitigations

Close or disable unused services and ports.

Use a firewall to limit access by IP or network.

Use strong authentication (keys, MFA) and change default credentials.

Keep services patched and up to date.

Monitor logs and use IDS/IPS where possible.

📂 Repository Contents (what to include)

README.md ← this file

scan_results.txt ← saved Nmap output

ipconfig_screenshot.png ← screenshot of ipconfig output

nmap_scan_screenshot.png ← screenshot of the terminal showing the scan

(optional) wireshark_capture.pcap ← packet capture file

.gitignore (optional) to ignore large or sensitive files

🧾 Outcome

Gained practical experience performing basic network reconnaissance with Nmap.

Learned to identify open ports and understand associated risks.

Learned how to document and save scan results for reporting.

👨‍💻 Author

Name: Adarsh Singh
Task: Cyber Security Internship — Task 1
Network Range Scanned: 10.30.67.0/24
Date: October 2025



