<p align="center">
  <img src="https://images.contentstack.io/v3/assets/bltefdd0b53724fa2ce/blt601c406b0b5af740/620577381692951393fdf8d6/elastic-logo-cluster.svg" alt="Elastic Logo" width="300">
</p>

<h1 align="center">🔍 Elastic SIEM Home Lab</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Elastic-SIEM-005571?style=flat&logo=elastic" alt="Elastic">
  <img src="https://img.shields.io/badge/Kali_Linux-VM-557C94?style=flat&logo=kalilinux" alt="Kali Linux">
  <img src="https://img.shields.io/badge/Nmap-Security_Scanner-4682B4?style=flat&logo=nmap" alt="Nmap">
  <img src="https://img.shields.io/badge/Kibana-Dashboard-E8478B?style=flat&logo=kibana" alt="Kibana">
  <img src="https://img.shields.io/badge/status-active-success.svg" alt="Status">
</p>

<p align="center">
  <i>A hands-on guide to building a Security Information and Event Management (SIEM) home lab using Elastic Stack and Kali Linux for security monitoring and incident response.</i>
</p>

---

## 🎯 Project Aim

> **"The difference between a security breach and a security incident is detection time."**

In today's threat landscape, organizations need to detect and respond to security incidents in **minutes, not months**. This project aims to:

🔬 **Provide hands-on experience** with enterprise-grade SIEM technology used by Fortune 500 companies

🛡️ **Build practical skills** in security monitoring, log analysis, and incident detection

📊 **Master visualization techniques** to identify patterns and anomalies in security data

⚡ **Create real-time alerting** systems that notify you the moment threats are detected

🎓 **Enhance your resume** with a portfolio-worthy project that demonstrates SOC analyst capabilities

Whether you're an aspiring security analyst, a penetration tester, or an IT professional looking to level up your security skills — this lab will give you the practical experience that employers are looking for.

---

## 📑 Table of Contents

