# Cybersecurity Incident Report  
**Incident:** SYN Flood Attack  
**Date:** [12-10-2025]  
**Prepared by:** [Thejas K]  

---

## 1. Summary  
Website experienced repeated connection timeouts.  
Log analysis indicates a **Denial of Service (DoS)** attack using **SYN flooding** from a single external IP source.

---

## 2. Incident Identification  

**Type of Attack:** DoS – SYN Flood  
**Symptoms Observed:**  
- Website displayed “connection timeout” errors.  
- Legitimate users and employees experienced service unavailability.  
- Logs showed large numbers of SYN packets with no follow-up ACKs.  

**Probable Cause:**  
An attacker sent excessive TCP SYN requests to overwhelm the server’s ability to process new connections.

---

## 3. Attack Explanation  

### Normal TCP Handshake  
1. **SYN:** Client requests to start a connection.  
2. **SYN-ACK:** Server acknowledges the request.  
3. **ACK:** Client confirms and completes connection.  

### During SYN Flood  
- The attacker repeatedly sends SYN packets but never replies with the final ACK.  
- The server keeps waiting, filling up its connection table.  
- Legitimate connection requests are dropped, causing timeout messages.

---

## 4. Log Analysis  

| Timestamp | Source IP | Destination | Protocol | Observation |
|------------|------------|--------------|------------|--------------|
| 2025-10-11 10:04:x | 203.x.113.x | webserver.local | TCP (SYN) | Multiple repeated SYN requests |
| 2025-10-11 10:05:x | Internal Employees | webserver.local | TCP | Normal connection attempts failing |

**Interpretation:**  
The single-source IP repeatedly sent SYN requests without completing the handshake, overwhelming the system.

---

## 5. Impact Assessment  
- **Availability:** High impact — users unable to access the site.  
- **Integrity:** No signs of data alteration.  
- **Confidentiality:** No sensitive data exposure observed.  
- **Reputation:** Moderate risk if service outages persist.  

---

## 6. Recommendations  

**Immediate Actions:**  
- Block or rate-limit traffic from the malicious IP.  
- Restart web services once load stabilizes.  

**Preventive Measures:**  
- Implement SYN cookies or connection rate limiting on the firewall.  
- Deploy an Intrusion Detection/Prevention System (IDS/IPS).  
- Monitor for abnormal traffic spikes using a SIEM dashboard.  
- Configure alerts for failed or incomplete TCP handshakes.  

---

**End of Report**
