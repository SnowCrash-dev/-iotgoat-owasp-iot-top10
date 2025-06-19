# -iotgoat-owasp-iot-top10

# 🔐 IoTGoat OWASP IoT Top 10 Exploitation

This project demonstrates real-world exploitation of the [OWASP IoT Top 10](https://owasp.org/www-project-internet-of-things/) vulnerabilities using the intentionally vulnerable [OWASP IoTGoat](https://owasp.org/www-project-iot-goat/) firmware. The assessment was performed using Kali Linux and virtual networking environments to simulate IoT pentesting techniques.

---

## 🧪 Project Goals

- Demonstrate attacks across the OWASP IoT Top 10
- Use real tools like `nmap`, `wireshark`, `tcpdump`, `ssh`, `telnet`, and bash scripting
- Practice identifying, exploiting, and analyzing insecure firmware and services

---

## 📊 Challenge Breakdown

Each challenge maps directly to a Top 10 vulnerability:

| Challenge | OWASP IoT Top 10 Item | Summary |
|----------|------------------------|---------|
| 4 | Lack of Secure Update Mechanism | Injected a cron job to wget & execute a malicious binary from a remote HTTP server |
| 5 | Use of Insecure or Outdated Components | Exploited outdated Dropbear SSH server supporting only deprecated `ssh-rsa` |
| 6 | Insufficient Privacy Protection | Captured HTTP login credentials in plaintext via Wireshark |
| 7 | Insecure Data Transfer & Storage | Found hardcoded emails, passwords in plain text; transmitted data over HTTP |
| 8 | Lack of Device Management | Cracked weak password hashes; no alerting or logging; no update enforcement |
| 9 | Insecure Default Settings | Telnet and a backdoor were enabled on boot; world-writable scripts led to privilege escalation |

---

## 🧠 Key Takeaways

> _"The most important thing I took away was the methodology."_

- Recognized the difference between **network**, **application**, and **configuration-level** attack surfaces.
- Practiced real-world tactics like:
  - Reconfiguring services
  - Reverse shell deployment
  - Script automation
  - Exploit chaining (e.g., cron job → remote shell → SSH)
- Emphasized the importance of **logging**, **access control**, and **secure-by-default** principles in embedded system design.

---

## 📂 Repo Contents

| File/Folder                  | Description |
|-----------------------------|-------------|
| `/screenshots/`             | Visuals of successful exploits (PCAPs, terminals) |
| `/iotgoat_findings.md`      | Full writeups of each challenge |
| `/bash_scripts/`            | Scripts used to automate device enumeration, reverse shell setup |
| `/traffic/`                 | Captured PCAP files showing credential leaks |
| `/hashes/`                  | Cracked or attempted password hashes |
| `README.md`                 | You're here :) |

---

## 🧰 Tools Used

- `nmap`, `wireshark`, `tcpdump`, `netstat`, `telnet`, `ssh`, `wget`
- `John the Ripper` with `rockyou.txt`
- Python `http.server`
- Bash for scripting and crontab injection
- VirtualBox with bridged networking

---

## 🌐 Connect

- HackerOne: [@snowcrash225](https://hackerone.com/skyblue225)
- GitHub: [`snowcrash-dev`](https://github.com/snowcrash-dev)
- Inspired by *Snow Crash* and a love for engineering secure systems.

---

## 💬 Want Help Using This?

Feel free to fork this repo or reach out if you're learning embedded security or want help replicating these attacks in your own test lab!
