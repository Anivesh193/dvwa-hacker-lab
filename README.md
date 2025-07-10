# 🔐 DVWA Hacker Lab Project (Local SOC Simulation)

This project simulates a real-world attack and defense setup using:

- 🐳 DVWA (Damn Vulnerable Web Application) as the target
- 🐱 Kali Linux as the attacker machine
- 📦 Tools like Nikto, Nmap, and OWASP ZAP
- 🧠 Goal: Learn ethical hacking + basic SOC operations (vuln scanning, reporting)

---

## 🚀 Part 1 – Set Up DVWA + Kali Linux

👉 [Full Blog Guide](https://medium.com/@aniveshmohan/part-1-deploy-a-local-hacker-lab-using-dvwa-and-kali-linux-90289f30d645)

### What I Did:
- Installed **Docker** and used `docker-compose` to run DVWA on port `9090`
- Configured Kali Linux (VM) to act as an attacker
- Found host IP using `ipconfig`
- Accessed DVWA from Kali via `http://<host-ip>:9090`

---

## 🛡️ Part 2 – Scan DVWA with Nmap, Nikto & OWASP ZAP

👉 [Full Blog Guide](https://medium.com/@aniveshmohan/part-2-scanning-dvwa-using-nmap-nikto-owasp-zap-f40ab5563f42)

### Tools Used:
- **Nikto** for a quick web vulnerability scan
- **OWASP ZAP** (GUI scanner) to detect XSS, SQLi, CSRF, etc.
- **Nmap** to scan open ports, services, and web weaknesses

### Key Commands:

```bash
# Nikto scan
nikto -h http://<host-ip>:9090

# Nmap scan with service detection
nmap -sV -T4 -Pn <host-ip>

# Nmap web vuln scripts
nmap --script http-enum,http-vuln* -p 9090 <host-ip>

