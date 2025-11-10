# Nessus Home Lab Scan

## Summary
I used Nessus on Windows 11 to scan my home lab (Win11 host, Win10 VM, Kali VM) to find and fix vulnerabilities.

## Setup
- **Host:** Windows 11 (Nessus at https://localhost:8834)
- **VMs:** Windows 10, Kali Linux
- **Tools:** Nessus, VMware

## Steps
1. Installed Nessus on Win11 and ran a scan called “my home”.
2. Scanned all three systems.
3. Exported CSV report, took screenshots, and reviewed results.
4. Prioritized issues using CVSS score and color (Critical > High > Medium > Low).

---

## Findings & Fixes

### Windows 11
- **SMB Signing not required:** Enable “Digitally sign communications (always)”.  
- **Untrusted SSL Certificate:** Replace with a valid CA-signed certificate.

### Windows 10
- **Weak SSL Ciphers (SWEET32):** Disable 3DES and enable TLS 1.2/1.3 with AES or ChaCha20.  
- **Self-Signed/Untrusted Certs:** Use trusted SSL certificates.

### Kali Linux
- **Old OpenSSH (<10.0):** Upgrade to version 10.0 or later.  
- **ICMP Timestamp Disclosure:** Block ICMP type 13/14.  
- **SMB Signing not required:** Enforce SMB signing.

---

## Notes
- Saved CSV report and screenshots in order from 1 to 14.
- Matched each finding with its fix for clarity.  
- Will re-scan after remediation to confirm fixes.

