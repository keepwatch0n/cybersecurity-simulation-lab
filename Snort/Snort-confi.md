# 🛡️ Snort IDS/IPS Setup on pfSense

## Step 1: Install Snort Package on pfSense

Log in to the pfSense WebGUI.

Navigate to System → Package Manager → Available Packages.

Search for Snort and click Install.

Once installed, you will see Services → Snort in the navigation bar.

## Step 2: Create a Snort Interface

Go to Services → Snort → Interfaces.

Click Add and choose the interface where you want IDS/IPS inspection (e.g., DMZ, LAN).

Configure:

Interface: DMZ (or WAN/LAN depending on your use case).

Enable: Checked.

IPS Mode: Optionally enable inline IPS if desired.

Block Offenders: Enabled (for IPS).

![Snort Installed](https://github.com/keepwatch0n/cybersecurity-simulation-lab/blob/master/OpenVpn/Client/images/Screenshot%202025-08-11%20144544.png) 

## Step 3: Configure Snort Global Settings

Go to Services → Snort → Global Settings.

Configure rule download sources (Snort VRT, Emerging Threats, etc.).

Enter your Oinkcode (if using Snort.org rules).

Save and update rules.

## Step 4: Add Custom Snort Rules (DMZ Alerts)

Go to Services → Snort → Rules on the DMZ interface.

Create a custom rule inside local.rules. Example:

alert icmp any any -> any any (msg:"ICMP Ping Detected"; sid:1000001; rev:1;)


This rule will trigger alerts whenever ICMP packets (ping) are detected in the DMZ.

![Snort Installed](https://github.com/keepwatch0n/cybersecurity-simulation-lab/blob/master/OpenVpn/Client/images/Screenshot%202025-08-11%20144609.png)


## Step 5: View Snort Alerts

Navigate to Services → Snort → Alerts.

Select the interface (e.g., DMZ).

You should now see triggered alerts such as ICMP detection logs.

![Snort Installed](https://github.com/keepwatch0n/cybersecurity-simulation-lab/blob/master/OpenVpn/Client/images/Screenshot%202025-08-11%20144511.png)


✅ Summary

Installed Snort on pfSense.

Configured Snort interfaces (e.g., DMZ,LAN).

Applied alert rules.

Verified results in Services → Snort → Alerts.

Snort is now running as an IDS/IPS on pfSense, monitoring and generating alerts based on your configured rules.
