# PortSwigger Web Security Academy — Notes & Progress

My personal notes, payloads, and lab writeups from PortSwigger Web Security Academy.
Each folder contains detailed notes for that topic. Check off labs as you complete them — but only mark done when you've solved it without hints, re-solved it from scratch, and documented why it worked.

---

## Progress Tracker

| Phase | Topic | Status |
|-------|-------|--------|
| 🟢 Phase 1 | Server-side vulnerabilities | ![](https://img.shields.io/badge/0%25-grey) |
| 🟢 Phase 1 | SQL Injection | ![](https://img.shields.io/badge/0%25-grey) |
| 🟢 Phase 1 | Authentication vulnerabilities | ![](https://img.shields.io/badge/0%25-grey) |
| 🟢 Phase 1 | Access control vulnerabilities | ![](https://img.shields.io/badge/0%25-grey) |
| 🟢 Phase 1 | CSRF | ![](https://img.shields.io/badge/0%25-grey) |
| 🟡 Phase 2 | Path Traversal | ![](https://img.shields.io/badge/0%25-grey) |
| 🟡 Phase 2 | File Upload Vulnerabilities | ![](https://img.shields.io/badge/0%25-grey) |
| 🟡 Phase 2 | SSRF | ![](https://img.shields.io/badge/0%25-grey) |
| 🟠 Phase 3 | CORS | ![](https://img.shields.io/badge/0%25-grey) |
| 🟠 Phase 3 | Clickjacking | ![](https://img.shields.io/badge/0%25-grey) |
| 🔴 Phase 4 | API Testing | ![](https://img.shields.io/badge/0%25-grey) |
| 🔴 Phase 4 | OAuth Authentication Vulnerabilities | ![](https://img.shields.io/badge/0%25-grey) |
| 🔴 Phase 4 | Race Conditions | ![](https://img.shields.io/badge/0%25-grey) |
| 🔴 Phase 4 | NoSQL Injection | ![](https://img.shields.io/badge/0%25-grey) |
| 🟣 Phase 5 | WebSockets vulnerabilities | ![](https://img.shields.io/badge/0%25-grey) |
| 🟣 Phase 5 | GraphQL API vulnerabilities | ![](https://img.shields.io/badge/0%25-grey) |
| 🟣 Phase 5 | Prototype pollution | ![](https://img.shields.io/badge/0%25-grey) |
| 🟣 Phase 5 | Web cache deception | ![](https://img.shields.io/badge/0%25-grey) |
| 🟣 Phase 5 | Web LLM attacks | ![](https://img.shields.io/badge/0%25-grey) |

---

## 🟢 PHASE 1 — Foundations

> Build HTTP instinct. Understand how requests work before you abuse them.

---

### 1. Server-side Vulnerabilities (Apprentice)

Your base camp. Parameter tampering, basic injections, access control, request manipulation.

- [ ] Apprentice Lab 1 — Retrieving hidden data via SQL injection
- [ ] Apprentice Lab 2 — Bypassing login with SQL injection
- [ ] Apprentice Lab 3 — Insecure direct object references (IDOR)
- [ ] Apprentice Lab 4 — File path traversal — simple case
- [ ] Apprentice Lab 5 — OS command injection — simple case
- [ ] Apprentice Lab 6 — Reflected XSS into HTML context with nothing encoded
- [ ] Apprentice Lab 7 — Stored XSS into HTML context with nothing encoded
- [ ] Apprentice Lab 8 — Username enumeration via different responses
- [ ] Apprentice Lab 9 — 2FA simple bypass
- [ ] Apprentice Lab 10 — Unprotected admin functionality

---

### 2. SQL Injection (Practitioner)

Don't move forward until you can do UNION, Boolean blind, and Time-based blind manually.

#### UNION Attacks
- [ ] SQL injection UNION attack — determining number of columns
- [ ] SQL injection UNION attack — finding a column with text data
- [ ] SQL injection UNION attack — retrieving data from other tables
- [ ] SQL injection UNION attack — retrieving multiple values in a single column

#### Blind SQLi
- [ ] Blind SQL injection with conditional responses
- [ ] Blind SQL injection with conditional errors
- [ ] Visible error-based SQL injection
- [ ] Blind SQL injection with time delays
- [ ] Blind SQL injection with time delays and information retrieval
- [ ] Blind SQL injection with out-of-band interaction
- [ ] Blind SQL injection with out-of-band data exfiltration

#### Other
- [ ] SQL injection vulnerability in WHERE clause allowing retrieval of hidden data
- [ ] SQL injection vulnerability allowing login bypass
- [ ] SQL injection with filter bypass via XML encoding
- [ ] SQL injection attack — querying the database type and version (MySQL/Microsoft)
- [ ] SQL injection attack — querying the database type and version (Oracle)
- [ ] SQL injection attack — listing the database contents (non-Oracle)
- [ ] SQL injection attack — listing the database contents (Oracle)

---

### 3. Authentication Vulnerabilities

Logic flaws, 2FA bypass, password reset abuse, account takeover patterns.

- [ ] Username enumeration via different responses
- [ ] Username enumeration via subtly different responses
- [ ] Username enumeration via response timing
- [ ] Broken brute-force protection — IP block
- [ ] Username enumeration via account lock
- [ ] 2FA simple bypass
- [ ] 2FA broken logic
- [ ] 2FA bypass using a brute-force attack
- [ ] Brute-forcing a stay-logged-in cookie
- [ ] Offline password cracking
- [ ] Password reset broken logic
- [ ] Password reset poisoning via middleware
- [ ] Password brute-force via password change

---

### 4. Access Control Vulnerabilities

IDOR mastery is non-negotiable.

- [ ] Unprotected admin functionality
- [ ] Unprotected admin functionality with unpredictable URL
- [ ] User role controlled by request parameter
- [ ] User role can be modified in user profile
- [ ] URL-based access control can be circumvented
- [ ] Method-based access control can be circumvented
- [ ] User ID controlled by request parameter
- [ ] User ID controlled by request parameter with unpredictable user IDs
- [ ] User ID controlled by request parameter with data leakage in redirect
- [ ] User ID controlled by request parameter with password disclosure
- [ ] Insecure direct object references
- [ ] Multi-step process with no access control on one step
- [ ] Referer-based access control

---

### 5. CSRF

Token validation, state parameter logic, Login CSRF, SameSite bypass.

- [ ] CSRF vulnerability with no defenses
- [ ] CSRF where token validation depends on request method
- [ ] CSRF where token validation depends on token being present
- [ ] CSRF where token is not tied to user session
- [ ] CSRF where token is tied to non-session cookie
- [ ] CSRF where token is duplicated in cookie
- [ ] SameSite Lax bypass via method override
- [ ] SameSite Strict bypass via on-site gadget
- [ ] SameSite Strict bypass via sibling domain
- [ ] SameSite Lax bypass via cookie refresh
- [ ] CSRF where Referer validation depends on header being present
- [ ] CSRF with broken Referer validation

---

## 🟡 PHASE 2 — Server Abuse & File Control

> Start thinking like someone trying to own the server.

---

### 6. Path Traversal

Directory traversal, filter bypass, encoding tricks.

- [ ] File path traversal — simple case
- [ ] File path traversal — traversal sequences blocked with absolute path bypass
- [ ] File path traversal — traversal sequences stripped non-recursively
- [ ] File path traversal — traversal sequences stripped with superfluous URL-decode
- [ ] File path traversal — validation of start of path
- [ ] File path traversal — validation of file extension with null byte bypass

---

### 7. File Upload Vulnerabilities

MIME bypass, extension bypass, web shell logic, RCE chaining.

- [ ] Remote code execution via web shell upload
- [ ] Web shell upload via Content-Type restriction bypass
- [ ] Web shell upload via path traversal
- [ ] Web shell upload via extension blacklist bypass
- [ ] Web shell upload via obfuscated file extension
- [ ] Remote code execution via polyglot web shell upload
- [ ] Web shell upload via race condition

---

### 8. SSRF

Internal network mapping, metadata service abuse, filter bypass tricks.

- [ ] Basic SSRF against the local server
- [ ] Basic SSRF against another back-end system
- [ ] SSRF with blacklist-based input filter
- [ ] SSRF with whitelist-based input filter
- [ ] SSRF with filter bypass via open redirection
- [ ] Blind SSRF with out-of-band detection
- [ ] Blind SSRF with Shellshock exploitation

---

## 🟠 PHASE 3 — Browser & Client-Side Control

---

### 9. CORS

Misconfig, origin reflection, credential leakage.

- [ ] CORS vulnerability with basic origin reflection
- [ ] CORS vulnerability with trusted null origin
- [ ] CORS vulnerability with trusted insecure protocols
- [ ] CORS vulnerability with internal network pivot attack

---

### 10. Clickjacking

UI redressing, frame-based attacks.

- [ ] Basic clickjacking with CSRF token protection
- [ ] Clickjacking with form input data prefilled from a URL parameter
- [ ] Clickjacking with a frame buster script
- [ ] Exploiting clickjacking vulnerability to trigger DOM-based XSS
- [ ] Multistep clickjacking

---

## 🔴 PHASE 4 — Application Logic & API Attacks

> High-value logic territory. This is where real-world VAPT lives.

---

### 11. API Testing

Hidden endpoints, parameter pollution, internal API discovery.

- [ ] Exploiting an API endpoint using documentation
- [ ] Exploiting unused API endpoint
- [ ] Finding and exploiting an unused API endpoint
- [ ] Exploiting a mass assignment vulnerability
- [ ] Exploiting server-side parameter pollution in a query string
- [ ] Exploiting server-side parameter pollution in a REST URL

---

### 12. OAuth Authentication Vulnerabilities

Broken auth + CSRF + redirect abuse + token logic combined.

- [ ] Authentication bypass via OAuth implicit flow
- [ ] Forced OAuth profile linking
- [ ] OAuth account hijacking via redirect_uri
- [ ] Stealing OAuth access tokens via an open redirect
- [ ] SSRF via OpenID dynamic client registration
- [ ] Stealing OAuth access tokens via a proxy page

---

### 13. Race Conditions

Requires comfort with Repeater, Turbo Intruder, timing exploitation.

- [ ] Limit overrun race conditions
- [ ] Bypassing rate limits via race conditions
- [ ] Multi-endpoint race conditions
- [ ] Single-endpoint race conditions
- [ ] Partial construction race conditions
- [ ] Exploiting time-sensitive vulnerabilities

---

### 14. NoSQL Injection

Modern injection layer.

- [ ] Detecting NoSQL injection
- [ ] Exploiting NoSQL operator injection to bypass authentication
- [ ] Exploiting NoSQL injection to extract data
- [ ] Exploiting NoSQL operator injection to extract unknown fields

---

## 🟣 PHASE 5 — Advanced & Niche

> Do these after your brain is hardened. Specialist skill enhancers, not foundation.

---

### 15. WebSockets Vulnerabilities
- [ ] Manipulating WebSocket messages to exploit vulnerabilities
- [ ] Manipulating the WebSocket handshake to exploit vulnerabilities
- [ ] Cross-site WebSocket hijacking

### 16. GraphQL API Vulnerabilities
- [ ] Accessing private GraphQL posts
- [ ] Accidental exposure of private GraphQL fields
- [ ] Finding a hidden GraphQL endpoint
- [ ] Bypassing GraphQL brute force protections
- [ ] Performing CSRF exploits over GraphQL

### 17. Prototype Pollution
- [ ] DOM XSS via client-side prototype pollution
- [ ] DOM XSS via an alternative prototype pollution vector
- [ ] Client-side prototype pollution via flawed sanitization
- [ ] Client-side prototype pollution in third-party libraries
- [ ] Client-side prototype pollution via browser APIs
- [ ] Privilege escalation via server-side prototype pollution
- [ ] Detecting server-side prototype pollution without polluted property reflection
- [ ] Bypassing flawed input filters for server-side prototype pollution
- [ ] Remote code execution via server-side prototype pollution

### 18. Web Cache Deception
- [ ] Exploiting path mapping for web cache deception
- [ ] Exploiting path delimiters for web cache deception
- [ ] Exploiting origin server normalization for web cache deception
- [ ] Exploiting cache server normalization for web cache deception
- [ ] Exploiting exact-match cache rules for web cache deception

### 19. Web LLM Attacks
- [ ] Exploiting LLM APIs with excessive agency
- [ ] Exploiting vulnerabilities in LLM APIs
- [ ] Indirect prompt injection

---

## The Rule

For every lab:
1. Solve it without hints first
2. Re-solve it from scratch
3. Modify the payload — break it differently
4. Document why it worked in the folder notes

Marking a checkbox just to move the progress bar forward is cheating yourself.

---

## Repo Structure

```
portswigger-notes/
├── README.md                  ← you are here
├── sql-injection/
│   └── notes.md
├── auth-bypass/
│   └── notes.md
├── access-control/
│   └── notes.md
├── csrf/
│   └── notes.md
├── path-traversal/
│   └── notes.md
├── file-upload/
│   └── notes.md
├── ssrf/
│   └── notes.md
├── cors/
│   └── notes.md
├── clickjacking/
│   └── notes.md
├── api-testing/
│   └── notes.md
├── oauth/
│   └── notes.md
├── race-conditions/
│   └── notes.md
├── nosql-injection/
│   └── notes.md
└── advanced/
    └── notes.md
```
