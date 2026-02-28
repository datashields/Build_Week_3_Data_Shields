# SOC Operations & Cyber Defense Archive

*🇬🇧 English Version (Italian version below)*

## Overview
This repository documents the comprehensive analysis of malware samples and network traffic within a controlled environment. The operations mirror the workflows of a Security Operations Center (SOC), adopting a strict safe-by-design approach using isolated virtual machines and data-exchange restrictions to prevent malicious code leakage. The objective of this archive is to map the attack surface and document Indicators of Compromise (IoCs) to block future threats in enterprise contexts.

## SOC Operational Areas (Directory Structure)

### 1. Threat Intelligence & Malware Analysis
Investigation of compromise vectors and behavioral reverse engineering:
* **Scareware Dynamic Analysis:** Evaluation of rogue security software simulating fake infections to extort targets.
* **Advanced Infostealers (Vidar/Lumma):** Tracking multi-stage infections utilizing Process Hollowing to inject malicious code into legitimate Windows processes (RegAsm.exe). Identification of evasion techniques such as disk I/O saturation and Cloudflare infrastructure abuse.
* **Static Analysis (Mydoom):** Reconstruction of the worm's operational logic in a Flare VM environment, including mass propagation mechanisms via SMTP and string obfuscation techniques (ROT13).

### 2. Network Security Monitoring (NSM) & Forensics
Interception and dissection of network flows:
* **Network Forensics:** Analysis of PCAP captures to identify TCP sequences and directly extract malicious executables (e.g., W32.Nimda.Amm.exe) from application traffic.
* **Cryptographic Analysis (HTTP vs HTTPS):** Demonstration of plaintext credential exposure on insecure protocols versus data encapsulation via Transport Layer Security (TLSv1.3).
* **Traffic Classification:** Utilization of the 5-tuple standard (Source/Destination IP, Ports, Protocol) to isolate conversations and deploy firewalling rules (ACLs).
* **Exfiltration Detection:** Theoretical analysis of combined attacks using Blind SQL Injection and covert data exfiltration via DNS queries.

### 3. Incident Response & Phishing Remediation
Incident response and threat containment:
* **Credential Harvesting:** Analysis of advanced phishing campaigns (ConvertKit-Meta) exploiting dynamic redirection and OAuth protocol abuse.
* **Remediation Strategies:** Application of identity-centric methodologies to revoke compromised session tokens.
* **Endpoint Hardening:** Manual removal of persistence mechanisms in the Windows registry and elimination of malicious file systems.

### 4. System Hardening & Vulnerability Research
Configuration validation and vulnerability analysis:
* **Linux Architecture:** Exploration of mount points, rigorous permission management via `chmod`, and architectural differentiation between symbolic and hard links to prevent system instability.
* **Service Mapping:** Correlation between listening ports, protocols, and active processes (e.g., Nginx on port 80) utilizing system utilities (`netstat`, `ps`).
* **Exploit Development (Theoretical):** Systematic cracking of a stack-based Buffer Overflow vulnerability via fuzzing, precise offset identification (EIP), and execution flow routing toward a malicious shellcode (JMP ESP). 

---

*🇮🇹 Versione Italiana*

## Panoramica
Questo
