<div align="center">

# 🔐 API Security Testing — Learning Journey

[![Status](https://img.shields.io/badge/Status-Active%20Learning-brightgreen?style=for-the-badge)]()
[![Progress](https://img.shields.io/badge/Progress-Week%200%2F16-blue?style=for-the-badge)]()
[![Labs](https://img.shields.io/badge/Labs-0%20Completed-orange?style=for-the-badge)]()
[![Scripts](https://img.shields.io/badge/Scripts-0%20Built-yellow?style=for-the-badge)]()
[![Focus](https://img.shields.io/badge/Focus-REST%20API%20Security-critical?style=for-the-badge)]()

> **A comprehensive, hands-on documentation of my API Security Testing journey — from HTTP fundamentals to real-world bug bounty hunting.**
>
> *"Every expert was once a beginner. This repo is proof of the grind."*

[Progress](#-progress-overview) • [Labs](#-lab-index) • [Notes](#-learning-notes) • [Roadmap](#-16-week-roadmap) • [Resources](#-resources)

</div>

---

## 👤 About This Repository

**Author:** Saber Hasan Swoyon | Software Engineering Undergraduate

- 🛡️ **Aspiring Application Security (AppSec) Engineer**
- 🐍 **Tech Stack:** Python | Linux | Burp Suite | Postman | Docker
- 📚 **Currently Learning:** REST API Security Testing
- 🎯 **Goal:** Master API vulnerabilities → Bug Bounty → AppSec Career

> 🔗 **My Main Portfolio:** [Cybersecurity Labs Portfolio](https://github.com/swoyon01/cybersecurity-labs)

This repository serves as my **centralized learning hub** for API Security Testing. Every concept I learn, every lab I complete, every script I write — everything is documented here. Once this learning journey is complete, I will compile the best findings into a polished, public portfolio repository.

---

## 📊 Progress Overview

| Category | Completed | In Progress | Not Started |
|----------|:---------:|:-----------:|:-----------:|
| **01 — HTTP Basics** | 0 | 0 | 4 |
| **02 — Tools Setup** | 0 | 0 | 3 |
| **03 — Authentication** | 0 | 0 | 4 |
| **04 — Authorization** | 0 | 0 | 3 |
| **05 — Common Vulnerabilities** | 0 | 0 | 4 |
| **06 — Labs & Practice** | 0 | 0 | 4+ |
| **07 — Notes & Cheatsheets** | 0 | 0 | 2 |
| **08 — Resources** | 0 | 0 | 3 |

**Overall Progress:** `0%` (0 / 30 topics)

**Current Phase:** 🟡 **Foundation** — Week 1–2

---

## 📁 Repository Structure

```
api-security-testing/
│
├── 📄 README.md                   
├── 📄 ROADMAP.md                   ← Detailed 16-week learning plan
├── 📄 .gitignore
│
├── 📂 01-basics/                   ← Foundation Phase
│   ├── 📄 01-http-methods.md
│   ├── 📄 02-status-codes.md
│   ├── 📄 03-json-basics.md
│   └── 📄 04-api-vs-website.md
│
├── 📂 02-tools-setup/              ← Tool Mastery
│   ├── 📄 01-postman-setup.md
│   ├── 📄 02-burp-suite-setup.md
│   └── 📄 03-curl-commands.md
│
├── 📂 03-authentication/           ← Breaking Authentication
│   ├── 📄 01-api-keys.md
│   ├── 📄 02-jwt-basics.md
│   ├── 📄 03-jwt-common-attacks.md
│   └── 📄 04-session-tokens.md
│
├── 📂 04-authorization/            ← Breaking Authorization ⭐
│   ├── 📄 01-idor-bola.md
│   ├── 📄 02-bfla.md
│   └── 📄 03-mass-assignment.md
│
├── 📂 05-common-vulnerabilities/   ← Other API Attacks
│   ├── 📄 01-sql-injection-api.md
│   ├── 📄 02-xss-via-api.md
│   ├── 📄 03-rate-limiting.md
│   └── 📄 04-error-message-leakage.md
│
├── 📂 06-labs-practice/            ← Hands-On Labs
│   ├── 📄 01-crapi-setup.md
│   ├── 📄 02-lab1-idor.md
│   ├── 📄 03-lab2-jwt.md
│   ├── 📄 04-lab3-auth-bypass.md
│   └── 📂 screenshots/
│
├── 📂 07-notes/                    ← Quick Reference
│   ├── 📄 owasp-api-top10-summary.md
│   └── 📄 bug-bounty-tips.md
│
└── 📂 08-resources/                ← External Links
    ├── 📄 youtube-playlists.md
    ├── 📄 useful-websites.md
    └── 📄 practice-platforms.md
```

---

## 🧪 Lab Index

### crAPI (Completely Ridiculous API) — Local Lab

> **Setup:** `docker run -p 8888:8888 crapi/crapi-all` → http://localhost:8888

| # | Challenge | Vulnerability | Difficulty | Status | Write-up |
|---|-----------|---------------|:----------:|:------:|----------|
| 01 | — | — | — | 🔴 | — |
| 02 | — | — | — | 🔴 | — |
| 03 | — | — | — | 🔴 | — |
| 04 | — | — | — | 🔴 | — |
| 05 | — | — | — | 🔴 | — |
| 06 | — | — | — | 🔴 | — |
| 07 | — | — | — | 🔴 | — |
| 08 | — | — | — | 🔴 | — |
| 09 | — | — | — | 🔴 | — |
| 10 | — | — | — | 🔴 | — |

### PortSwigger Web Security Academy — API Labs

| # | Lab Name | Vulnerability | Difficulty | Status | Write-up |
|---|----------|---------------|:----------:|:------:|----------|
| 01 | — | — | — | 🔴 | — |
| 02 | — | — | — | 🔴 | — |
| 03 | — | — | — | 🔴 | — |
| 04 | — | — | — | 🔴 | — |
| 05 | — | — | — | 🔴 | — |

### VAmPI — Local Lab

> **Setup:** `docker run -p 5000:5000 erev0s/vampi`

| # | Challenge | Vulnerability | Status | Write-up |
|---|-----------|---------------|:------:|----------|
| 01 | — | — | 🔴 | — |
| 02 | — | — | 🔴 | — |
| 03 | — | — | 🔴 | — |

### Custom Scripts & Tools

| # | Script Name | Purpose | Language | Status | Location |
|---|-------------|---------|----------|:------:|----------|
| 01 | — | — | Python | 🔴 | — |
| 02 | — | — | Python | 🔴 | — |
| 03 | — | — | Python | 🔴 | — |
| 04 | — | — | Python | 🔴 | — |

**Legend:** 🔴 Not Started | 🟡 In Progress | ✅ Completed

---

## 📝 Learning Notes

### 01 — HTTP Basics

| # | Topic | Description | Status | File |
|---|-------|-------------|:------:|------|
| 1.1 | HTTP Methods | GET, POST, PUT, DELETE, PATCH, OPTIONS | 🔴 | `01-basics/01-http-methods.md` |
| 1.2 | Status Codes | 1xx, 2xx, 3xx, 4xx, 5xx categories | 🔴 | `01-basics/02-status-codes.md` |
| 1.3 | JSON Basics | Objects, arrays, strings, numbers, booleans, null | 🔴 | `01-basics/03-json-basics.md` |
| 1.4 | API vs Website | How APIs differ from traditional web apps | 🔴 | `01-basics/04-api-vs-website.md` |

### 02 — Tools Setup

| # | Topic | Description | Status | File |
|---|-------|-------------|:------:|------|
| 2.1 | Postman | Collections, environments, variables, tests | 🔴 | `02-tools-setup/01-postman-setup.md` |
| 2.2 | Burp Suite | Proxy, intercept, repeater, intruder, target scope | 🔴 | `02-tools-setup/02-burp-suite-setup.md` |
| 2.3 | cURL | Command-line requests, headers, auth, data | 🔴 | `02-tools-setup/03-curl-commands.md` |

### 03 — Authentication

| # | Topic | Description | Status | File |
|---|-------|-------------|:------:|------|
| 3.1 | API Keys | Header vs URL vs Cookie placement, exposure risks | 🔴 | `03-authentication/01-api-keys.md` |
| 3.2 | JWT Basics | Structure (Header.Payload.Signature), claims, decode | 🔴 | `03-authentication/02-jwt-basics.md` |
| 3.3 | JWT Common Attacks | None alg, weak secret, KID injection, alg confusion | 🔴 | `03-authentication/03-jwt-common-attacks.md` |
| 3.4 | Session Tokens | Cookies vs tokens, session fixation, hijacking | 🔴 | `03-authentication/04-session-tokens.md` |

### 04 — Authorization ⭐

| # | Topic | Description | Status | File |
|---|-------|-------------|:------:|------|
| 4.1 | BOLA / IDOR | Broken Object Level Authorization, ID manipulation | 🔴 | `04-authorization/01-idor-bola.md` |
| 4.2 | BFLA | Broken Function Level Authorization, admin endpoints | 🔴 | `04-authorization/02-bfla.md` |
| 4.3 | Mass Assignment | Injecting extra JSON properties for privilege escalation | 🔴 | `04-authorization/03-mass-assignment.md` |

### 05 — Common Vulnerabilities

| # | Topic | Description | Status | File |
|---|-------|-------------|:------:|------|
| 5.1 | SQL Injection (API) | SQLi via API parameters, headers, JSON values | 🔴 | `05-common-vulnerabilities/01-sql-injection-api.md` |
| 5.2 | XSS via API | Stored & reflected XSS through API responses | 🔴 | `05-common-vulnerabilities/02-xss-via-api.md` |
| 5.3 | Rate Limiting | 429 responses, bypass via headers, IP rotation | 🔴 | `05-common-vulnerabilities/03-rate-limiting.md` |
| 5.4 | Error Message Leakage | Stack traces, sensitive info, verbose errors | 🔴 | `05-common-vulnerabilities/04-error-message-leakage.md` |

### 06 — Labs & Practice

| # | Lab | Platform | Vulnerability | Status | File |
|---|-----|----------|---------------|:------:|------|
| 6.1 | crAPI Setup | Docker | Lab environment | 🔴 | `06-labs-practice/01-crapi-setup.md` |
| 6.2 | Lab 1 — IDOR | crAPI/PortSwigger | BOLA/IDOR | 🔴 | `06-labs-practice/02-lab1-idor.md` |
| 6.3 | Lab 2 — JWT | crAPI/PortSwigger | JWT attacks | 🔴 | `06-labs-practice/03-lab2-jwt.md` |
| 6.4 | Lab 3 — Auth Bypass | crAPI/PortSwigger | Authentication | 🔴 | `06-labs-practice/04-lab3-auth-bypass.md` |

### 07 — Notes & Cheatsheets

| # | Topic | Description | Status | File |
|---|-------|-------------|:------:|------|
| 7.1 | OWASP API Top 10 | 2023 version summary with examples | 🔴 | `07-notes/owasp-api-top10-summary.md` |
| 7.2 | Bug Bounty Tips | Reporting, CVSS, PoC, platforms | 🔴 | `07-notes/bug-bounty-tips.md` |

### 08 — Resources

| # | Topic | Description | Status | File |
|---|-------|-------------|:------:|------|
| 8.1 | YouTube Playlists | Curated video tutorials | 🔴 | `08-resources/youtube-playlists.md` |
| 8.2 | Useful Websites | Blogs, documentation, tools | 🔴 | `08-resources/useful-websites.md` |
| 8.3 | Practice Platforms | TryHackMe, HTB, PortSwigger, etc. | 🔴 | `08-resources/practice-platforms.md` |

---

## 🗺️ 16-Week Roadmap

> **Duration:** 16 Weeks (4 Months)  
> **Daily Commitment:** 1.5–2 Hours  
> **Start Date:** [Fill in your start date]

### Phase 1: Foundation (Week 1–2)
**Goal:** Understand how APIs communicate

- [ ] **Week 1:** HTTP Methods (GET, POST, PUT, DELETE, PATCH, OPTIONS)
  - Make 50+ API requests using Postman
  - Understand request/response lifecycle
  - Document: `01-basics/01-http-methods.md`

- [ ] **Week 2:** Status Codes & JSON
  - Build status code reference sheet (1xx–5xx)
  - Parse complex JSON responses
  - Understand Content-Type headers
  - Document: `01-basics/02-status-codes.md` + `01-basics/03-json-basics.md`

**Deliverables:** Complete `01-basics/` folder

---

### Phase 2: Tools Mastery (Week 3–4)
**Goal:** Become comfortable with testing tools

- [ ] **Week 3:** Postman Deep Dive
  - Collections, folders, environment variables
  - Pre-request scripts & tests
  - Collection runner for automation
  - Document: `02-tools-setup/01-postman-setup.md`

- [ ] **Week 4:** Burp Suite for APIs
  - Proxy setup with Firefox + FoxyProxy
  - Intercept, Repeater, Intruder basics
  - Target scope & filtering
  - Document: `02-tools-setup/02-burp-suite-setup.md`

**Deliverables:** Complete `02-tools-setup/` folder + screenshots

---

### Phase 3: Authentication Attacks (Week 5–7)
**Goal:** Break how APIs verify "who you are"

- [ ] **Week 5:** API Keys & Basic Auth
  - Key placement risks (URL, header, cookie)
  - Basic Auth (Base64) testing
  - Common misconfigurations
  - Document: `03-authentication/01-api-keys.md`

- [ ] **Week 6:** JWT Basics
  - Structure: Header.Payload.Signature
  - Decode with jwt.io
  - Claims: iss, sub, aud, exp, nbf, iat, jti
  - Document: `03-authentication/02-jwt-basics.md`

- [ ] **Week 7:** JWT Attacks
  - None algorithm attack
  - Weak secret brute force
  - KID injection & algorithm confusion
  - Complete PortSwigger JWT labs
  - Document: `03-authentication/03-jwt-common-attacks.md`

**Deliverables:** Complete `03-authentication/` folder + working PoCs

---

### Phase 4: Authorization Attacks ⭐ (Week 8–11)
**Goal:** Break how APIs verify "what you can do"

- [ ] **Week 8:** BOLA / IDOR
  - Set up crAPI lab
  - Identify endpoints with object IDs
  - Test horizontal privilege escalation
  - Document: `04-authorization/01-idor-bola.md` + lab walkthrough

- [ ] **Week 9:** BFLA
  - Discover admin endpoints
  - Test with normal user token
  - Method-based access control
  - Document: `04-authorization/02-bfla.md`

- [ ] **Week 10:** Mass Assignment
  - Send extra JSON properties
  - Test for privilege escalation
  - Complete crAPI mass assignment challenge
  - Document: `04-authorization/03-mass-assignment.md`

- [ ] **Week 11:** Authorization Review
  - Review all authorization vulnerabilities
  - Complete remaining PortSwigger labs
  - Build reusable testing checklist

**Deliverables:** Complete `04-authorization/` folder + 3+ lab walkthroughs

---

### Phase 5: Common Vulnerabilities (Week 12–13)
**Goal:** Find other weaknesses in APIs

- [ ] **Week 12:** Injection Attacks
  - SQL Injection via API parameters
  - XSS through API responses
  - Document: `05-common-vulnerabilities/01-sql-injection-api.md` + `02-xss-via-api.md`

- [ ] **Week 13:** Rate Limiting & Info Disclosure
  - Test for rate limiting (429)
  - Bypass via headers (X-Forwarded-For, etc.)
  - Error message analysis
  - Build rate-limit bypass script
  - Document: `05-common-vulnerabilities/03-rate-limiting.md` + `04-error-message-leakage.md`

**Deliverables:** Complete `05-common-vulnerabilities/` folder + scripts

---

### Phase 6: Real-World Practice (Week 14–16)
**Goal:** Apply everything in realistic environments

- [ ] **Week 14:** crAPI Complete Walkthrough
  - Solve all crAPI challenges
  - Write bug reports for each finding
  - Document: `06-labs-practice/`

- [ ] **Week 15:** PortSwigger API Labs
  - Complete all API-related labs
  - Document techniques & payloads

- [ ] **Week 16:** Bug Bounty Preparation
  - Choose target with API scope
  - Perform recon & find endpoints
  - Submit first bug bounty report

**Deliverables:** Complete `06-labs-practice/` + first bug bounty submission

---

## 🎯 OWASP API Security Top 10 (2023) — Progress Tracker

| Rank | Vulnerability | API Category | Status | Notes |
|:----:|---------------|:------------:|:------:|-------|
| API1 | **Broken Object Level Authorization** | Authorization | 🔴 | — |
| API2 | **Broken Authentication** | Authentication | 🔴 | — |
| API3 | **Broken Object Property Level Authorization** | Authorization | 🔴 | — |
| API4 | **Unrestricted Resource Consumption** | Availability | 🔴 | — |
| API5 | **Broken Function Level Authorization** | Authorization | 🔴 | — |
| API6 | **Unrestricted Access to Sensitive Business Flows** | Business Logic | 🔴 | — |
| API7 | **Server Side Request Forgery (SSRF)** | Injection | 🔴 | — |
| API8 | **Security Misconfiguration** | Configuration | 🔴 | — |
| API9 | **Improper Inventory Management** | Asset Management | 🔴 | — |
| API10 | **Unsafe Consumption of APIs** | Third-Party | 🔴 | — |

**Legend:** 🔴 Not Started | 🟡 Learning | 🟢 Practiced | ✅ Mastered

---

## 🛠️ My Toolkit

```
┌─────────────────────────────────────────────┐
│  OS:        Kali Linux (VirtualBox)         │
│  Browser:   Firefox + FoxyProxy             │
│  Proxy:     Burp Suite Community Edition    │
│  API Tool:  Postman                         │
│  Editor:    VS Code                         │
│  Terminal:  Bash / Zsh                      │
│  Languages: Python 3, Bash                  │
│  Labs:      Docker (crAPI, VAmPI)           │
└─────────────────────────────────────────────┘
```

### Python Libraries for API Testing

```bash
pip install requests        # HTTP requests
pip install pyjwt           # JWT encode/decode
pip install python-jose     # JWT verification
pip install urllib3         # Advanced HTTP client
```

---

## 📚 Resources

### 📖 Books & Documentation

| Resource | Type | Link |
|----------|------|------|
| OWASP API Security Top 10 (2023) | Official Guide | [owasp.org](https://owasp.org/www-project-api-security/) |
| PortSwigger Web Security Academy | Free Labs | [portswigger.net](https://portswigger.net/web-security) |
| API Security in Action | Book | Manning Publications |

### 🎥 YouTube Channels

| Channel | Focus | Link |
|---------|-------|------|
| InsiderPhD | Bug bounty & API hacking | [YouTube](https://www.youtube.com/@InsiderPhD) |
| STÖK | Recon & methodology | [YouTube](https://www.youtube.com/@STOKfredrik) |
| NahamSec | Beginner-friendly content | [YouTube](https://www.youtube.com/@NahamSec) |
| HackerSploit | Labs & tools | [YouTube](https://www.youtube.com/@HackerSploit) |

### 🏆 Bug Bounty Platforms

| Platform | Best For | Link |
|----------|----------|------|
| HackerOne | Enterprise programs | [hackerone.com](https://hackerone.com) |
| Bugcrowd | Diverse scope | [bugcrowd.com](https://bugcrowd.com) |
| Intigriti | European programs | [intigriti.com](https://intigriti.com) |

### 🧪 Practice Platforms

| Platform | Type | Best For |
|----------|------|----------|
| PortSwigger Web Security Academy | Free Guided Labs | Structured learning |
| TryHackMe | Rooms & Challenges | Beginner to advanced |
| Hack The Box | Machines & CTFs | Realistic scenarios |

### 🐳 Local Vulnerable Labs

```bash
# crAPI — OWASP-based vulnerable API
docker pull crapi/crapi-all
docker run -p 8888:8888 crapi/crapi-all
# Access: http://localhost:8888

# VAmPI — Vulnerable API for auth & injection
docker pull erev0s/vampi
docker run -p 5000:5000 erev0s/vampi
# Access: http://localhost:5000
```

---

## 📝 How I Use This Repository

### Daily Routine
1. **Study** → Read/watch tutorial on today's topic
2. **Practice** → Fire up a lab or test on a public API
3. **Document** → Write notes in the relevant `.md` file
4. **Update** → Mark progress in this README
5. **Commit** → `git add . && git commit -m "Week X: Topic completed"`

### Lab Documentation Format
Each lab walkthrough in `06-labs-practice/` follows:

```markdown
## Lab: [Name]

### Target
```
METHOD /api/endpoint
Headers: ...
Body: ...
```

### Vulnerability
[Type: BOLA / JWT / Auth Bypass / etc.]

### Steps to Reproduce
1. Step one
2. Step two
3. Step three

### Proof of Concept
[Screenshot in screenshots/ folder]

### Impact
[What an attacker can achieve]

### Mitigation
[How to fix]
```

---

## ✅ Completion Checklist

- [ ] All `01-basics/` topics completed
- [ ] All `02-tools-setup/` topics completed
- [ ] All `03-authentication/` topics completed
- [ ] All `04-authorization/` topics completed
- [ ] All `05-common-vulnerabilities/` topics completed
- [ ] At least 5 lab walkthroughs documented
- [ ] At least 3 Python scripts written
- [ ] OWASP API Top 10 summary completed
- [ ] First bug bounty report submitted
- [ ] Progress tracker fully updated

---

## 🔗 Connect With Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/swoyon)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:swoyon@email.com)
[![TryHackMe](https://img.shields.io/badge/TryHackMe-212C42?style=for-the-badge&logo=tryhackme&logoColor=white)](https://tryhackme.com/p/swoyon)

---

> **Disclaimer:** This repository is for educational and personal learning purposes only. All testing is performed on:
> - Authorized training platforms (TryHackMe, PortSwigger)
> - Locally hosted vulnerable labs (crAPI, VAmPI)
> - Systems I own or have explicit permission to test
>
> **Unauthorized access to computer systems is illegal.**

---

<div align="center">

**⭐ Star this repo to follow my API security journey!**

*Learning one vulnerability at a time. Building the future of security. 🔥*

</div>
