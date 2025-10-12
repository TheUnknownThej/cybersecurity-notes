# Cybersecurity Incident Report – DDoS Attack Analysis  
**Incident:** Distributed Denial of Service (DDoS) via ICMP Flood  
**Date:** [12-10-2025]  
**Prepared by:** [Thejas K]  

---

## 🧩 Summary  
An organization recently experienced a **DDoS attack** that disrupted internal network operations for approximately two hours. During the incident, network services stopped responding due to an incoming flood of **ICMP packets**.  

The incident management team responded by:  
- Blocking incoming ICMP packets  
- Taking non-critical services offline  
- Restoring critical services  

After containment, the organization’s cybersecurity team investigated and identified that an **unconfigured firewall** allowed malicious ICMP traffic to flood the network.

---

## 🔍 NIST Cybersecurity Framework Application  

### **1. Identify**  
The investigation revealed that the attacker exploited a firewall misconfiguration, allowing an excessive number of ICMP echo requests (ping floods) to pass through. This caused network saturation, resulting in a **Distributed Denial of Service (DDoS)** condition.

---

### **2. Protect**  
To prevent similar incidents, the team implemented several network hardening measures:  
- Added **firewall rate limiting** for ICMP traffic  
- Enabled **source IP verification** to detect and drop spoofed packets  
- Deployed **network monitoring tools** to flag abnormal traffic spikes  
- Configured **IDS/IPS** to automatically filter and alert on suspicious ICMP activity  

---

### **3. Detect**  
Improved detection capabilities were introduced through:  
- Continuous **network traffic analysis** for anomaly detection  
- **Automated alerts** from the IDS/IPS system  
- **Log correlation** between firewalls and network devices to identify coordinated attack patterns  

---

### **4. Respond**  
During the incident, the following response actions were taken:  
- **Rate limiting**: Restricted the number of ICMP requests accepted within a given time frame  
- **Firewall adjustments**: Blocked all non-essential inbound ICMP traffic  
- **Communication**: Upper management was informed immediately; they initiated customer notifications and prepared legal reporting in accordance with data breach regulations  

---

### **5. Recover**  
The cybersecurity team restored data and services by:  
- Recovering affected systems from the **previous night’s full backup**  
- Performing **integrity checks** on network configurations  
- Conducting a **post-incident review** to strengthen policies and prevent recurrence  

---

## 🧠 Reflections / Notes  
- Firewall misconfigurations can act as open doors for network-based attacks.  
- ICMP flood attacks, while simple, can still cripple unprotected networks.  
- Proactive monitoring and strong rate limiting are crucial defenses.  
- Applying the **NIST Cybersecurity Framework** helps standardize the response and recovery process.  

---

**End of Report**
