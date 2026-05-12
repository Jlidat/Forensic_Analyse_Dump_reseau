<p align="center">

<img src="https://img.shields.io/badge/Forensics-Network-blue">
<img src="https://img.shields.io/badge/Tool-Wireshark-orange">
<img src="https://img.shields.io/badge/Traffic-PCAPNG-green">
<img src="https://img.shields.io/badge/Language-Markdown-lightgrey">
<img src="https://img.shields.io/badge/Course-CNAM%20Menaces informatiques et codes malveillants-red">

</p>

> [!NOTE]
> This project was conducted for educational purposes as part of CNAM.

> [!WARNING]
> The original PCAP file is not publicly available.

> [!TIP]
> Screenshots are provided to illustrate the forensic methodology.

# Network Forensic Investigation (PCAP Analysis)
## Objective

    This project presents a pedagogical network forensic investigation performed on a PCAPNG capture file as part of the CNAM course Computer threats and malicious code.

    The objective of this work is to apply digital forensics and network traffic analysis techniques in order to:

    - identify hosts and network communications,
    - analyze the protocols used,
    - study user activity,
    - extract transferred files,
    - and detect suspicious or malicious behavior.

    Due to confidentiality and academic integrity constraints, the original capture file is not publicly available.

### Instead, this repository provides: 
    - A step-by-step investigation methodology
    - Visual evidence (Wireshark captures)
    - Technical analysis and interpretation
    - A professional forensic report

## Data Availability

    The original PCAPNG file is not published for confidentiality and academic integrity reasons.

    This project focuses on:
    - Reproducible analysis methodology
    - Observations derived from traffic inspection
    - Evidence-based reasoning (screenshots + explanations)

## Investigation Approach

    The analysis follows a structured forensic methodology inspired by real-world incident response :   
    - Environment Mapping : Identify hosts, IP addresses, and operating systems.    
    - Protocol Analysis : Examine network protocols and detect anomalies.
    - User Activity Analysis : Investigate web browsing, authentication, and downloads.
    - File Extraction & Analysis : Extract transferred files and compute hashes.
    - Attack Detection : Identify suspicious behaviors such as brute-force attempts.

## Repository Structure

```text
01_environment_mapping.md
02_protocols_analysis.md
03_user_activities.md
04_file_extraction.md
05_attack_detection.md
06_timeline_and_conclusion.md
captures/
README.md
```

## Key Findings
    . Multiple private IP addresses identified within a LAN environment
    . Presence of several clear-text protocols (HTTP, FTP, DNS)
    . User authentication observed in clear text (credential exposure)  
    . Download of a compressed archive file
    . File successfully extracted and hashed (SHA256) 
    . Detection of a brute-force attack attempt
    . Identification of attacker MAC address and tool (via User-Agent)

## Results 
### User Activity Highlights
    -> Web authentication detected over http:
        > Username
        > Password
    -> Browsing activity revealed multiple page visits
    -> Suspicious file download observe
    -> User-Agent analysis used to distinguish:
        - user browsing activity,
        - system activity,
        - and service discovery traffic
    

### File Analysis
    --> Extracted file via network traffic reconstruction
    --> File type: compressed archive (e.g., .zip / .7z)
    --> Hash calculated:
    --> SHA256 fingerprint used for identification
    --> File content inspected after extraction

### Detected Attack
    --> FTP brute-force attack identified
    --> Multiple authentication attempts observed
    --> Successful authentication detected after repeated failures
    --> File exfiltration performed after compromise
    --> Attacker activity correlated through network behavior and protocol analysis

### Indicators of Compromise (IOC)
    --> Suspicious authentication behavior
    --> Repeated FTP login failures
    --> Use of weak credentials
    --> Clear-text credential exposure
    --> Extracted file hashes
    --> Suspicious internal communications
### Attack Scenario (Reconstructed)
    1. User activity observed on a web application
    2. Credentials transmitted over unencrypted HTTP
    3. Download of a compressed archive file
    4. FTP brute-force attack performed against a local server
    5. Successful authentication obtained
    6. File exfiltration conducted through FTP
### Limitations
1. No access to host-based logs
2. Partial visibility on encrypted traffic
3. Analysis limited to network-level data

## Tools Used
- Wireshark
- tcpdump (optional)
- Hash utilities (sha256sum, md5sum)
- 7-Zip / unzip

## Report
    A detailed forensic report is available in:
    /report/forensic_report.pdf

## Skills Demonstrated
    + Network traffic analysis
    + Digital forensics methodology
    + Threat detection and investigation
    + Protocol analysis
    + Evidence-based reasoning
    + Security incident reconstruction
## Author
    Cybersecurity engineering student
    Specialization: Systems, Networks & Security

- - 

## Analysis Workflow
1. Environment Mapping → 01_environment_mapping.md
2. Protocol Analysis → 02_protocol_analysis.md
3. User Activity → 03_user_activity.md
4. File Extraction → 04_file_extraction.md
5. Attack Detection → 05_attack_detection.md
6. Timeline & Conclusion → 06_timeline_and_conclusion.md

## Structure of Each Analysis File
1. Objective
2. Méthode
3. Résultat
4. Evidence
5. Interpretation