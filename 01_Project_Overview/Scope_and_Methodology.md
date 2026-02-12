# Scope & Methodology

## Engagement Overview

This Vulnerability Assessment was conducted as part of a Cyber Security Internship engagement.

The objective was to evaluate publicly accessible security posture using non-intrusive, read-only techniques.

The assessment simulates a real-world security consulting scenario.

---

## Target System

Website: http://testphp.vulnweb.com/  
Hosting Environment: Amazon Web Services (EC2)

---

## Scope of Testing

### In-Scope

- Public-facing web pages
- HTTP service exposure
- Server banner information
- Security header configuration
- Cookie attributes
- Client-side security controls

### Out of Scope

- Login bypass attempts
- Credential brute-forcing
- Denial-of-Service testing
- Exploitation of identified vulnerabilities
- Data extraction or manipulation
- Any intrusive testing techniques

---

## Testing Methodology

The assessment followed a structured approach:

### Phase 1 – Reconnaissance
- Identified open ports and exposed services using Nmap.
- Verified hosting environment and publicly exposed service banners.

### Phase 2 – Configuration Review
- Analyzed HTTP response headers.
- Evaluated browser security header implementation.
- Reviewed session cookie configuration.

### Phase 3 – Risk Classification
- Categorized findings as Low / Medium / High.
- Assessed business impact.
- Provided remediation recommendations.

---

## Tools Used

- Nmap (Port & Service Analysis)
- Browser Developer Tools
- SecurityHeaders.com (Header Evaluation)
- Manual Configuration Review

---

## Ethical Statement

All testing was conducted using passive and non-destructive techniques.

No exploitation attempts were performed.

This assessment strictly adhered to responsible disclosure and ethical security practices.
