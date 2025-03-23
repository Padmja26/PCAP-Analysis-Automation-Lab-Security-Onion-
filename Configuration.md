# PCAP Analysis Automation Lab with Security Onion  

## Overview  

This project sets up an **automated PCAP (Packet Capture) analysis lab** using **Security Onion**, a free and open-source Linux distribution for threat hunting, network security monitoring (NSM), and log management. The primary goal is to analyze malware network traffic, detect threats, and generate insightful security reports and dashboards. By importing malware PCAP files into Security Onion, we leverage powerful tools such as **Zeek, Suricata, and Kibana** to visualize network threats, improve forensic investigations, and enhance cybersecurity threat-hunting workflows.  

---

## Requirements  

### **1. System Requirements**  
To set up the lab, ensure your system meets the following requirements:  

- **Security Onion ISO** ([Download here](https://securityonion.net/))  
- **Virtualization Software**: VirtualBox / VMware  
- **Minimum Hardware Specifications**:  
  - **RAM**: 8GB (Recommended: 16GB for better performance)  
  - **CPU Cores**: At least 2 (Recommended: 4 for larger PCAP files)  
  - **Storage**: Minimum of 50GB free space (Recommended: 100GB+)  
  
**Note**: Running Security Onion inside a virtual machine is recommended to isolate analysis from the host operating system.  

---

## Installation & Configuration  

### **1. Installing Security Onion**  
Security Onion installation involves setting up a virtual machine and configuring the operating system for network monitoring. Follow these steps:  

1. Download the **Security Onion ISO** from the official website.  
2. Create a new **virtual machine** in VirtualBox or VMware.  
3. Allocate **at least 8GB RAM** and **2+ CPU cores** to the VM.  
4. Assign at least **50GB of disk space** for logs and analysis data.  
5. Attach the Security Onion ISO to the VM and boot from it.  
6. Follow the on-screen instructions to install the OS.  

After installation, reboot the VM and proceed to configuration.  

---

### **2. Configuring Security Onion**  
During the initial setup, you'll be prompted to configure the system. Choose the following settings:  

- **Deployment Mode:** Select **Evaluation (Eval) Mode** for easy setup and testing.  
- **Network Configuration:** Choose **Direct (Not Proxy)**.  
- **IP Addressing:** Select **DHCP** (Static IP may require manual network setup). 

Once configured, you can access the **Security Onion web interface** using the provided URL. This interface allows you to view security alerts, dashboards, and logs.  

![Screenshot from 2025-03-22 19-31-07](https://github.com/user-attachments/assets/0930d974-086e-4d69-9b4f-ac7e9835271e)

---

### **3. Verifying Security Onion is Running**  
Before proceeding, ensure that Security Onion is running properly by checking the following:  

1. Log in to the Security Onion web interface.  
2. Navigate to the **Dashboard** and check for:  
   - **Alerts & Detections** displayed from Suricata and Zeek.  
   - **Log analysis** from various sensors.  
3. Verify that core services such as **Zeek, Suricata, Kibana, and Elasticsearch** are active.
4. To check use the command
    ```sh
    sudo so-status
    ```
    ![VirtualBox_SecurityOnion_23_03_2025_15_17_03](https://github.com/user-attachments/assets/f1dbd2c4-8615-4c60-9c74-4ec18b81dafb)


---

### **4. Importing & Analyzing PCAP Files**  
PCAP files contain recorded network traffic and are used to investigate cyber threats. To analyze a malware PCAP file in Security Onion, follow these steps:  

1. Open the **Security Onion terminal** within the virtual machine.  
2. Download a **sample malware PCAP file** from a trusted source such as **Malware Traffic Analysis**:  

   ```sh
   wget https://www.malware-traffic-analysis.net/2024/02/28/2019-02-28-Fallout-EK-from-HookAds-campaign.pcap.zip
   ```

3. Verify the downloaded file:  

   ```sh
   ls -lh
   ```

4. Unzip the PCAP file:  

   ```sh
   unzip 2019-02-28-Fallout-EK-from-HookAds-campaign.pcap.zip
   ```

5. Check the extracted files:  

   ```sh
   ls -lh
   ```

6. Import the PCAP file into Security Onion for analysis:  

   ```sh
   so-import-pcap 2019-02-28-Fallout-EK-from-HookAds-campaign.pcap
   ```

7. If you encounter permission issues, try running with **sudo**:  

   ```sh
   sudo so-import-pcap 2019-02-28-Fallout-EK-from-HookAds-campaign.pcap
   ```

Once imported, Security Onion will process the traffic and generate alerts.  

---

### **5. Generating Reports & Dashboards**  
After importing a PCAP file, Security Onion automatically processes the data and provides valuable insights through various dashboards. You can access:  

- **Security Onion Console** for real-time threat alerts.  
- **Kibana dashboards** to visualize network activity and detect anomalies.  
- **Zeek logs** for detailed traffic analysis and protocol-level information.  
- **Suricata alerts** indicating potential security threats and intrusion attempts.

  **Dashboard Example**
  ![Screenshot from 2025-03-22 19-32-29](https://github.com/user-attachments/assets/0e1209dd-1fc4-410c-8001-3c8ef20567d6)
  ![Screenshot from 2025-03-22 19-32-26](https://github.com/user-attachments/assets/6899f052-7ad3-475e-a7c3-27630f4679f5)
  ![Screenshot from 2025-03-22 19-32-32](https://github.com/user-attachments/assets/7f1c27a5-17a5-4d57-b891-359b0bd6fdfe)

  **Kibana Report Example**

We can aldo create diffrent cases in order to indentify certain alerts more efficiently.

Using these tools, analysts can correlate threats, identify suspicious patterns, and take appropriate action.  

---

## Next Steps  

To further analyze and investigate network threats, consider the following:  

- Review **Zeek and Suricata logs** for specific indicators of compromise (IoCs).  
- Investigate alerts and security events in **Security Onion Console**.  
- Use **Kibana** to filter and analyze network connections.  
- Integrate external **threat intelligence feeds** to enhance detection capabilities.  

This setup enables proactive threat hunting and network forensic investigations.  

---

## References  

For more information and detailed documentation, refer to:  

- **[Security Onion Documentation](https://docs.securityonion.net/)** – Official Security Onion guide.  
- **[Malware Traffic Analysis](https://www.malware-traffic-analysis.net/)** – A great resource for PCAP files and network traffic analysis.  

---



