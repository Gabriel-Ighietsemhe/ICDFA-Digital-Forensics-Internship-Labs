# CIP-B104-CS3: Rhino Hunting Digital Forensics Investigation

**Case Identifier:** `CIP-B104-CS3-17288`

**Assessment:** Case Study 3 — USB Image Analysis and Deleted File-Recovery

**Course:** CIP-B104 Computer Forensics Case Study I (ICDFA)

**Analyst:** Gabriel Ighietsemhe (`C11/26/DFIT/17288`)

**Date:** 12th September 2026

---

## 📌 Repository Overview

This repository contains the digital forensic investigation documentation, technical findings, and evidentiary records for the **Rhino Hunting Case Study (CIP-B104-CS3)**. The examination evaluates a physical storage media image (`RHINOUSB.dd`) alongside network capture logs (`rhino.log`, `rhino2.log`, `rhino3.log`) to identify allocated, unallocated, carved, and transferred media assets, testing the scenario threshold regarding the possession of nine or more unique rhinoceros images.

---

## 📁 Repository Directory Structure

```text
CIP-B104-CS3-17288/
├── README.md                                                          # Repository documentation and overview
├── report/
│   └── CIP-B104-CS3_C11-26-DFIT-17288-Gabriel_Ighietsemhe.pdf        # Consolidated 23-page professional PDF forensic report[cite: 5]
└── screenshots/                                                          # Evidentiary screenshots and tool output logs[cite: 5]

```

---

## 🔬 Evidence Ingestion & Cryptographic Verification

All primary evidence files were write-protected upon ingestion, and cryptographic MD5 integrity baselines were verified against case manifests:

| Evidence Description | Filename | Size | Calculated MD5 Hash |
| --- | --- | --- | --- |
| **Seized USB Image**<br> | `RHINOUSB.dd`<br> | 260 MB | `80348c58eec4c328ef1f7709adc56a54`<br>

 | `c0d0093eb1664cd7b73f3a5225ae3f30`<br> |
| **Network Capture Log 1 (FTP)**<br> | `rhino.log`<br> | 3.2 MB

 | `cd21eaf4acfb50f71ffff857d7968341`<br> |
| **Network Capture Log 2 (HTTP)**<br> | `rhino2.log`<br> | 293 KB

 | `7e29f9d67346df25faaf18efcd95fc30`<br> |
| **Network Capture Log 3 (Static Binary)**<br> | `rhino3.log`<br> | 226 KB


---

## 🔍 Key Technical Findings

* **FAT16 File System & Volume Mapping:** Analysis (`fdisk -l`, `fls -o 0`) identified a partitionless (superfloppy) FAT16 architecture anchored directly at sector offset 0.


* **File Carving from Unallocated Space:** Carving via PhotoRec recovered four distinct rhinoceros images from unallocated clusters where metadata had been unlinked. Accompanying artifacts linked the storage media to the local user account `Kamryn`.


* **FTP Stream Reconstruction (`rhino.log`):** Dissection of cleartext FTP sessions exposed user credentials (`gnome` / `gnome123`), recovered downloaded image assets (`rhino1.jpg`, `rhino3.jpg`), and identified an uploaded container (`contraband.zip`).


* **Encrypted Archive Password Recovery:** Using `fcrackzip` paired with the approved dictionary wordlist, the password for `contraband.zip` was cracked as `pw monkey`. Extraction yielded `rhino2.jpg`, confirming cross-source duplication with USB evidence.


* **HTTP Object Extraction (`rhino2.log`):** Dissection of web transaction streams isolated server responses containing binary image payloads, successfully extracting `rhino4.jpg` and `rhino5.gif`.


* **Static Binary Evaluation (`rhino3.log`):** Non-destructive static string and header analysis was performed on the transferred executable binary without dynamic host execution.


* **Deduplication & Final Forensic Opinion:** Cross-domain correlation across the physical USB image, carved clusters, FTP streams, encrypted ZIP containers, and HTTP logs confirmed that the deduplicated count of unique rhinoceros images successfully meets the case threshold criteria.



---

## 🛠️ Tools & Utilities Used

* **The Sleuth Kit (TSK) / PhotoRec:** Partition mapping, file listing (`fls`), and unallocated space file carving.


* **Wireshark:** Network packet dissection, TCP stream following, and protocol analysis.


* **fcrackzip / ImageMagick:** Archive password recovery and image asset verification.


* **OpenSSL / md5sum:** Cryptographic hash generation, verification, and deduplication.



---

## 📖 Accessing the Full Report

The full, 23-page formal forensic report—including chain-of-custody worksheets, step-by-step terminal outputs, the normalized UTC timeline, and numbered evidentiary exhibits—is available in the [report directory](./report/CIP-B104-CS3_C11-26-DFIT-17288-Gabriel_Ighietsemhe.pdf).

---

Disclaimer: This repository contains historical training evidence created for the International Cybersecurity & Digital Forensics Academy (ICDFA). All recovered artifacts remain contained strictly within authorized educational parameters.
