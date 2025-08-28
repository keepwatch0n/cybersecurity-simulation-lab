## 🛡️ Enterprise Security Simulation Lab

This project is a hands-on Enterprise Security Simulation Lab built during my CDAC journey, designed to replicate real-world cybersecurity environments.
It includes network defense (Blue Team) and attack simulations (Red Team) with monitoring, detection, and reporting.

🏗️ Project Architecture

Firewall & Network Segmentation

pfSense configured with WAN, LAN, and DMZ zones

Rules applied to control network traffic between internal, external, and DMZ networks

DMZ Services

Linux Server (Apache) hosting DVWA (Damn Vulnerable Web Application) for penetration testing and exploitation

Intrusion Detection & Prevention

Snort IDS/IPS integrated with pfSense for detecting malicious traffic and attacks

Blue Team Monitoring

Nagios for service and host availability monitoring

ELK Stack (Elasticsearch, Logstash, Kibana) for log analysis and visualization of attack patterns

Red Team Attack Simulation

External attacker machine configured to exploit DVWA vulnerabilities

Testing of IDS/IPS alerts, firewall rules, and monitoring system responses

Secure Remote Access

OpenVPN integrated with pfSense for encrypted and authenticated remote access into the lab
