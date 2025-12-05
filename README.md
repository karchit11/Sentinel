🛡️ WebSentinel: HTTP Traffic Attack Analysis

WebSentinel is an automated Intrusion Detection System (IDS) dashboard designed to analyze HTTP traffic logs in real-time. It solves the challenge of manual log inspection by automatically detecting, classifying, and visualizing malicious URL patterns.

🚀 The Problem

Modern organizations face massive volumes of web traffic logs. Security teams struggle to manually inspect these logs to distinguish between:

Harmless traffic

Failed attack attempts (e.g., a firewall blocking an XSS attack)

Successful breaches (e.g., an SQL injection that returned sensitive data)

💡 The Solution

WebSentinel acts as a "Robot Security Guard." It parses web logs and uses signature-based detection (Regex) to identify specific attack patterns. It then visualizes this data in a modern React dashboard, allowing security analysts to filter threats by type, severity, and outcome.

✨ Key Features

Attack Detection: Automatically flags SQL Injection (SQLi), Cross-Site Scripting (XSS), Directory Traversal, and Command Injection.

Outcome Classification:

🔴 Critical/Success: Detects potential data leaks (e.g., HTTP 200 responses with large payloads during an attack).

🟡 Attempt: Identifies attacks blocked by the server (e.g., HTTP 403/401).

Real-Time Dashboard: A responsive UI to monitor traffic trends and attack velocity.

Search & Filter: deeply analyze logs by IP address, timestamp, or attack category.

🛠️ Tech Stack

Frontend: React, TypeScript, Vite

Styling: Tailwind CSS, Lucide React (Icons)

Runtime: Node.js

🔍 How It Works

The system analyzes the request URL and query parameters against a database of known attack signatures:

Attack Type

Detection Logic (Simplified)

SQL Injection

UNION SELECT, ' OR 1=1, --, DROP TABLE

XSS

<script>, javascript:, onerror=, onload=

Path Traversal

../, ..\, /etc/passwd, boot.ini

🔮 Future Roadmap

PCAP Ingestion: Support for parsing raw .pcap network files using PyShark/Scapy.

AI Anomaly Detection: Implementing ML models to detect unknown "Zero-day" attacks.

Export Reports: Ability to export threat reports as PDF/CSV for compliance.
