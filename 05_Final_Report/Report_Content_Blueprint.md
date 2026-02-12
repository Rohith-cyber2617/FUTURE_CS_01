# Vulnerability Assessment Report
Cyber Security Internship – Future Interns (2026)

---

## 1. Cover Page
- Report Title: Vulnerability Assessment Report
- Target: testphp.vulnweb.com
- Prepared By: ROHITH RACHAPUDI

---

## 2. Executive Summary

This report presents the results of a structured, read-only vulnerability assessment conducted on a publicly accessible web application.

The objective was to identify security weaknesses, classify risks, and provide clear remediation recommendations.

Overall Security Rating: High Risk

---

## 3. Scope of Engagement

- Public-facing web pages only
- Passive security assessment
- No exploitation performed
- No intrusive testing techniques used

---

## 4. Methodology

Phase 1 – Reconnaissance  
Phase 2 – Configuration Review  
Phase 3 – Risk Classification & Reporting  

Tools Used:
- Nmap
- Browser DevTools
- SecurityHeaders.com

---

## 5. Summary of Findings

| Finding ID | Title | Risk |
|------------|-------|------|
| 01 | Public Service Exposure | Low |
| 02 | Missing Security Headers | High |
| 03 | Insecure Session Cookie Configuration | High |

---

## 6. Detailed Findings

### Finding 01 – Public Service Exposure
Include:
- Description
- Risk Explanation
- Evidence Screenshot
- Remediation

---

### Finding 02 – Missing Security Headers
Include:
- Missing headers list
- SecurityHeaders grade
- Business impact explanation
- Remediation steps

---

### Finding 03 – Insecure Session Cookie Configuration
Include:
- Cookie attributes
- Risk explanation
- Business impact
- Remediation

---

## 7. Risk Prioritization Recommendation

Immediate Action:
- Implement HTTPS
- Configure security headers
- Secure session cookies

Medium-Term:
- Continuous vulnerability monitoring
- Regular patch management

---

## 8. Conclusion

The identified vulnerabilities indicate configuration-level weaknesses that increase exposure to common web-based attacks.

Immediate remediation is recommended to strengthen the website’s security posture and protect user data.
