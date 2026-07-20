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

### [CVE-2026-12694] Vimesoft Enterprise Video Platform - Broken Access Control & Denial of Service (DoS)
**Overview:** Discovered a critical broken access control vulnerability that allows unauthorized users to access UI settings and maliciously modify core application configurations.

**Technical Detail:** The application fails to properly verify authorization levels for the UI settings endpoints. A user who has no explicit permissions to manage UI settings can still access this area and manipulate application-wide parameters. 

**Impact:** By maliciously altering essential application configurations, an unauthorized user can create a localized Denial of Service (DoS) condition. This disrupts the interface or internal logic, effectively blocking access to the application and halting services for all legitimate users.

---

### [CVE-2026-12693] Vimesoft Enterprise Video Platform - Unauthenticated Password Reset via UID (Account Takeover)
**Overview:** Discovered a critical vulnerability allowing completely unauthenticated attackers to change user passwords using publicly accessible User IDs (UIDs).

**Technical Detail:** The password modification endpoint does not enforce session authentication or require the old password for verification. An attacker only needs to supply a target user's UID and a new password. Since UIDs are not treated as sensitive secrets and can be easily harvested from public interactions (e.g., viewing channel details or reading comments on posts), the barrier to exploitation is extremely low.

**Impact:** This vulnerability allows unauthenticated actors to execute arbitrary password resets on any harvested UID, leading to targeted or widespread account takeovers and complete compromise of user accounts without any prerequisite credentials.

---

### [CVE-2026-12692] Vimesoft Enterprise Video Platform - Improper Authentication (Account Takeover)
**Overview:** Identified a critical improper authentication flaw in the password reset mechanism allowing unauthorized password modifications based solely on a known username.

**Technical Detail:** The password reset endpoint lacks proper verification mechanisms. It processes requests containing only a username and a new password without requiring the current/old password, security questions, or any temporary validation token.

**Impact:** An attacker can exploit this flaw to arbitrarily reset the password of any user simply by knowing their username. This leads to complete, unauthorized account takeover and potential compromise of the target's data and privileges.

---

### [CVE-2026-12691] Vimesoft Enterprise Video Platform - Insecure Direct Object Reference (IDOR) & Information Disclosure
**Overview:** Identified an Insecure Direct Object Reference (IDOR) vulnerability that allows unauthorized access to detailed user information within groups.

**Technical Detail:** The endpoint responsible for retrieving group user details relies solely on a "Group ID" parameter without proper authorization checks. Furthermore, these Group IDs are generated predictably in a sequential, auto-incrementing manner. 

**Impact:** An attacker can easily enumerate and brute-force the sequential Group IDs to scrape and disclose detailed, sensitive information of users across all groups in the system, leading to significant privacy violations and mass data exposure.

---

### [CVE-2025-5997] Beamsec PhishPro - Privilege Escalation & Information Disclosure
**Overview:** Discovered a critical access control flaw within the application's user management functionality or API endpoints. 

**Technical Detail:** The system failed to properly validate authorization levels when requesting user data. An attacker authenticated with standard, low-level user privileges could exploit this vulnerability to query and access the sensitive data of other users. 

**Impact:** This flaw allowed unauthorized access to the password information of any user on the system, including administrative accounts. It presents a severe risk of complete system compromise through vertical privilege escalation.

---

### [CVE-2024-5619] PruvaSoft Apinizer - Insecure Direct Object Reference (IDOR)
**Overview:** Identified an Authorization Bypass vulnerability caused by the insecure handling of user-controlled keys, specifically project ID values.

**Technical Detail:** The application did not sufficiently verify if the user requesting a project download had the correct permissions for that specific `Project ID`. By intercepting the HTTP request and manipulating the ID parameter, authorization checks could be completely bypassed.

**Impact:** An attacker could systematically iterate through project IDs to forcefully download arbitrary project files and configurations belonging to other users or organizations, leading to a massive exposure of sensitive data and source code.

---

### [CVE-2024-5620] PruvaSoft Apinizer - Improper Access Control on Registration Endpoint
**Overview:** Discovered a business logic and access control flaw where backend API endpoints were not properly synchronized with frontend security configurations.

**Technical Detail:** Although the user registration feature was explicitly disabled and hidden on the application's frontend UI, the underlying backend registration API endpoint remained active and lacked proper authorization checks. 

**Impact:** An attacker could craft and send direct POST requests to the hidden API endpoint to successfully register a new user account. This allowed unauthorized threat actors to provision themselves valid credentials and gain unwarranted initial access to the internal system environment.

## Contact
- **LinkedIn:** [linkedin.com/in/musatalayy](https://linkedin.com/in/musatalayy)
- **Mail** musa.atalayy@outlook.com
