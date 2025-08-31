# 🛡️ DMZ Web Server Setup (DVWA on Apache)

## 📌 Overview
This guide documents the setup of a **DMZ Web Server** hosting the **Damn Vulnerable Web Application (DVWA)**.  
The DMZ is designed to isolate publicly accessible services from the internal LAN, providing **network segmentation and layered security**.  

DVWA is intentionally vulnerable and is used here for **penetration testing, vulnerability assessment, and SOC training**.

---

## ⚙️ Step 1: HTTPS Certificate Configuration

The DMZ web server is secured using an **SSL/TLS certificate** issued by the internal **SecurityLab Root CA**.  

* CN (Common Name): `192.168.20.100`  
* Organization: `SecurityLab`  
* OU: `DMZ Web Server`  
* Issued By: `SecurityLab Root CA`  

![Certificate Configuration](https://github.com/keepwatch0n/cybersecurity-simulation-lab/blob/master/OpenVpn/Client/images/Certificate_HTTPS.png)

---

## ⚙️ Step 2: DVWA Login Page

The DVWA web interface is accessible over HTTPS via:  



https://192.168.20.100/DVWA/login.php



Users can authenticate with their assigned credentials.  

![DVWA Login Page](https://github.com/keepwatch0n/cybersecurity-simulation-lab/blob/master/OpenVpn/Client/images/DMZ_Login_page.png)

---

## ⚙️ Step 3: Security Level Configuration

DVWA allows changing its **security level** to simulate different vulnerability exposures:  

- **Low** → Fully vulnerable, no security controls.  
- **Medium** → Basic protections, still insecure.  
- **High** → Stricter protections, limited vulnerabilities.  
- **Impossible** → Fully patched, secure mode.  

![DVWA Security Settings](https://github.com/keepwatch0n/cybersecurity-simulation-lab/blob/master/OpenVpn/Client/images/DVWA%20Security%20Page.png).

---

## ⚙️ Step 4: DVWA Application Dashboard

Upon successful login, the DVWA dashboard provides access to multiple **vulnerability testing modules**, including:  

- SQL Injection  
- XSS (Reflected, Stored, DOM)  
- Command Injection  
- File Upload  
- CSRF  
- Weak Session IDs  

![DVWA Dashboard](https://github.com/keepwatch0n/cybersecurity-simulation-lab/blob/master/OpenVpn/Client/images/Successful%20login%20dashboard.png).

---

## ⚙️ Step 5: Web Server & Database Configuration

The DVWA setup is running on an **Apache Web Server** with the following environment:  

* **Server Name:** 192.168.20.100  
* **PHP Version:** 8.2.29  
* **Database Backend:** MySQL/MariaDB  
* **Database User:** `aditya`  
* **Database Name:** `dvwa`  
* **Database Port:** `3306`  

![DVWA Environment Setup](https://github.com/keepwatch0n/cybersecurity-simulation-lab/blob/master/OpenVpn/Client/images/This%20setup%20check%20page.png).

---

## 🛡️ Security Notes

* The DVWA server is intentionally vulnerable and must **only be deployed in isolated lab environments**.  
* Ensure **pfSense firewall rules** restrict access to the DMZ.  
* Use **IDS/IPS tools (Snort/Suricata)** for monitoring attacks on the DVWA server.  
* Rotate SSL/TLS certificates periodically.  

---

## ✅ Summary

This DMZ setup provides a **realistic environment** for:  
- Practicing web application attacks.  
- Testing SOC detection & response.  
- Demonstrating how segmentation and monitoring protect internal assets from exposed services.

---
