<div align="center">

# 🔐 API Security Testing

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
[![Roadmap](https://img.shields.io/badge/Roadmap-4%20Months-blue.svg)]()
[![Status](https://img.shields.io/badge/Status-Active-success.svg)]()

**A comprehensive, hands-on learning repository for API Security Testing — from HTTP basics to real-world bug bounty hunting.**

[Getting Started](#-getting-started) • [Roadmap](#-roadmap) • [Labs](#-labs) • [Resources](#-resources)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Repository Structure](#-repository-structure)
- [Getting Started](#-getting-started)
- [Learning Roadmap](#-learning-roadmap)
- [Labs & Practice](#-labs--practice)
- [Tools & Technologies](#-tools--technologies)
- [Key Vulnerabilities Covered](#-key-vulnerabilities-covered)
- [Resources](#-resources)
- [How to Use This Repo](#-how-to-use-this-repo)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 Overview

This repository documents my journey into **API Security Testing**, covering the complete pipeline from understanding REST APIs to identifying and exploiting real-world vulnerabilities. The content is structured for **systematic learning** with a strong emphasis on **practical, hands-on labs**.

### What You'll Find Here

- ✅ Structured learning modules from basics to advanced
- ✅ Step-by-step vulnerable API lab walkthroughs
- ✅ Authentication & Authorization attack vectors
- ✅ Custom Python automation scripts
- ✅ Bug bounty reporting templates
- ✅ Curated resources and cheat sheets

---

## 📁 Repository Structure

```
api-security-testing/
│
├── 📂 01-basics/                  # HTTP, JSON, Status Codes
├── 📂 02-tools-setup/             # Postman, Burp Suite, cURL
├── 📂 03-authentication/          # API Keys, JWT, Sessions
├── 📂 04-authorization/           # BOLA/IDOR, BFLA, Mass Assignment
├── 📂 05-common-vulnerabilities/  # SQLi, XSS, Rate Limiting
├── 📂 06-labs-practice/           # crAPI, PortSwigger Walkthroughs
├── 📂 07-notes/                   # OWASP API Top 10 Summaries
├── 📂 08-resources/               # YouTube, Blogs, Platforms
│
├── 📄 README.md                   # You are here
├── 📄 ROADMAP.md                  # Detailed 4-month learning plan
└── 📄 .gitignore
```

---

## 🚀 Getting Started

### Prerequisites

Before diving in, ensure you have:

| Requirement | Purpose |
|-------------|---------|
| [Postman](https://www.postman.com/downloads/) | API testing & manual requests |
| [Burp Suite Community](https://portswigger.net/burp/communitydownload) | Proxy, intercept & repeater |
| [Docker](https://www.docker.com/products/docker-desktop) | Run vulnerable labs locally |
| Python 3.x | Automation scripts |
| Linux/Unix Terminal | cURL & command-line tools |

### Quick Setup

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/api-security-testing.git
cd api-security-testing

# Set up vulnerable lab environment (crAPI)
docker pull crapi/crapi-all
docker run -p 8888:8888 crapi/crapi-all

# Access crAPI at http://localhost:8888
```

---

## 🗺️ Learning Roadmap

> **Duration:** 16 Weeks (4 Months) | **Commitment:** 1.5–2 Hours/Day

### Phase 1: Foundation (Weeks 1–2)
- [ ] Understand HTTP Methods: GET, POST, PUT, DELETE
- [ ] Master Status Codes: 200, 401, 403, 404, 500
- [ ] Learn JSON structure & data types
- [ ] Make 50+ API requests using Postman

**Deliverable:** Collection of API requests with different methods & headers.

### Phase 2: Tools Mastery (Weeks 3–4)
- [ ] Configure Burp Suite Proxy with browser
- [ ] Intercept & modify requests in Repeater
- [ ] Write cURL one-liners for common operations
- [ ] Understand request/response lifecycle

**Deliverable:** Intercepted & modified 20+ API requests via Burp.

### Phase 3: Authentication Attacks (Weeks 5–7)
- [ ] Decode & analyze JWT tokens (jwt.io)
- [ ] Identify None Algorithm vulnerability
- [ ] Test weak JWT secrets
- [ ] Understand API Key exposure risks
- [ ] Session vs Token-based auth comparison

**Deliverable:** JWT attack lab completion with PoC screenshots.

### Phase 4: Authorization Attacks ⭐ (Weeks 8–11)
- [ ] **BOLA (IDOR):** Access other users' resources by manipulating IDs
- [ ] **BFLA:** Access admin endpoints with regular user credentials
- [ ] **Mass Assignment:** Inject extra JSON properties for privilege escalation
- [ ] Test horizontal & vertical privilege escalation

**Deliverable:** 3 complete lab walkthroughs with detailed notes.

### Phase 5: Common Vulnerabilities (Weeks 12–13)
- [ ] SQL Injection via API parameters
- [ ] XSS through API responses
- [ ] Rate Limiting bypass techniques
- [ ] Sensitive data exposure in error messages

**Deliverable:** Vulnerability checklist for each attack type.

### Phase 6: Real-World Practice (Weeks 14–16)
- [ ] Complete PortSwigger API Security labs
- [ ] Practice on Hack The Box / TryHackMe
- [ ] Submit first bug bounty report (HackerOne/Bugcrowd)
- [ ] Document findings with professional reports

**Deliverable:** First valid bug bounty submission or CTF write-up.

---

## 🧪 Labs & Practice

### Local Vulnerable Labs

| Lab | Description | Setup |
|-----|-------------|-------|
| **crAPI** | Completely Ridiculous API — OWASP-based vulnerable API | `docker run crapi/crapi-all` |
| **VAmPI** | Vulnerable API for security testing | `docker run -p 5000:5000 erev0s/vampi` |
| **vAPI** | Another vulnerable API project | Docker or local Python |

### Online Platforms

| Platform | Type | Link |
|----------|------|------|
| PortSwigger Web Security Academy | Free Guided Labs | [portswigger.net](https://portswigger.net/web-security) |
| TryHackMe | Rooms & Challenges | [tryhackme.com](https://tryhackme.com) |
| Hack The Box | Machines & CTFs | [hackthebox.com](https://www.hackthebox.com) |

### Lab Documentation Format

Each lab in `06-labs-practice/` follows this structure:

```markdown
## Lab: [Name]

### Target Endpoint
```
METHOD /api/endpoint
```

### Vulnerability
[BOLA / JWT / Auth Bypass / etc.]

### Steps to Reproduce
1. Step one
2. Step two
3. Step three

### Proof of Concept
[Screenshot attached in screenshots/]

### Impact
[What an attacker can achieve]

### Mitigation
[How to fix this vulnerability]
```

---

## 🛠️ Tools & Technologies

### Primary Tools

| Tool | Category | Purpose |
|------|----------|---------|
| **Postman** | API Testing | Manual request crafting & collections |
| **Burp Suite** | Proxy & Repeater | Intercept, modify, and replay requests |
| **cURL** | Command Line | Quick API calls and automation |
| **Docker** | Environment | Run vulnerable labs locally |

### Python Libraries

```txt
requests          # HTTP requests
pyjwt             # JWT encoding/decoding
python-jose       # JWT verification
urllib3           # Advanced HTTP client
```

### Browser Extensions

- **FoxProxy** — Quick proxy switching
- **JSON Viewer** — Format API responses
- **Wappalyzer** — Technology fingerprinting

---

## 🎯 Key Vulnerabilities Covered

### 🔴 Critical

| Vulnerability | OWASP Category | Description |
|---------------|----------------|-------------|
| **BOLA / IDOR** | API1:2023 | Access other users' objects by manipulating IDs |
| **Broken Authentication** | API2:2023 | Weak JWT, None Alg, credential stuffing |
| **BFLA** | API5:2023 | Regular user accessing admin functions |

### 🟠 High

| Vulnerability | OWASP Category | Description |
|---------------|----------------|-------------|
| **Mass Assignment** | API3:2023 | Injecting extra properties in JSON payloads |
| **Excessive Data Exposure** | API3:2023 | APIs returning more data than needed |
| **Rate Limit Bypass** | API4:2023 | Circumventing request throttling |

### 🟡 Medium

| Vulnerability | Description |
|---------------|-------------|
| **SQL Injection** | Injecting SQL via API parameters |
| **XSS via API** | Stored/Reflected XSS through API responses |
| **Error Message Leakage** | Stack traces & sensitive info in errors |

---

## 📚 Resources

### 📖 Recommended Reading

- [OWASP API Security Top 10 (2023)](https://owasp.org/www-project-api-security/)
- [The Web Application Hacker's Handbook](https://portswigger.net/web-security)
- [API Security in Action](https://www.manning.com/books/api-security-in-action)

### 🎥 YouTube Channels

- [InsiderPhD](https://www.youtube.com/@InsiderPhD) — Bug bounty & API hacking
- [STÖK](https://www.youtube.com/@STOKfredrik) — Recon & methodology
- [NahamSec](https://www.youtube.com/@NahamSec) — Beginner-friendly content
- [HackerSploit](https://www.youtube.com/@HackerSploit) — Labs & tools

### 📝 Blogs & Write-ups

- [PortSwigger Research](https://portswigger.net/research)
- [HackerOne Hacktivity](https://hackerone.com/hacktivity)
- [Bugcrowd Blog](https://www.bugcrowd.com/blog/)

### 🏆 Bug Bounty Platforms

| Platform | Focus |
|----------|-------|
| [HackerOne](https://hackerone.com) | Enterprise programs |
| [Bugcrowd](https://bugcrowd.com) | Diverse scope |
| [Intigriti](https://intigriti.com) | European programs |

---

## 📖 How to Use This Repo

### For Beginners

1. Start with `01-basics/` — don't skip fundamentals
2. Set up tools from `02-tools-setup/`
3. Follow the Roadmap week by week
4. Complete every lab before moving forward

### For Practice

1. Pick a vulnerability from `04-authorization/` or `05-common-vulnerabilities/`
2. Read the notes and understand the attack vector
3. Fire up crAPI or PortSwigger lab
4. Document your findings in the lab folder

### For Bug Bounty

1. Review `07-notes/` for quick reference
2. Use checklists before submitting
3. Follow the reporting template in `09-reporting/`
4. Always include PoC screenshots

---

## 🤝 Contributing

This is a personal learning repository, but suggestions are welcome!

If you find better resources, improved payloads, or want to share lab walkthroughs:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit your changes (`git commit -m 'Add: new payload for BOLA'`)
4. Push to the branch (`git push origin feature/improvement`)
5. Open a Pull Request

---

## 📝 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

> **Disclaimer:** This repository is for **educational purposes only**. Always test on systems you own or have explicit permission to test. Unauthorized access to computer systems is illegal.

---

<div align="center">

**⭐ Star this repo if you find it helpful!**

*Happy Hacking! 🔥*

</div>
