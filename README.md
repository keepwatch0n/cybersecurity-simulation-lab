#### 🏢 Enterprise Security Simulation Lab
📌 Overview

This project simulates a real-world enterprise security infrastructure, combining both offensive (Red Team) and defensive (Blue Team) operations. It provides a practical environment for learning firewall configuration, IDS/IPS tuning, vulnerability exploitation, monitoring, log analysis, VPN security, DNS filtering, and email protection.

The lab was built as part of my CDAC journey, fully deployed under Oracle VirtualBox, using a mix of Linux (Debian 12 Bookworm, Kali Linux) and Windows 11 machines.

🎯 Objectives

Simulate cyber attacks using Kali Linux Red Team tools.

Detect and prevent intrusions with pfSense + Snort.

Aggregate and analyze logs with the ELK Stack.

Monitor systems with Nagios.

Secure communications via TLS, OpenVPN.

Enhance email security.

🏗️ Project Architecture
🔒 Firewall & Segmentation

pfSense with WAN, LAN, and DMZ network segmentation

Configured firewall rules for controlled communication

Integrated Snort IDS/IPS for intrusion detection & prevention

🌐 DMZ Services

Debian 12 Server hosting Apache + DVWA (with TLS enabled) for vulnerability assessment

⚔️ Red Team (Offense)

Kali Linux Attacker using tools:

Nmap, Burp Suite, SQLmap, Metasploit, LinPEAS

Simulated attacks: Reconnaissance, SQL Injection, XSS, privilege escalation, persistence

🛡️ Blue Team (Defense)

Nagios for service uptime & host monitoring

ELK Stack (Elasticsearch, Logstash, Kibana) with Filebeat for centralized log collection & dashboards

Snort rules tuned for attack detection

Real-time email alerts from triggered logs

🔑 Secure Remote Access

OpenVPN integrated with pfSense for secure authenticated client connections

🌍 Additional Hardening

Bastion Host for SSH access control


🚀 Features Implemented

✅ pfSense firewall with Snort IDS/IPS integration
✅ DVWA in DMZ for attack simulations
✅ Blue Team monitoring with Nagios & ELK Stack
✅ OpenVPN for secure client connectivity
✅ Email security
✅ Red Team vs Blue Team practical simulations
✅ HTTPS enabled with self-signed certificate

📊 Learning Outcomes

Built and defended enterprise-grade security infrastructure

Hands-on Red Team (Attack) & Blue Team (Defense) operations

Applied log monitoring & SIEM techniques with ELK

Implemented network hardening (TLS, VPN, Email Security)

Practical experience with incident detection, analysis, and response

🔮 Future Scope

Add Wazuh for host-based intrusion detection

Integrate malware sandboxing (Cuckoo)

Expand to cloud environments (AWS/Azure)

Explore container security with Docker + Falco

✅ Conclusion

This Enterprise Security Simulation Lab demonstrates a full-scale cybersecurity simulation with both offensive and defensive strategies, closely aligned with industry practices. It serves as a strong foundation for hands-on learning, career preparation, and advanced cybersecurity research.
