# 🔐 Vulnerability Assessment Report  
## Cyber Security Internship – Future Interns (2026)

---

## 🎯 Target Website
http://testphp.vulnweb.com/

---

## 📌 Engagement Overview
A structured, read-only vulnerability assessment was conducted to evaluate publicly exposed services, browser security configuration, and session management practices.

This assessment follows ethical security auditing principles.

---

# 📊 Executive Summary

| Category | Result |
|----------|--------|
| Open Services | 1 (HTTP) |
| Security Headers | Missing Critical Headers |
| Session Security | Misconfigured |
| Overall Risk Level | **HIGH** |

The website demonstrates configuration-level weaknesses that may expose users to client-side attacks and session compromise.

---

# 🔍 Technical Findings

---

## 🔹 Finding 01 – Public Service Exposure (Low)

**Observation**
- Port 80 open
- Service: nginx 1.19.0
- Hosted on AWS EC2

**Risk**
Exposed service version may assist attackers in targeted reconnaissance.

**Recommendation**
- Keep nginx updated
- Minimize banner disclosure

---

## 🔹 Finding 02 – Missing Security Headers (High)

**Missing Headers**
- Content-Security-Policy
- X-Frame-Options
- X-Content-Type-Options
- Referrer-Policy
- Permissions-Policy

**Impact**
- Clickjacking
- XSS exposure
- MIME sniffing attacks
- Browser-level protection bypass

**Recommendation**
- Implement HTTPS
- Configure all required security headers

---

## 🔹 Finding 03 – Insecure Session Cookie (High)

**Cookie Name:** login  
- Secure: No  
- HttpOnly: No  
- SameSite: Not Set  

**Impact**
- Session hijacking
- XSS cookie theft
- MITM interception

**Recommendation**
- Enable Secure flag
- Enable HttpOnly
- Configure SameSite attribute
- Enforce HTTPS

---

# 📷 Evidence

(Screenshots will be displayed below)

---

# 🛠 Tools Used

- Nmap
- Browser Developer Tools
- SecurityHeaders.com
- Manual configuration analysis

---

# ⚖ Scope & Ethics

- Public-facing pages only
- Passive testing only
- No exploitation performed
- No brute force or DoS testing

---

# 📈 Final Security Assessment

Overall Security Posture: **HIGH RISK**

Immediate remediation is recommended to improve browser-level defenses and session integrity.
