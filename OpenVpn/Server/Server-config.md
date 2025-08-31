# 🔐 OpenVPN Server Setup Guide (pfSense)

This guide explains how to set up an OpenVPN server on pfSense, with proper firewall rules and client verification.  
All screenshots are included to showcase the configuration process.

---

## 📌 Prerequisites
- A running **pfSense firewall/router** with administrative access.  
- Internet connectivity on the pfSense box.  
- Certificates generated for the VPN server and clients.  
- A plan for VPN network addressing (e.g., `10.8.0.0/24`).  

---

## 📝 Step 1: Create/Import Certificates
- Navigate to **System → Certificates → Certificates** in pfSense.  
- Either **create** a new certificate or **import** an existing one.  
- Make sure to generate both the **certificate** and **private key** for your VPN server.  

![Certificate Creation](https://github.com/keepwatch0n/cybersecurity-simulation-lab/blob/master/OpenVpn/Client/images/15.png)

---

## 📝 Step 2: Configure OpenVPN Server
- Go to **VPN → OpenVPN → Servers**.  
- Click **Add** to create a new OpenVPN server.  
- Set the parameters as follows:
  - **Protocol/Port:** UDP / 1194  
  - **Tunnel Network:** `10.8.0.0/24`  
  - **Mode:** Remote Access (SSL/TLS + User Auth)  
  - **Data Ciphers:** AES-256-GCM, AES-128-GCM, CHACHA20-POLY1305, AES-256-CBC  
  - **Digest:** SHA256  
  - **DH Params:** 2048 bits  

![OpenVPN Server Configuration](https://github.com/keepwatch0n/cybersecurity-simulation-lab/blob/master/OpenVpn/Client/images/14.png)

---

## 📝 Step 3: Configure Firewall Rules
- Navigate to **Firewall → Rules → OpenVPN**.  
- Create a new **pass rule** to allow traffic from the VPN subnet into the LAN.  
- Example:
  - **Source:** `10.8.0.0/24`  
  - **Destination:** LAN Subnets  
  - **Action:** Pass  

![Firewall Rule](https://github.com/keepwatch0n/cybersecurity-simulation-lab/blob/master/OpenVpn/Client/images/16.png)

---

## 📝 Step 4: Verify VPN Client Connection
- After setting up the server, connect a client using the exported `.ovpn` file.  
- Once connected, verify in **Status → OpenVPN**.  
- You should see the client’s **Common Name, Real Address, Virtual Address**, and connection details.  

![Client Connected](https://github.com/keepwatch0n/cybersecurity-simulation-lab/blob/master/OpenVpn/Client/images/13.png)

---

## 📝 Step 5: Export Client Configuration
- Use the **Client Export Utility** in pfSense (if installed) to generate client configuration files.  
- Distribute the `.ovpn` profile along with the necessary credentials to users.  

---

## ⚠️ Troubleshooting Tips
- Ensure certificates are valid and not expired.  
- Confirm firewall rules allow traffic from the VPN subnet.  
- Check the OpenVPN log (`Status → System Logs → OpenVPN`) if connection issues occur.  
- Verify that the **server and client are using matching ciphers and authentication methods**.  

---

✅ This documentation mirrors the **Client Setup Guide** but is tailored for the **server-side** setup.  
Both client and server guides can now live together in your repository for a **complete OpenVPN solution**.  
