# PCAP Analysis Automation Lab with Security Onion  

## Overview  

This project sets up an **automated PCAP analysis lab** using **Security Onion** to analyze malware network traffic, detect threats, and generate reports and dashboards. By importing malware PCAP files into Security Onion, we leverage **Zeek, Suricata, and Kibana** to visualize network threats and enhance cybersecurity threat-hunting workflows.  

---

## Requirements  

### **1. System Requirements**  
- **Security Onion ISO** ([Download here](https://securityonion.net/))  
- **Virtualization Software**: VirtualBox / VMware  
- **Minimum Specs**:  
  - 8GB RAM (Recommended: 16GB)  
  - 2+ CPU Cores  
  - 50GB+ Storage  

---

## Installation & Configuration  

### **1. Install Security Onion**  
Follow the official Security Onion installation steps:  
- Download and install Security Onion in a **VM (Virtual Machine)**.  
- Allocate **at least 8GB RAM** and **2+ CPU cores** for smooth operation.  

---

### **2. Security Onion Setup**  
During setup, configure the following:  
- **Deployment Mode:** Select **Evaluation (Eval) Mode**.  
- **Network Configuration:** Choose **Direct (Not Proxy)**.  
- **IP Addressing:** Use **DHCP** (Static IP did not work in this setup).  

Once installed, access the **Security Onion web interface** via the URL provided during setup.  

---

### **3. Verify Security Onion is Running**  
1. Open the web console and check:  
   - **Alerts & Detections** in the Security Onion dashboard.  
   - Ensure services like **Zeek, Suricata, Kibana, and Elasticsearch** are running.  

---

### **4. Importing & Analyzing PCAP Files**  
To analyze malware network traffic, manually import **PCAP files** as follows:  

1. Open the **Security Onion terminal**.  
2. Download a **malware PCAP file**:  

   ```sh
   wget https://www.malware-traffic-analysis.net/2024/02/28/2019-02-28-Fallout-EK-from-HookAds-campaign.pcap.zip
   ```

3. Verify the download:  

   ```sh
   ll
   ```

4. Unzip the file:  

   ```sh
   unzip 2019-02-28-Fallout-EK-from-HookAds-campaign.pcap.zip
   ```

5. Verify extracted files:  

   ```sh
   ll
   ```

6. Import the **PCAP file into Security Onion** for analysis:  

   ```sh
   so-import-pcap 2019-02-28-Fallout-EK-from-HookAds-campaign.pcap
   ```

7. If permission issues occur, run with **sudo**:  

   ```sh
   sudo so-import-pcap 2019-02-28-Fallout-EK-from-HookAds-campaign.pcap
   ```

---

### **5. Generating Reports & Dashboards**  
Once the **PCAP file** is imported, Security Onion will generate:  
- **Threat detection alerts** in **Security Onion Console**.  
- **Dashboards in Kibana** for network traffic visualization.  
- **Security reports** detailing malicious activity.  

---

## Next Steps  

- Analyze alerts and **Zeek/Suricata logs** in the Security Onion Console.  
- Investigate network anomalies using **Kibana dashboards**.  
- Use **threat intelligence** sources to correlate findings.  

---

## References  

- **[Security Onion Documentation](https://docs.securityonion.net/)**  
- **[Malware Traffic Analysis](https://www.malware-traffic-analysis.net/)**  


