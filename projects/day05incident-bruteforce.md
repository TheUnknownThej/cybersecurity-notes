# Cybersecurity Incident Report  
**Incident:** Brute Force Attack on Administrator Account  
**Date:** [12-10-2025]  
**Prepared by:** [Thejas K]  

---

## 1. Network Protocols Involved  
- **HTTP** — Used for web login requests and file downloads.  
- **DNS** — Used for domain name resolution during website access.  

These protocols were observed during the attacker’s activity and the corresponding log analysis.

---

## 2. Incident Description  

Several customers reported that visiting `yummyrecipesforme.com` prompted them to download a file claiming to provide free recipes. After running the file, their computers experienced performance issues.  

The website owner was locked out of the administrator account. A cybersecurity analyst used a sandbox environment and tcpdump to capture network traffic:  

- Initial access to the website was normal over HTTP.  
- After executing the downloaded file, the browser redirected to a fake website `greatrecipesforme.com`.  
- The logs indicated a sudden change in network traffic to the new IP address.  

Further investigation revealed that the attacker had likely used a **brute force attack** to gain access to the administrator account, allowing them to modify the website and inject malicious code. Execution of the file compromised end-user machines.

---

## 3. Impact Assessment  

- **Confidentiality:** High — administrator account compromised, user data at risk.  
- **Integrity:** Moderate — website content was altered by the attacker.  
- **Availability:** Moderate — users were temporarily unable to access the website.  

---

## 4. Recommended Remediations  

1. **Disallow previous/default passwords** — prevents attackers from exploiting default credentials.  
2. **Enforce frequent password changes** — reduces risk if a password is exposed.  
3. **Implement two-factor authentication (2FA)** — requires both a password and a one-time passcode to log in, preventing unauthorized access.  
4. **Monitor login attempts** — use alerts for repeated failed logins to detect brute force attacks early.  
5. **Educate users** — warn about downloading files from untrusted sources to prevent malware execution.  

---

**End of Report**
