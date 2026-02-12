# 🔐 Vulnerability Assessment Report  
## Cyber Security Internship – Future Interns (2026)

---

## 🎯 Target Website
http://testphp.vulnweb.com/

---

## 📌 Engagement Overview

A structured, read-only vulnerability assessment was conducted to evaluate publicly exposed services, HTTP security configuration, and session management controls.

The objective of this assessment was to:

- Identify publicly accessible services
- Evaluate browser-level security mechanisms
- Assess session cookie configuration
- Classify risks using business-friendly impact analysis
- Provide actionable remediation guidance

All testing was conducted using passive, non-intrusive techniques.

---

# 📊 Executive Summary

> 🔴 **Overall Risk Level: HIGH**
>
> The assessment identified configuration weaknesses that significantly increase exposure to client-side attacks and session compromise risks.

| Category | Status |
|----------|--------|
| Open Services | 1 (HTTP – nginx 1.19.0) |
| Critical Security Headers | Not Implemented |
| Session Cookie Protection | Weak Configuration |
| HTTPS Enforcement | Not Enabled |

While public HTTP exposure is expected, the absence of security headers and improper cookie settings considerably weaken the website’s defensive posture.

---

# 🔍 Technical Findings

---

## 🔹 Finding 01 – Public Service Exposure (Low)

### Observation
- Port 80 open
- Service: nginx 1.19.0
- Hosted on AWS EC2 infrastructure

### Risk Explanation
Public service version disclosure may assist attackers in targeted reconnaissance and vulnerability identification.

### Recommendation
- Keep nginx updated to latest stable version
- Reduce unnecessary server banner disclosure
- Implement a Web Application Firewall (WAF)

### 📷 Evidence – Nmap Scan

![Nmap Scan](screenshots/nmap1.png)

---

## 🔹 Finding 02 – Missing Security Headers (High)

### Missing Security Headers
- Content-Security-Policy (CSP)
- X-Frame-Options
- X-Content-Type-Options
- Referrer-Policy
- Permissions-Policy

### Risk Impact
The absence of critical security headers increases exposure to:

- Clickjacking attacks
- Cross-Site Scripting (XSS)
- MIME-type sniffing
- Browser feature abuse
- Data leakage via referrer headers

Additionally, the website operates over HTTP without enforced HTTPS, increasing susceptibility to Man-in-the-Middle (MITM) attacks.

### Recommendation
- Enforce HTTPS with valid SSL/TLS certificate
- Implement a strict Content-Security-Policy
- Enable X-Frame-Options (DENY or SAMEORIGIN)
- Enable X-Content-Type-Options (nosniff)
- Configure Referrer-Policy and Permissions-Policy
- Regularly validate header configuration

### 📷 Evidence – Security Headers Report

![Security Headers](screenshots/Headers_Checking.png)

---

## 🔹 Finding 03 – Insecure Session Cookie Configuration (High)

### Cookie Identified
- Name: login
- Secure Flag: Not Enabled
- HttpOnly Flag: Not Enabled
- SameSite Attribute: Not Set
- Protocol: HTTP

### Risk Impact
Improper cookie configuration significantly increases risk of:

- Session hijacking
- XSS-based cookie theft
- Man-in-the-Middle interception
- Cross-site request forgery (CSRF)

Without Secure and HttpOnly flags, session integrity cannot be reliably protected.

### Recommendation
- Enforce HTTPS across the entire application
- Enable Secure flag for all session cookies
- Enable HttpOnly to prevent JavaScript access
- Configure SameSite=Strict or Lax
- Implement secure session timeout policies

### 📷 Evidence – Cookie Configuration

![Cookie Analysis](screenshots/dev_cookies.png)

---

# 🛠 Tools Used

- Nmap (Port & Service Exposure Analysis)
- Browser Developer Tools
- SecurityHeaders.com
- Manual Configuration Review

---

# ⚖ Scope & Ethical Statement

This assessment was conducted under the following constraints:

- Public-facing pages only
- Passive security analysis
- No exploitation attempts
- No brute-force or denial-of-service testing
- No data extraction or manipulation

All testing adhered to responsible security auditing principles.

---

# 📈 Final Security Assessment

**Overall Security Posture: HIGH RISK**

Although the application exposes only one public service, critical configuration weaknesses in browser security controls and session management substantially increase attack surface.

Immediate remediation is strongly recommended to:

- Protect user sessions
- Strengthen browser-level defenses
- Reduce client-side attack exposure
- Improve overall security posture
