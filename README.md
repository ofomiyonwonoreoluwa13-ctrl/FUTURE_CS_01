# FUTURE_CS_01
This repository contains Task 1 of the FUTURE Cyber Security Internship: Web Application Security Testing using OWASP ZAP, Burp Suite, and SQLMap.
Here is the rewritten version of your **Professional Security Assessment Report** in plain text (`.txt`) format. The structure and technical content have been preserved, but the language has been refined for clarity and professional tone.

---

**Professional Security Assessment Report**
**Vulnerability Assessment of DVWA Web Application**

---

**1. Executive Summary**
This security assessment focused on analyzing the Damn Vulnerable Web Application (DVWA) to identify and evaluate critical web security vulnerabilities. The goal was to replicate real-world penetration testing activities, detect potential risks, and offer remediation strategies aligned with OWASP Top 10 standards.

Three major vulnerabilities were discovered:

* **SQL Injection**
* **Cross-Site Request Forgery (CSRF)**
* **Brute Force Attacks**

If exploited in a production setting, these vulnerabilities could lead to data breaches, unauthorized system access, or full system compromise. Each issue is mapped to the corresponding OWASP Top 10 category, along with suggested remediation steps.

---

**2. Methodology & Tools**
The assessment was conducted using DVWA installed on a local virtualized environment. A combination of manual testing and automated tools was used to uncover vulnerabilities.

**Tools Utilized:**

* OWASP ZAP (Zed Attack Proxy)
* Burp Suite (Intruder, Repeater modules)
* DVWA (configured at multiple security levels)
* Kali Linux environment

**Approach:**

1. Set up the DVWA test environment and perform reconnaissance.
2. Conduct manual exploitation to simulate attacker behavior.
3. Execute automated scans and brute-force attempts.
4. Document findings with evidence and remediation guidance.

---

**3. Findings**

**3.1 SQL Injection**
**Description:**
A SQL Injection vulnerability was found, allowing attackers to manipulate backend queries and extract sensitive data.

**Impact:** High
Potential compromise of the database and leakage of user credentials.

**Evidence:**
Screenshots show successful SQL injection revealing user information.

**Remediation:**

* Use parameterized queries (prepared statements).
* Validate and sanitize user input.
* Deploy Web Application Firewalls (WAF) to detect query anomalies.

---

**3.2 Cross-Site Request Forgery (CSRF)**
**Description:**
A CSRF vulnerability allowed attackers to trigger unauthorized password changes for authenticated users.

**Impact:** High
Could result in unauthorized account modifications or privilege escalation.

**Evidence:**
Demonstrated with a crafted request that successfully reset a user’s password.

**Remediation:**

* Use anti-CSRF tokens in all sensitive forms.
* Validate request origin using proper headers.
* Require re-authentication for critical actions like password changes.

---

**3.3 Brute Force Attack**
**Description:**
The login functionality was vulnerable to brute-force attacks. Automated tools could attempt multiple login attempts without restriction.

**Impact:** Medium
Lack of rate limiting could lead to unauthorized account access.

**Evidence:**
Burp Suite Intruder successfully guessed credentials through repeated attempts.

**Remediation:**

* Enforce account lockout or rate limiting after failed login attempts.
* Require strong passwords and implement multi-factor authentication.
* Monitor login attempts for suspicious activity.

---

**4. OWASP Top 10 Mapping**

| Vulnerability      | OWASP Top 10 Category                           |
| ------------------ | ----------------------------------------------- |
| SQL Injection      | A03: Injection                                  |
| CSRF               | A05: Security Misconfiguration                  |
| Brute Force Attack | A07: Identification and Authentication Failures |

---

**5. Conclusion & Recommendations**
This assessment highlights several critical vulnerabilities present in the DVWA application, which mirror real-world security threats. SQL Injection, CSRF, and Brute Force attacks remain common vectors for compromise.

**Recommendations:**

* Follow secure coding practices based on OWASP guidelines.
* Implement layered defenses including WAFs and authentication controls.
* Conduct regular penetration testing and vulnerability scans.
* Train development teams on secure coding and the Software Development Lifecycle (SSDLC).

By addressing these vulnerabilities and applying the recommended mitigations, organizations can greatly improve their security posture and reduce the likelihood of successful cyberattacks.

---