- [🔍 Overview](#-overview)
- [✨ Key Features](#-key-features)
- [🏗️ Architecture](#️-architecture)
- [🚀 Quick Start](#-quick-start)
- [💡 Lab Tasks](#-lab-tasks)
- [📊 Creating Dashboards](#-creating-dashboards)
- [🔔 Setting Up Alerts](#-setting-up-alerts)
- [📁 Project Structure](#-project-structure)
- [🗺️ Roadmap](#️-roadmap)
- [🤝 Contributing](#-contributing)
- [📞 Contact & Support](#-contact--support)

---

## 🔍 Overview

This project provides a comprehensive guide to setting up a **home lab for Elastic Stack SIEM** using the Elastic Cloud portal and a Kali Linux virtual machine. You'll learn how to collect security events, forward them to a centralized SIEM, and perform real-world security analysis.

> ### 💡 Why Build a SIEM Home Lab?
> 
> Security Operations Centers (SOCs) rely heavily on SIEM systems for threat detection and incident response. By building your own lab, you'll:
> - Understand how security events flow from endpoints to SIEM
> - Learn to write queries that detect malicious activity
> - Practice creating dashboards used by real SOC analysts
> - Gain experience with alerting mechanisms for threat detection

---

## ✨ Key Features

### 🔐 Elastic SIEM Capabilities
- 📥 **Centralized Log Collection** — Aggregate logs from multiple sources
- 🔎 **Powerful Search Engine** — Query millions of events in milliseconds
- 📈 **Real-time Analysis** — Detect threats as they happen
- 🎨 **Kibana Visualizations** — Create stunning security dashboards
- 🚨 **Custom Alerting** — Get notified when threats are detected

### 🐧 Kali Linux Integration
- 🛠️ **Pre-installed Security Tools** — Nmap, Metasploit, and more
- 📡 **Elastic Agent Deployment** — Seamless log forwarding
- 🔄 **Event Generation** — Create realistic security scenarios
- 🖥️ **Virtualization Support** — Works with VirtualBox & VMware

### 📊 Analytics & Monitoring
- 📉 **Event Timeline** — Track security events over time
- 🗺️ **Network Mapping** — Visualize scanned hosts and services
- 📋 **Query Builder** — Filter logs with precision
- 📑 **Custom Reports** — Export findings for documentation

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                           ELASTIC CLOUD PLATFORM                            │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                         ELASTICSEARCH CLUSTER                         │  │
│  │                                                                       │  │
│  │   ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐      │  │
│  │   │   Data Nodes    │  │  Master Nodes   │  │  Ingest Nodes   │      │  │
│  │   │  (Log Storage)  │  │  (Coordination) │  │  (Processing)   │      │  │
│  │   └─────────────────┘  └─────────────────┘  └─────────────────┘      │  │
│  │                                                                       │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                     │                                       │
│                                     ▼                                       │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                              KIBANA                                   │  │
│  │   ┌──────────────┐  ┌──────────────┐  ┌──────────────┐               │  │
│  │   │  Dashboards  │  │    SIEM     │  │    Alerts    │               │  │
│  │   │              │  │   Console    │  │   Manager    │               │  │
│  │   └──────────────┘  └──────────────┘  └──────────────┘               │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
                                      ▲
                                      │ HTTPS (Encrypted)
                                      │
┌─────────────────────────────────────────────────────────────────────────────┐
│                            LOCAL ENVIRONMENT                                │
│                                                                             │
│   ┌─────────────────────────────────────────────────────────────────────┐   │
│   │                    VIRTUALIZATION PLATFORM                          │   │
│   │                   (VirtualBox / VMware)                             │   │
│   │  ┌───────────────────────────────────────────────────────────────┐  │   │
│   │  │                      KALI LINUX VM                            │  │   │
│   │  │                                                               │  │   │
│   │  │   ┌─────────────┐    ┌─────────────┐    ┌─────────────┐      │  │   │
│   │  │   │   Elastic   │    │    Nmap     │    │  Security   │      │  │   │
│   │  │   │   Agent     │    │  Scanner    │    │   Events    │      │  │   │
│   │  │   │ (Collector) │    │  (Testing)  │    │ (Generated) │      │  │   │
│   │  │   └──────┬──────┘    └─────────────┘    └─────────────┘      │  │   │
│   │  │          │                                                    │  │   │
│   │  │          └──────────── Forwards Logs ─────────────────────►   │  │   │
│   │  └───────────────────────────────────────────────────────────────┘  │   │
│   └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 🚀 Quick Start

### Prerequisites

| Requirement | Description |
|-------------|-------------|
| 💻 **Virtualization Software** | VirtualBox or VMware |
| 🐧 **Kali Linux VM** | Download from [kali.org](https://www.kali.org/get-kali/#kali-virtual-machines) |
| ☁️ **Elastic Cloud Account** | Free trial at [cloud.elastic.co](https://cloud.elastic.co/registration) |
| 🌐 **Internet Connection** | Required for Elastic Cloud communication |
| 🧠 **Basic Linux Knowledge** | Command line familiarity |

### Installation Steps

**1️⃣ Set Up Elastic Cloud Account**
```bash
# Navigate to Elastic Cloud
https://cloud.elastic.co/registration

# Create a deployment
- Click "Create Deployment"
- Select "Elasticsearch" as deployment type
- Choose your region
- Click "Create Deployment"
```

**2️⃣ Set Up Kali Linux VM**
```bash
# Download Kali Linux VM
https://www.kali.org/get-kali/#kali-virtual-machines

# Default credentials
Username: kali
Password: kali
```

**3️⃣ Install Elastic Agent on Kali**
```bash
# Navigate to Integrations in Elastic Cloud
# Search for "Elastic Defend"
# Copy the Linux installation command

# Paste and run in Kali terminal
curl -L -O https://artifacts.elastic.co/downloads/beats/elastic-agent/...
sudo ./elastic-agent install ...

# Verify installation
sudo systemctl status elastic-agent.service
```

---

## 💡 Lab Tasks

### Task 1: Generate Security Events with Nmap

```bash
# Basic scan of local machine
sudo nmap <vm-ip>

# SYN scan (stealth scan)
sudo nmap -sS <target-ip>

# TCP connect scan
sudo nmap -sT <target-ip>

# Full port scan
sudo nmap -p- <target-ip>

# Aggressive scan with OS detection
sudo nmap -A <target-ip>
```

### Task 2: Query Security Events in SIEM

```kql
# Search for Nmap scan events
event.action: "nmap_scan"

# Search for sudo commands
process.args: "sudo"

# Search for authentication failures
event.action: "authentication_failure"

# Search for SSH login attempts
event.category: "authentication" AND process.name: "sshd"
```

### Task 3: Analyze Results

| Event Type | What It Indicates | Severity |
|------------|-------------------|----------|
| `nmap_scan` | Network reconnaissance | Medium |
| `authentication_failure` | Brute force attempt | High |
| `privilege_escalation` | Sudo usage | Medium |
| `ssh_login` | Remote access | Low-High |

---

## 📊 Creating Dashboards

### Security Events Over Time

1. Navigate to **Analytics** → **Dashboards**
2. Click **Create Dashboard**
3. Add **Visualization** → Select **Area** or **Line**
4. Configure:
   - **Metrics**: Count
   - **Horizontal Axis**: Timestamp
   - **Breakdown**: event.action

### Sample Dashboard Widgets

| Widget | Visualization Type | Purpose |
|--------|-------------------|---------|
| Event Timeline | Area Chart | Track events over time |
| Top Event Types | Pie Chart | Identify common events |
| Source IPs | Data Table | List event sources |
| Alert Status | Metric | Show active alerts |

---

## 🔔 Setting Up Alerts

### Create Nmap Detection Rule

```yaml
Rule Name: Nmap Scan Detection
Rule Type: Custom Query
Query: event.action: "nmap_scan"
Severity: Medium
Schedule: Every 5 minutes
Actions:
  - Email notification
  - Slack message
  - Webhook trigger
```

### Alert Configuration Steps

1. Navigate to **Security** → **Alerts**
2. Click **Manage Rules** → **Create New Rule**
3. Select **Custom Query**
4. Enter detection query
5. Configure severity and schedule
6. Set up notification actions
7. **Create and Enable Rule**

---

## 📁 Project Structure

```
elastic-siem-home-lab/
├── 📂 configs/
│   ├── elastic-agent.yml        # Agent configuration
│   └── kibana-dashboards.ndjson # Exported dashboards
├── 📂 queries/
│   ├── nmap-detection.kql       # Nmap scan queries
│   ├── auth-failures.kql        # Authentication queries
│   └── suspicious-activity.kql  # General threat queries
├── 📂 alerts/
│   ├── nmap-scan-rule.json      # Nmap detection rule
│   └── brute-force-rule.json    # Brute force detection
├── 📂 scripts/
│   ├── generate-events.sh       # Security event generator
│   └── install-agent.sh         # Agent installation script
├── 📂 docs/
│   ├── SETUP.md                 # Detailed setup guide
│   ├── QUERIES.md               # Query reference
│   └── TROUBLESHOOTING.md       # Common issues
├── 📂 assets/
│   ├── banner.png               # Project banner
│   └── screenshots/             # Lab screenshots
└── 📄 README.md                 # Project documentation
```

---

## 🗺️ Roadmap

- [x] Set up Elastic Cloud account
- [x] Deploy Kali Linux VM
- [x] Install and configure Elastic Agent
- [x] Generate security events with Nmap
- [x] Query and analyze logs in SIEM
- [x] Create visualization dashboards
- [x] Set up alerting rules
- [ ] Add Windows VM for multi-OS monitoring
- [ ] Integrate with cloud providers (AWS/Azure)
- [ ] Create automated attack simulations
- [ ] Build incident response playbooks
- [ ] Add threat intelligence feeds
- [ ] Implement MITRE ATT&CK mapping

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. 🍴 **Fork** the repository
2. 🌿 **Create** a feature branch (`git checkout -b feature/NewFeature`)
3. 💾 **Commit** your changes (`git commit -m 'Add NewFeature'`)
4. 📤 **Push** to branch (`git push origin feature/NewFeature`)
5. 🔃 **Open** a Pull Request

### Contribution Ideas
- 📝 Additional KQL queries for threat detection
- 📊 New dashboard templates
- 🔔 Alert rules for different attack types
- 📚 Documentation improvements
- 🐛 Bug fixes and optimizations

---

## 📞 Contact & Support

- **Project Repository**: https://github.com/kiransairammuntha/A-Simple-Elastic-SIEM-Lab
- **Issues**: https://github.com/kiransairammuntha/A-Simple-Elastic-SIEM-Lab/issues
- **Discussions**: https://github.com/kiransairammuntha/A-Simple-Elastic-SIEM-Lab/discussions

---

## 📊 Project Stats

![GitHub stars](https://img.shields.io/github/stars/kiransairammuntha/A-Simple-Elastic-SIEM-Lab?style=social)
![GitHub forks](https://img.shields.io/github/forks/kiransairammuntha/A-Simple-Elastic-SIEM-Lab?style=social)
![GitHub issues](https://img.shields.io/github/issues/kiransairammuntha/A-Simple-Elastic-SIEM-Lab)
![GitHub pull requests](https://img.shields.io/github/issues-pr/kiransairammuntha/A-Simple-Elastic-SIEM-Lab)

---

<div align="center">

**Built with ❤️ for Security Analysts**

**Learn. Detect. Respond. Protect.**

**Open-Source Tools • Enterprise Skills • Career Ready**

[⬆ Back to Top](#-a-simple-elastic-siem-lab)

</div>
