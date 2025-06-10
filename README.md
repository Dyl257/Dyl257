# Vulnerability Scanning Lab (Azure + Tenable)

Hands‐on demo of running unauthenticated vs. authenticated scans against a Linux VM.  
Includes step‐by‐step setup: VM provisioning, agent group creation, scan configuration, triggering, and reviewing results.

---

## 🛠️ Steps & Screenshots

### 1. VM Provisioning  
![VM Overview](./images/VMcreation.PNG)  
*Azure Portal showing `linux-scan-agent-dylan` VM details (Size, OS, IP).*

### 2. Create Agent Group  
![Agent Groups](./images/agentgroupcreation.PNG)  
*“Linux-agent-group-Dylan” created under **Sensors → Agent Groups**.*

### 3. Install & Link Agent  
![Install Command](./images/Install_Command.PNG)  
*`curl -H 'X-Key: …' 'https://sensor.cloud.tenable/install/agent?...' | bash`*  
![Successful Agent Install](./images/Successful_Agent_Install.PNG)  
*Terminal output showing “INSTALL PASSED” and auto-configuration complete.*

### 4. Verify Agent Online  
![Agent in Portal](docs/projects/vuln-scan/agent based/Agent Appearing in Portal.PNG)  
*Agent status “Online” with IP, Platform, and “Linked on” timestamp.*

### 5. Configure & Trigger Scan  
![Create a Scan](./images/createscan.PNG)  
*“Basic Agent Scan” configured to use `Linux-agent-group-Dylan` with a Triggered Scan on filename `dishsoap.lol`.*  
![Trigger File Creation](./images/Trigger_File_Creation.PNG)  
*On VM: `touch /opt/nessus_agent/var/nessus/triggers/dishsoap.lol`.*

### 6. View Scan Results  
![Scan Results](./images/Scan_Results.PNG)  
*Final report showing critical, high, medium and low vulnerabilities under “Vulns by Plugin.”*

---

## 🔗 Links

- 👉 [Live demo video (YouTube)](https://youtu.be/Vn_L0xCZq7M?si=85hbWY88JREd2cCz)  
- 👉 [Project source on GitHub](https://github.com/Dyl257/Dyl257/tree/Vulnerability)

---

## 🧰 Tech Stack

- **Platform:** Azure Linux VM (Ubuntu 16.04)  
- **Scanner:** Tenable.io Agents & Nessus  
- **Scripting:** Bash (curl installer + trigger)  
