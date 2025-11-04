**Project:** ISO 27001 Mock Risk Assessment 
**Company:** Gulf Digital Trust Bank 
**Application:** "Online Loan Application Portal" 
**Date:** 14-05-2025
**Assessor:** Sameer basha - GRC Analyst


**Executive Summary**
A mock risk assessment, aligned with ISO 27001 principles, was conducted on the new "Online Loan Application Portal." The assessment identified 11 key vulnerabilities in the application's design and supporting infrastructure.

Of these, 5 were rated as "Critical," primarily related to a lack of encryption, weak authentication, and known attack vectors (SQLi). These findings represent a severe and immediate risk of a data breach, which could lead to significant financial loss and regulatory penalties from the CBUAE.

This report outlines the findings and provides clear recommendations for remediation.

**Risk Assessment Register**
The following table details all identified vulnerabilities, their analysis, and the recommended controls.

| ID | Vulnerability (The "Threat") | Likelihood | Impact | Risk Level | Recommendation (The "Control") | Control Type |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **001** | Weak password policy allowed. | **High** | **Critical** | **Critical** | Enforce a strong password policy (14+ chars, complexity) and mandate Multi-Factor Authentication (MFA). | Technical |
| **002** | No Multi-Factor Authentication (MFA). | **High** | **Critical** | **Critical** | (Covered by ID 001) Implement a risk-based MFA solution for all customer logins. | Technical |
| **003** | No data encryption in the database. | **Medium** | **Critical** | **Critical** | Encrypt all "Strictly Confidential" data at rest in the database using AES-256 encryption. | Technical |
| **004** | Data sent in plaintext (No HTTPS). | **High** | **High** | **High** | Enforce HTTPS (SSL/TLS) across the entire application to encrypt all data in transit. | Technical |
| **005** | SQL Injection vulnerability. | **Medium** | **Critical** | **Critical** | Use parameterized queries (prepared statements) in the application code to prevent SQLi. | Technical |
| **006** | Default admin accounts ("admin/admin"). | **High** | **Critical** | **Critical** | Change all default passwords and disable or rename default administrator accounts immediately. | Technical |
| **007** | No Web Application Firewall (WAF). | **High** | **High** | **High** | Implement a WAF to protect the application from common web attacks (like SQLi, XSS). | Technical |
| **008** | Detailed error messages. | **High** | **Medium** | **High** | Use generic error messages (e.g., "Invalid username or password") for all login failures. | Technical |
| **009** | Out-of-date server software. | **High** | **High** | **High** | Implement a formal patch management process. All servers must be patched within 30 days of a critical update. | Administrative |
| **010** | No access logging. | **High** | **High** | **High** | Enable detailed access and error logging. Forward all logs to a central SIEM for monitoring. | Technical |
| **011** | No secure coding training for developers. | **High** | **High** | **High** | Mandate annual secure coding training (e.g., OWASP Top 10) for all development staff. | Administrative |


**Key Recommendations & Next Steps**
Based on the 5 Critical risks identified, the following actions must be prioritized before the application is launched:

**Remediate ID 001 & 002**: Enforce strong passwords and implement MFA for all customer accounts.

**Remediate ID 003:** Apply AES-256 encryption to the database fields storing customer PII and financial data.

**Remediate ID 005:** All database queries must be re-coded to use parameterized statements to prevent SQL Injection.

**Remediate ID 006:** The default administrator accounts for the portal must be changed or disabled.
