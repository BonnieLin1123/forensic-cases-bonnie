# Case 01 – Valdoria Times Incident

**Investigator:** Bonnie Lin  
**Completion Date:** August 2025  
**Tools Used:** KQL, Email/Event Logs, Passive DNS, Network/Process/File Event Analysis  

---

## 📌 Case Overview
This case simulates a targeted phishing and insider threat scenario against the *Valdoria Times*.
My objective was to trace suspicious employee activity, identify malicious files, and catch phishing emails to find potential security loopholes.

---

## 🔍 Investigation Steps

### 1. Employee & Email Analysis
- Queried employees by role and name to identify potential targets.  
- Traced malicious recruitment emails (e.g., *newspaper_jobs@gmail.com*, *valdorias_best_recruiter@gmail.com*) to specific recipients.  
- Confirmed delivery of fraudulent offer letters in `.docx` attachments.  

### 2. Network & DNS Activity
- Identified suspicious outbound traffic from internal IPs (`10.10.0.22`, `10.10.0.19`).  
- Detected domains with recruitment themes (e.g., `promotionrecruit.com`, `jobhire.org`).  
- Correlated passive DNS results to uncover infrastructure overlap.  

### 3. File & Process Forensics
- Tracked creation of malicious documents (e.g., `Editorial_Offer_Letter.docx`, `Editorial_J0b_Openings_2024.docx`).  
- Observed execution of PowerShell payloads (`hacktivist_manifesto.ps1`).  
- Detected persistence/command-and-control attempts via `plink.exe`.  

### 4. Insider Correlation
- Linked activity back to specific employees (`Sonia Gose`, `Ronnie McLovin`).  
- Tracked compromised credentials and IPs to confirm insider involvement.  

---

## 📑 Key Findings
- Multiple employees received phishing emails masquerading as job offers.  
- Attachments were used as initial access vectors.  
- Execution of PowerShell scripts and `plink.exe` indicated post-exploitation persistence.  
- At least two employees were leveraged as insider footholds.  

---

## 🛡️ Lessons Learned
- Employee awareness training could have prevented credential exposure.  
- Email filtering and DNS monitoring must be strengthened.  
- Forensic logging of process creation was critical in detecting purposes.  

---

✅ This case demonstrates my skills in identifying threats, validating evidence, and building a clear investigative narrative. 
It reflects the methodology I would apply in real-world digital forensics investigations.
