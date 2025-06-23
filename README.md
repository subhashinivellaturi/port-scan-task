# Cybersecurity Internship Task - Port Scanning

## 🎯 Objective
To scan the local network for open ports using Nmap and analyze network exposure. Optionally capture packet-level activity using Wireshark.

---

## 🛠 Tools Used
- Nmap (Network scanning)
- Wireshark (Packet analysis)
- Kali Linux

---

## 📡 Network Scanned
- Local IP: 10.10.78.109 (Kali Linux)
- Subnet Scanned: 10.10.78.0/24

---

## 🔍 Nmap Command Used
```bash
sudo nmap -sS 10.10.78.0/24 -oN port_scan_results.txt

Scan Results Summary

---
### IP Found with Open Ports:

**10.10.78.130**
- 22/tcp - ssh
- 80/tcp - http
- 443/tcp - https
- 8080/tcp - http-proxy
- 8443/tcp - https-alt
- 10000/tcp - snet-sensor-mgmt

**10.10.78.109** (Kali Linux)
- All 1000 scanned ports are closed

Security Risk Analysis
Port	       Risk	                 Mitigation
22	         SSH brute-force	     Use SSH keys, fail2ban, restrict IPs
80	         Unencrypted HTTP	     Redirect to HTTPS
443	         SSL/TLS risks	       Keep certificates updated
8080 / 8443	 Admin interfaces	     Strong auth, IP restriction
10000	       Webmin exposure	     Disable unused services, update frequently

Wireshark Analysis
Wireshark was used to capture packets during scanning.
Display Filter Used:
tcp.flags.syn == 1 && tcp.flags.ack == 0

