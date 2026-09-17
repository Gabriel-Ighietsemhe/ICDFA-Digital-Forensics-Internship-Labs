# CIP-B105-CS2: Email Harassment Investigation (Wireshark and TShark Attribution)

## 📌 Repository Overview

This repository contains the comprehensive digital forensic investigation documentation, technical findings, and artifact registers for the **Email Harassment Case Study (CIP-B105-CS2)**. The investigation utilizes packet capture analysis (`Nitroba.pcap`), HTTP stream reconstruction, and class-roster correlation to attribute malicious network transmissions originating from a shared university dorm network to an individual suspect.

---

## 📁 Repository Directory Structure

```text
CIP-B105-CS2-REGNO/
├── README.md                                                          # Repository documentation and guide
├── report/
│   └── CIP-B105-CS2_C11-26-DFIT-17288-Gabriel_Ighietsemhe.pdf        # Final consolidated professional PDF forensic report[cite: 1]
└── exhibits/                                                          # Numbered screenshots and tool output logs[cite: 1]

```

---

## 🔍 Investigation Summary & Key Findings

* **Overcoming the Shared-IP Problem:** Initial analysis of victim Lily Tuckrige's complaint email header revealed an originating IP address belonging to a university residential dorm gateway, which alone could not isolate an individual. Analysis was successfully transitioned to the gateway uplink packet capture (`Nitroba.pcap`).


* **HTTP POST Reconstruction:** Dissecting outbound session streams targeting `willselfdestruct.com` (`69.25.94.22`) isolated HTTP `POST` requests containing text payloads matching the exact phrasing of the harassment complaint (*"you can't find us / and you can't hide from us / Stop teaching / Start running"*).


* **MAC Address Attribution:** Lower-layer Ethernet frame analysis linked the client IP (`192.168.15.4`) to a physical hardware MAC address (`00:17:f2:e2:c0:ce`) on the local segment.


* **Suspect Identification:** Inspecting session cookies and identity-bearing tokens tied to the MAC address, followed by cross-referencing against the Chemistry 109 class roster, positively identified the suspect as **Johnny Coach** (`jcoachj@gmail.com`).


* **Normalized UTC Timeline:**
* **Date Submitted (Form Post):** `2008-07-22 06:24:05 UTC`

* **Date Email Sent Successfully (Server Response):** `2008-07-22 07:24:45 UTC`




---

## 📖 Accessing the Full Report

You can read the complete, professionally structured 21-page forensic report—complete with full chain-of-custody worksheets, evidentiary figures, TShark/Wireshark filter parameters, and the formal appendix—by navigating to the [report directory](/report/CIP-B105-CS2_C11-26-DFIT-17288-Gabriel_Ighietsemhe.pdf).
