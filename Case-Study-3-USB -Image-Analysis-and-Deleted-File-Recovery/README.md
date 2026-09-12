CIP-B104-CS3: Rhino Hunting Digital Forensics Investigation
Case Identifier: CIP-B104-CS3-REGNO

Assessment: Case Study 2 — USB, Steganography and Network Evidence Investigation

Course: CIP-B104 Computer Forensics Case Study I (ICDFA)

📌 Repository Overview
This repository contains the structured investigative documentation, scripts, timelines, and audit registers compiled during the forensic examination of the Rhino Hunting Case. The investigation evaluates physical storage media (RHINOUSB.dd) alongside network capture streams (rhino.log, rhino2.log, rhino3.log) to uncover allocated, deleted, hidden, and transferred digital media assets, ultimately testing the scenario threshold regarding unique rhinoceros image possession.

📁 Repository Directory Structure
Plaintext
CIP-B104-CS3-REGNO/
├── README.md                          # Repository documentation and guide
├── report/
│   └── CIP-B104-CS3_REGNO_FULLNAME.pdf # Final consolidated professional PDF forensic report
├── evidence/
│   ├── hashes/                        # Cryptographic hash manifests (MD5 / SHA-256)
│   └── inventory/                     # Master provenance and deduplication tables
├── timelines/
│   └── integrated_timeline.csv        # Chronological Coordinated Universal Time (UTC) activity log
├── registers/
│   └── evidence_register.xlsx         # Evidence ID, source, pathway, extraction, and limitations matrix
└── exhibits/                          # Numbered screenshots 
🔬 Evidence Domains Covered
Evidence Preparation & Provenance Control: Secure ingestion, integrity verification, and write-blocking of primary assets (RHINOUSB.dd, rhino.log, rhino2.log, rhino3.log).

USB File System & Carving Analysis: Partitionless (superfloppy) FAT16 volume mapping, sector-0 anchoring, file-system traversal (fls, fsstat), and unallocated space carving via PhotoRec/Foremost.

Steganography Detection & Payload Extraction: Statistical analysis (stegdetect), dictionary password recovery (stegbreak with authorized case wordlist), and payload extraction (JPSeek).

FTP Traffic Forensics: Session reconstruction, command-response mapping (USER, PASS, RETR, STOR), file export (rhino1.jpg, rhino3.jpg), and encrypted archive recovery (contraband.zip extraction via fcrackzip).

HTTP & Executable Traffic Analysis: Stream dissection of web traffic (rhino2.log) yielding rhino4.jpg and rhino5.gif, alongside non-destructive static analysis of the transferred binary in rhino3.log.

Master Deduplication & Final Opinion: Hash normalization, elimination of redundancy, integrated UTC timeline reconstruction, attribution limitation assessment, and final threshold evaluation.

🛠️ Tools & Environment
All examinations were performed inside a controlled, isolated laboratory environment utilizing open-source and industry-standard forensic utilities:

The Sleuth Kit (TSK) / Autopsy: Volume layout inspection and file-system traversal.

PhotoRec / Foremost: Deleted file carving from unallocated space.

Stegdetect / Stegbreak / JPSeek: Detection and extraction of steganographic payloads.

Wireshark / NetworkMiner: Network stream reconstruction and packet dissection.

Fcrackzip / OpenSSL: Archive cracking and cryptographic integrity verification (md5sum, sha256sum).

📊 Summary of Deliverables Included in Submission
Professional PDF Report: Structured precisely to ICDFA guidelines (11 core sections spanning legal authority, technical findings, timelines, and final forensic opinions).

Hash Manifest: Complete SHA-256 and MD5 records for all original evidence files and derived artifacts.

Integrated Timeline: Normalized Coordinated Universal Time (UTC) activity ledger.

Master Provenance Register: Comprehensive tracking table linking every object from source evidence to extracted file and hash group.

Exhibits: Logged tool outputs and numbered screenshots referenced directly from the formal report.

Disclaimer: This repository contains historical training evidence created for the International Cybersecurity & Digital Forensics Academy (ICDFA). All recovered artifacts remain contained strictly within authorized educational parameters.
