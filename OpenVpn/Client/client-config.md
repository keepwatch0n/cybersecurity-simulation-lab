# OpenVPN Client Setup Guide (Windows)

## Prerequisites

- A Windows client machine (Windows 10 or 11 recommended).
- OpenVPN client setup files exported from the pfSense OpenVPN server.
- Your OpenVPN client username and password.

---

## Step 1: Install OpenVPN Client on Windows

- Download the OpenVPN Client for Windows from the official OpenVPN website or the link provided by your administrator.  
  ![OpenVPN Client Download](https://github.com/keepwatch0n/cybersecurity-simulation-lab/blob/master/OpenVpn/Client/images/Client_Side.png)

- Run the OpenVPN installer `.exe` file.
- Follow the installation wizard’s instructions and complete the installation.  
  ![OpenVPN Installation](https://github.com/keepwatch0n/cybersecurity-simulation-lab/blob/master/OpenVpn/Client/images/Installation_Done.png)

- Once installed, you should see the OpenVPN Client icon in your system tray (bottom-right corner of your screen).  
  ![OpenVPN Client Icon](https://github.com/keepwatch0n/cybersecurity-simulation-lab/blob/master/OpenVpn/Client/images/4.png)

---

## Step 2: Import OpenVPN Configuration File

- Obtain the OpenVPN client configuration file (usually `.ovpn`) exported from your pfSense OpenVPN server.
- Open the OpenVPN Client application.
- Click **Import** and select the `.ovpn` configuration file.
- The profile will be added to your OpenVPN Client.

---

## Step 3: Connect to the VPN

- Locate the OpenVPN Client icon in the taskbar/system tray area.
- Right-click on it and select the connection profile you imported.
- Click **Connect**.
- When prompted, enter your **username** and **password** provided for VPN access.  
  ![OpenVPN Login](https://github.com/keepwatch0n/cybersecurity-simulation-lab/blob/master/OpenVpn/Client/images/5.png)
  
- After successful authentication, the OpenVPN client will connect, and the icon will turn **green** indicating an active VPN session.  
  ![OpenVPN Connected](https://github.com/keepwatch0n/cybersecurity-simulation-lab/blob/master/OpenVpn/Client/images/1.png)

---

## Step 4: Verify VPN Connection

- Open the Command Prompt (`cmd`).
- Run the command to check your IP address:  

![IP Configuration](https://github.com/keepwatch0n/cybersecurity-simulation-lab/blob/master/OpenVpn/Client/images/11.png)

- You should see an IP address assigned from the VPN network (matching your pfSense LAN subnet).
- Test connectivity by pinging your project LAN:  

![Ping Test](https://github.com/keepwatch0n/cybersecurity-simulation-lab/blob/master/OpenVpn/Client/images/10.png)

---

## Troubleshooting Tips

- Make sure the `.ovpn` file was imported correctly.
- Verify your username and password.
- Check firewall or antivirus settings that may block VPN connections.
- Restart the OpenVPN Client if connection problems arise.

---
