# SIEM-Content
Zero Day Sigma rules for early detections

https://medium.com/@abdul.myid/detecting-malicious-zip-archive-decryption-via-event-5379-8af2c2194d47
https://medium.com/@abdul.myid/sigma-rule-unauthenticated-access-attempts-to-cisco-asa-ftd-webvpn-noise-reduced-f570f89f9403
https://medium.com/p/774630c1fc29

# 🛡️ Sigma Rules for Zero-Day & Emerging Threats  

This repository is a curated collection of Sigma detection rules focused on zero-day exploits, APT campaigns, and emerging threats.  
The goal is to provide actionable detections that defenders can quickly adapt into their SIEM environments for early visibility and response.  


## 📂 Repository Structure  

Each file is a Sigma rule (`.yml`) mapped to a specific **threat, campaign, or TTP**. Rules are named to reflect their focus for quick identification.  

### Current Rules  
- BRICKSTORM Campaign
  - `BRICKSTORM campaign.yml` – General detection for BRICKSTORM activity  
  - `BRICKSTORM Campaign Suspicious VM Clone or Snapshot Activity in vCenter.yml`  
  - `BRICKSTORM DoH Beaconing from Appliance Interfaces.yml`  

- VMware / vCenter
  - `New User Creation on vCenter ESXi (Persistence).yml`  
  - `SSH Service Enabled on VMware vSphere Appliance.yml`  

- Cisco ASA / FTD
  - `Unauthenticated Cisco ASA-FTD WebVPN Access Attempts (CVE-2025-20333 CVE-2025-20362) - Low Noise.yml`  

- Windows / General
  - `Suspicious ZIP Archive Decryption via Event 5379.yml`
 
- Citrix / NetScaler
  - `Citrix NetScaler - Multi-request suspicious memory overflow attempt with server errors (CVE-2025-7775).yml`

- RAT / CountLoader → Amatera/PureRAT
  - `Suspicious SVG attachments with embedded HTML/redirects.yml`
  - `CHM file execution (hh.exe) — possible follow-on stage.yml`
 
- RAT / Infostealer - Banking 
  - `Suspicious C2 Communication from Stealer/Banker.yml`

- F5 / K000154696: F5 Security Incident  
 - `F5 Detect config -archive download patterns.yml`
 - `F5 Detect iControl REST calls to Mgmt IP.yml`
 - `F5 HTTP POST with high-entropy - base64-encoded body to management endpoint.yml`
 - `F5 Suspicious tmsh or f5 CLI usage outside authorized admin times.yml`

  

---

## 🚀 Purpose  

- Provide practical detection logic for defenders tracking the latest campaigns.  
- Reduce time-to-detection for zero-days and emerging vulnerabilities.  
- Serve as a living repository: continuously updated as new threat intelligence emerges.  

---

## 🛠️ Usage  

1. Convert Sigma rules to your SIEM’s query language using [sigmac](https://github.com/SigmaHQ/sigma).  
2. Deploy in your detection pipeline.  
3. Tune for your environment (e.g., paths, domains, user roles).  

Example:  

sigmac -t splunk -c config/splunk-windows.yml rules/*.yml


⚠️ Disclaimer

These rules are provided as-is, with no guarantees.
They are intended to assist security teams in detection but may require environmental tuning to reduce false positives.

📌 Contributions

Contributions, improvements, and new Sigma rules for zero-day detection and emerging threats are welcome. Please submit via Pull Request.
