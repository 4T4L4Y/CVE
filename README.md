## My Published CVEs

| CVE ID | Vendor / Product | Vulnerability Type | CVSS Score | Severity | Official Reference |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **CVE-2026-12694** | Vimesoft's Enterprise Video Platform | Missing Authorization | 9.1 | ![Critical](https://img.shields.io/badge/-Critical-red) | [NVD Link](https://nvd.nist.gov/vuln/detail/CVE-2026-12694) / [CVE.ORG](https://www.cve.org/CVERecord?id=CVE-2026-12694)|
| **CVE-2026-12693** | Vimesoft's Enterprise Video Platform | IDOR | 9.4 | ![Critical](https://img.shields.io/badge/-Critical-red) | [NVD Link](https://nvd.nist.gov/vuln/detail/CVE-2026-12693) / [CVE.ORG](https://www.cve.org/CVERecord?id=CVE-2026-12693)|
| **CVE-2026-12692** | Vimesoft's Enterprise Video Platform  | Improper Authentication | 9.8 | ![Critical](https://img.shields.io/badge/-Critical-red) | [NVD Link](https://nvd.nist.gov/vuln/detail/CVE-2026-12692) / [CVE.ORG](https://www.cve.org/CVERecord?id=CVE-2026-12692)|
| **CVE-2026-12691** | Vimesoft's Enterprise Video Platform | Authentication Bypass  | 7.5 | ![High](https://img.shields.io/badge/-High-orange) | [NVD Link](https://nvd.nist.gov/vuln/detail/CVE-2026-12691) / [CVE.ORG](https://www.cve.org/CVERecord?id=CVE-2026-12691)|
| **CVE-2025-5997** | Beamsec PhishPro | Incorrect Use of Privileged APIs | 8.8 | ![High](https://img.shields.io/badge/-High-orange) | [NVD Link](https://nvd.nist.gov/vuln/detail/CVE-2025-5997) / [CVE.ORG](https://www.cve.org/CVERecord?id=CVE-2025-5997) |
| **CVE-2024-5619** | PruvaSoft Informatics Apinizer Management Console | Authorization Bypass Through User-Controlled Key | 9.6 | ![Critical](https://img.shields.io/badge/-Critical-red) | [NVD Link](https://nvd.nist.gov/vuln/detail/CVE-2024-5619) / [CVE.ORG](https://www.cve.org/CVERecord?id=CVE-2024-5619) |
| **CVE-2024-5620** | PruvaSoft Informatics Apinizer Management Console | Authentication Bypass | 6.5 | ![Medium](https://img.shields.io/badge/-Medium-yellow) | [NVD Link](https://nvd.nist.gov/vuln/detail/CVE-2024-5620) / [CVE.ORG](https://www.cve.org/CVERecord?id=CVE-2024-5620)|

## Vulnerability Details & Technical Summaries

### [CVE-2025-5997] Beamsec PhishPro - Privilege Escalation & Information Disclosure
**Overview:** Discovered a critical access control flaw within the application's user management functionality or API endpoints. 

**Technical Detail:** The system failed to properly validate authorization levels when requesting user data. An attacker authenticated with standard, low-level user privileges could exploit this vulnerability to query and access the sensitive data of other users. 

**Impact:** This flaw allowed unauthorized access to the password information of any user on the system, including administrative accounts. It presents a severe risk of complete system compromise through vertical privilege escalation.

### [CVE-2024-5619] PruvaSoft Apinizer - Insecure Direct Object Reference (IDOR)
**Overview:** Identified an Authorization Bypass vulnerability caused by the insecure handling of user-controlled keys, specifically project ID values.

**Technical Detail:** The application did not sufficiently verify if the user requesting a project download had the correct permissions for that specific `Project ID`. By intercepting the HTTP request and manipulating the ID parameter, authorization checks could be completely bypassed.

**Impact:** An attacker could systematically iterate through project IDs to forcefully download arbitrary project files and configurations belonging to other users or organizations, leading to a massive exposure of sensitive data and source code.

### [CVE-2024-5620] PruvaSoft Apinizer - Improper Access Control on Registration Endpoint
**Overview:** Discovered a business logic and access control flaw where backend API endpoints were not properly synchronized with frontend security configurations.

**Technical Detail:** Although the user registration feature was explicitly disabled and hidden on the application's frontend UI, the underlying backend registration API endpoint remained active and lacked proper authorization checks. 

**Impact:** An attacker could craft and send direct POST requests to the hidden API endpoint to successfully register a new user account. This allowed unauthorized threat actors to provision themselves valid credentials and gain unwarranted initial access to the internal system environment.

## Contact
- **LinkedIn:** [linkedin.com/in/musatalayy](https://linkedin.com/in/musatalayy)
- **Mail** musa.atalayy@outlook.com
