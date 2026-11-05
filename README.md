# PortSwigger Web Security Academy – Solved Labs

![Total Labs Solved](https://img.shields.io/badge/Total_Labs_Solved-3-blue)
![Level](https://img.shields.io/badge/Level-Apprentice-green)
![Status](https://img.shields.io/badge/Status-Learning-orange)

This repository documents my journey through [PortSwigger Web Security Academy](https://portswigger.net/web-security).

My goal is to develop practical web application security and penetration testing skills by completing hands-on labs, understanding vulnerabilities, and documenting my findings.

## 🎯 Learning Goals

- Understand common web application vulnerabilities.
- Develop practical penetration testing skills.
- Learn to use Burp Suite effectively.
- Understand how vulnerabilities work and how to prevent them.
- Progress from Apprentice to Practitioner and Expert labs.

## 📊 Progress Overview

| Level | Completed |
|---|---:|
| Apprentice | 3 |
| Practitioner | 0 |
| Expert | 0 |
| **Total** | **3** |

## 📚 Categories Covered

- **SQL Injection:** 3 completed labs

## 🛠️ Tools Used

- Burp Suite Community Edition
- Kali Linux
- PortSwigger Web Security Academy
- VirtualBox

## 📂 Repository Structure

```text
portswigger-labs-tracker/
│
├── README.md
│
├── SQL-Injection/
│   ├── lab-01-hidden-data.md
│   ├── lab-02-login-bypass.md
│   └── lab-03-oracle-database-version.md
│
└── Screenshots/
```

## 🧪 Solved Labs

| No. | Topic | Lab Title | Difficulty | Status |
|---|---|---|---|---|
| 01 | SQL Injection | Retrieving Hidden Data | Apprentice | ✅ Solved |
| 02 | SQL Injection | Login Bypass | Apprentice | ✅ Solved |
| 03 | SQL Injection | Querying Database Version on Oracle | Apprentice | ✅ Solved |

## 📝 Lab Writeups

Detailed reports explain the vulnerability, testing process, payloads, results, and lessons learned.

- [Lab 01 – SQL Injection: Retrieving Hidden Data](SQL-Injection/lab-01-hidden-data.md)
- [Lab 02 – SQL Injection: Login Bypass](SQL-Injection/lab-02-login-bypass.md)
- [Lab 03 – SQL Injection: Querying Database Version on Oracle](SQL-Injection/lab-03-oracle-database-version.md)

## 📖 Key Concepts Learned

- SQL injection in a WHERE clause.
- How to intercept HTTP requests using Burp Suite.
- How to modify requests using Repeater.
- How SQL conditions can be manipulated.
- How SQL comments can bypass login authentication.
- How UNION-based SQL injection works.
- How to identify the number of columns using ORDER BY.
- How to retrieve Oracle database version information.
- Why parameterized queries help prevent SQL injection.

## ⚠️ Disclaimer

All practical security testing documented in this repository is performed in authorized learning environments, such as PortSwigger Web Security Academy.

---

**One lab at a time. One step closer to becoming a cybersecurity professional. 🚀**
