<p align="center">
  <img src="https://images.contentstack.io/v3/assets/bltefdd0b53724fa2ce/blt601c406b0b5af740/620577381692951393fdf8d6/elastic-logo-cluster.svg" alt="Elastic Logo" width="200">
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
- [🎓 Skills Demonstrated](#-skills-demonstrated)
- [🏆 Project Achievements](#-project-achievements)
- [📊 Key Metrics & Performance](#-key-metrics--performance)
- [🙏 Acknowledgments](#-acknowledgments)
- [🎬 Project Summary](#-project-summary)
- [📞 Contact & Support](#-contact--support)
- [📊 Project Stats](#-project-stats)

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

## 🎓 Skills Demonstrated

### Technical Skills
- ☁️ **Cloud SIEM Deployment** — Elastic Cloud setup and configuration
- 🐧 **Linux Administration** — Kali VM setup and management
- 📡 **Agent Deployment** — Elastic Agent installation and configuration
- 🔍 **Log Analysis** — KQL query writing and optimization
- 📊 **Data Visualization** — Kibana dashboard creation
- 🚨 **Alert Engineering** — Detection rule configuration

### Security Knowledge
- 🛡️ **SIEM Operations** — Security event monitoring and analysis
- 🔎 **Threat Detection** — Identifying malicious activity patterns
- 🗺️ **Network Scanning** — Nmap reconnaissance techniques
- 📋 **Incident Response** — Alert triage and investigation
- 🎯 **Attack Simulation** — Generating realistic security events

### Professional Competencies
- 📈 **SOC Workflows** — Security Operations Center procedures
- 📝 **Documentation** — Technical writing and guides
- 🧪 **Lab Environment** — Building isolated test environments
- 🔄 **Continuous Learning** — Staying current with security tools
- 🎓 **Knowledge Transfer** — Teaching security concepts

---

## 🏆 Project Achievements

### What This Project Demonstrates
- ✅ Complete SIEM home lab environment setup
- ✅ Cloud-based Elasticsearch deployment
- ✅ Endpoint agent installation and log forwarding
- ✅ Security event generation and analysis
- ✅ Custom dashboard and visualization creation
- ✅ Real-time alerting rule configuration

### Business Value
- 💰 **Cost-Effective Learning** — Free tier cloud resources for training
- 🎯 **Practical Experience** — Hands-on skills employers demand
- 📈 **Career Advancement** — Portfolio project for SOC roles
- 🔍 **Threat Understanding** — Real-world attack pattern recognition
- ✅ **Interview Ready** — Demonstrable SIEM experience

---

## 📊 Key Metrics & Performance

### Lab Capabilities

| Metric | Value |
|--------|-------|
| **Log Ingestion** | Real-time streaming |
| **Query Speed** | Millisecond responses |
| **Visualization** | Custom Kibana dashboards |
| **Alerting** | Rule-based detection |
| **Retention** | Configurable log storage |
| **Scalability** | Cloud-based expansion |

### Detection Coverage

| Event Type | Detection Method | Response |
|------------|------------------|----------|
| 🔍 **Nmap Scans** | Process monitoring | Alert triggered |
| 🔐 **Auth Failures** | Log analysis | Dashboard update |
| ⚡ **Privilege Escalation** | Sudo tracking | Real-time alert |
| 🌐 **SSH Attempts** | Connection logging | Event correlation |

---

## 🙏 Acknowledgments

**Open-Source Projects:**
- [Elastic Stack](https://www.elastic.co/) — Elasticsearch, Kibana, Beats
- [Kali Linux](https://www.kali.org/) — Penetration testing distribution
- [Nmap](https://nmap.org/) — Network scanner

**Cloud Platforms:**
- [Elastic Cloud](https://cloud.elastic.co/) — Managed Elasticsearch service
- [VirtualBox](https://www.virtualbox.org/) — Virtualization platform
- [VMware](https://www.vmware.com/) — Virtualization platform

**Security Community:**
- SOC analyst best practices
- Threat detection methodologies
- SIEM implementation guides

---

## 🎬 Project Summary

This Elastic SIEM Home Lab represents a **complete, hands-on security monitoring environment** that combines:

✅ **Enterprise SIEM technology** (Elastic Stack)
✅ **Cloud deployment** (Elastic Cloud)
✅ **Endpoint monitoring** (Elastic Agent)
✅ **Attack simulation** (Nmap scanning)
✅ **Visual analytics** (Kibana dashboards)
✅ **Real-time alerting** (Detection rules)

**Demonstrates:**
- SIEM deployment expertise
- Log analysis proficiency
- Query language skills (KQL)
- Dashboard creation abilities
- Alert engineering knowledge

**Delivers:**
- Practical SOC experience
- Portfolio-ready project
- Interview talking points
- Hands-on threat detection
- Real-world security skills

**Perfect For:**
- SOC Analyst roles
- Security Engineer positions
- Threat Detection opportunities
- Blue Team careers
- Portfolio demonstration

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
