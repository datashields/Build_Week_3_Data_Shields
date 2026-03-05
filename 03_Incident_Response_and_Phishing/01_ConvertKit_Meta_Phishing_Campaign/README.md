# 🎣 Threat Intel Report: ConvertKit-Meta Phishing Campaign

*Choose Language: [🇬🇧 English](#english) | [🇮🇹 Italiano](#italiano)*

---

<h2 id="english">🇬🇧 English</h2>

### 1. Executive Summary
Analysis of an advanced credential harvesting campaign that abuses the legitimate **ConvertKit** email marketing infrastructure to spoof **Meta (Facebook/Instagram)** security alerts. By leveraging the high reputation of ConvertKit's sending IPs, the threat actors successfully bypass standard Secure Email Gateways (SEG) and SPF/DKIM checks to deliver malicious payloads directly to user inboxes.

### 2. MITRE ATT&CK® Mapping
* **Initial Access:** `T1566.002` - Phishing: Spearphishing Link (Delivery via ConvertKit).
* **Credential Access:** `T1056.002` - GUI Input Capture (Fake Meta login portal to harvest credentials).
* **Defense Evasion:** `T1564` - Hide Artifacts (Abuse of legitimate SaaS platforms to mask the malicious origin).
* **Credential Access:** `T1550.001` - Application Access Token (Potential theft of OAuth tokens post-authentication).

### 3. Attack Flow & Infrastructure
1. **Delivery:** The attacker creates a free/compromised account on ConvertKit to send emails that technically pass SPF/DKIM alignment because they originate from ConvertKit's authorized servers.
2. **Lure:** The email mimics a critical Meta security alert (e.g., "Suspicious login attempt").
3. **Exploitation:** The embedded link redirects the victim to a highly convincing, attacker-controlled credential harvesting portal.
4. **Action on Objectives:** Harvested credentials and session tokens are exfiltrated to the attacker's database.

### 4. Attached Documentation
* Full Incident Response report in PDF format.
* Extracted Indicators of Compromise (`ioc_phishing.csv`).
* OSINT Infrastructure Mapping (`osint_infrastructure.md`).

---

<h2 id="italiano">🇮🇹 Italiano</h2>

### 1. Executive Summary
Analisi di una campagna avanzata di credential harvesting che abusa dell'infrastruttura legittima di email marketing **ConvertKit** per impersonare avvisi di sicurezza di **Meta (Facebook/Instagram)**. Sfruttando l'alta reputazione degli IP di invio di ConvertKit, gli attaccanti riescono a bypassare i controlli SPF/DKIM e i classici Secure Email Gateway (SEG).

### 2. Mappatura MITRE ATT&CK®
* **Initial Access:** `T1566.002` - Phishing: Spearphishing Link (Invio tramite ConvertKit).
* **Credential Access:** `T1056.002` - GUI Input Capture (Finto portale di login Meta per il furto di credenziali).
* **Defense Evasion:** `T1564` - Hide Artifacts (Abuso di piattaforme SaaS legittime per mascherare l'origine).
* **Credential Access:** `T1550.001` - Application Access Token (Potenziale furto di token OAuth).

### 3. Flusso di Attacco & Infrastruttura
1. **Delivery:** L'attaccante utilizza un account ConvertKit per inviare email che superano tecnicamente i controlli SPF/DKIM, poiché originate dai server autorizzati della piattaforma.
2. **Lure:** L'email simula un avviso di sicurezza critico di Meta (es. "Tentativo di accesso sospetto").
3. **Exploitation:** Il link reindirizza la vittima verso un portale di credential harvesting controllato dall'attaccante.
4. **Action on Objectives:** Le credenziali e i token di sessione inseriti vengono esfiltrati verso il database dell'attaccante.

### 4. Documentazione Allegata
* Report di Incident Response completo in formato PDF.
* Indicatori di Compromissione estratti (`ioc_phishing.csv`).
* Mappatura OSINT dell'infrastruttura (`osint_infrastructure.md`).
