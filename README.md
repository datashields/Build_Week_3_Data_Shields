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

*Versione Italiana*

## Panoramica
Questo repository documenta l'analisi completa di campioni malware e traffico di rete all'interno di un ambiente controllato. Le operazioni riflettono i flussi di lavoro di un Security Operations Center (SOC), adottando un rigoroso approccio safe-by-design tramite l'utilizzo di macchine virtuali isolate e limitazioni allo scambio di dati per prevenire fughe di codice malevolo. L'obiettivo dell'archivio è mappare la superficie di attacco e documentare gli Indicatori di Compromissione (IoC).

## Aree Operative del SOC (Struttura Directory)

### 1. Threat Intelligence & Malware Analysis
Indagine sui vettori di compromissione e reverse engineering comportamentale:
* **Analisi Dinamica Scareware:** Valutazione di rogue security software che simula infezioni fittizie.
* **Infostealer Avanzati (Vidar/Lumma):** Tracciamento di infezioni multi-stadio che utilizzano il Process Hollowing (RegAsm.exe). 
* **Analisi Statica (Mydoom):** Ricostruzione della logica operativa del worm, meccanismi SMTP e tecniche di offuscamento (ROT13).

### 2. Network Security Monitoring (NSM) & Forensics
Intercettazione e dissezione dei flussi di rete:
* **Network Forensics:** Analisi PCAP per l'estrazione diretta di file eseguibili (es. W32.Nimda.Amm.exe).
* **Analisi Crittografica:** HTTP (in chiaro) vs HTTPS (cifratura TLSv1.3).
* **Classificazione del Traffico:** Standard della 5-tupla per regole di firewalling.
* **Rilevamento Esfiltrazioni:** Blind SQL Injection ed esfiltrazione dati occulta via DNS.

### 3. Incident Response & Phishing Remediation
Risposta agli incidenti e contenimento:
* **Credential Harvesting:** Campagne phishing (ConvertKit-Meta) e abuso OAuth.
* **Strategie di Bonifica:** Metodologie identity-centric e revoca token di sessione.
* **Bonifica Endpoint:** Rimozione manuale della persistenza (Registry di Windows).

### 4. System Hardening & Vulnerability Research
Validazione delle configurazioni e analisi delle vulnerabilità:
* **Architettura Linux:** Mount point, permessi (`chmod`), e link simbolici vs hard link.
* **Mappatura Servizi:** Correlazione porte/processi (`netstat`, `ps`).
* **Exploit Development (Teorico):** Cracking Buffer Overflow stack-based (fuzzing, EIP offset, JMP ESP).
