# PortSwigger Web Security Academy – Solved Labs

[Total Labs](https://img.shields.io/badge/Total_Labs-5-blue) [Level](https://img.shields.io/badge/Level-Apprentice-green) [Status](https://img.shields.io/badge/Status-Learning-orange)

This repository documents my journey through **PortSwigger Web Security Academy** practical labs.

My goal is to learn web application security, understand common vulnerabilities, and develop practical penetration testing skills using Burp Suite.

## Learning Goals

- Understand common web vulnerabilities.
- Practice identifying and exploiting vulnerabilities in legal lab environments.
- Learn how to use Burp Suite effectively.
- Document my learning process and solutions.
- Improve my web application penetration testing skills.

## Progress Overview

| Level        | Completed Labs |
| ------------ | -------------- |
| Apprentice   | 5              |
| Practitioner | 0              |
| Expert       | 0              |
| **Total**    | **5**          |

## Categories Covered

| Category                   | Completed |
| -------------------------- | --------- |
| SQL Injection              | 5         |
| Cross-Site Scripting (XSS) | 0         |
| Authentication             | 0         |
| Access Control             | 0         |
| Other Vulnerabilities      | 0         |

## Tools Used

- Burp Suite Community Edition
- Kali Linux
- PortSwigger Web Security Academy
- VirtualBox
- Oracle Database and MySQL lab environments

## Repository Structure

```text
portswigger-labs-tracker/
│
├── README.md
│
├── SQL-Injection/
│   ├── lab-01-hidden-data.md
│   ├── lab-02-login-bypass.md
│   ├── lab-03-oracle-database-version.md
│   ├── lab-04-mysql-microsoft-database-version.md
│   └── lab-05-listing-database-contents.md
│
└── Screenshots/
    ├── lab-01-solved.png
    ├── lab-02-solved.png
    ├── lab-03-solved.png
    ├── lab-04-solved.png
    └── lab-05-solved.png
```

## Solved Labs

| No. | Lab Title | Difficulty | Status |
| --- | --- | --- | --- |
| 01 | SQL Injection – Retrieving Hidden Data | Apprentice | ✅ Solved |
| 02 | SQL Injection – Login Bypass | Apprentice | ✅ Solved |
| 03 | SQL Injection – Querying Database Version on Oracle | Apprentice | ✅ Solved |
| 04 | SQL Injection – Querying Database Version on MySQL and Microsoft | Apprentice | ✅ Solved |
| 05 | SQL Injection – Listing the Database Contents on Non-Oracle Databases | Apprentice | ✅ Solved |

## Lab Write-ups

1. [Lab 01 – SQL Injection: Retrieving Hidden Data](https://github.com/meli-bu/portswigger-labs-tracker/blob/main/SQL-Injection/lab-01-hidden-data.md)
2. [Lab 02 – SQL Injection: Login Bypass](https://github.com/meli-bu/portswigger-labs-tracker/blob/main/SQL-Injection/lab-02-login-bypass.md)
3. [Lab 03 – SQL Injection: Querying Database Version on Oracle](https://github.com/meli-bu/portswigger-labs-tracker/blob/main/SQL-Injection/lab-03-oracle-database-version.md)
4. [Lab 04 – SQL Injection: Querying Database Version on MySQL and Microsoft](https://github.com/meli-bu/portswigger-labs-tracker/blob/main/SQL-Injection/lab-04-mysql-microsoft-database-version.md)
5. [Lab 05 – SQL Injection: Listing the Database Contents on Non-Oracle Databases](https://github.com/meli-bu/portswigger-labs-tracker/blob/main/SQL-Injection/lab-05-listing-database-contents.md)

## Lab Screenshots

- [Lab 01 – Retrieving Hidden Data](Screenshots/lab-01-solved.png)
- [Lab 02 – Login Bypass](Screenshots/lab-02-solved.png)
- [Lab 03 – Oracle Database Version](Screenshots/lab-03-solved.png)
- [Lab 04 – MySQL and Microsoft Database Version](Screenshots/lab-04-solved.png)
- [Lab 05 – Listing Database Contents](Screenshots/lab-05-solved.png)

## Key Concepts Learned

- SQL injection in WHERE clauses.
- Boolean-based SQL injection.
- SQL injection authentication bypass.
- UNION-based SQL injection.
- Identifying the number of columns using ORDER BY.
- Retrieving database information.
- Oracle database version retrieval using `v$version`.
- MySQL database version retrieval using `@@version`.
- Enumerating database tables using `information_schema.tables`.
- Discovering table columns using `information_schema.columns`.
- Extracting database records through UNION-based SQL injection.
- SQL comments and query manipulation.
- Preventing SQL injection using parameterized queries.

## Disclaimer

All practical exercises documented here were performed in authorized PortSwigger Web Security Academy lab environments for educational purposes.

## Learning Journey

**Learning cybersecurity one vulnerability at a time.**

Stay curious. Keep practicing. Keep learning. 🔐
