# Lab 01: SQL Injection — Hidden Data

## Lab Information
- Platform: PortSwigger Web Security Academy
- Topic: SQL Injection
- Difficulty: Apprentice
- Status: Solved
- Tool: Burp Suite Community Edition

## Objective
Retrieve hidden products that are not normally displayed on the website.

## Vulnerability
SQL Injection (SQLi).

SQL injection happens when an application incorrectly handles user input in an SQL query, allowing an attacker to change the query's logic.

## Tools Used
- Burp Suite
- Burp Proxy
- Burp Repeater

## What I Learned
1. How to intercept HTTP requests.
2. How to inspect requests using HTTP History.
3. How to send requests to Repeater.
4. How single quotes can reveal possible SQL injection.
5. How SQL comments work.
6. How Boolean conditions can manipulate SQL queries.

## Test Payload

```sql
' OR 1=1--
```

## Why It Worked

`1=1` is always TRUE.

The injected condition changed the application's database query logic and caused products from other categories to appear.

## Result
Successfully retrieved products from other categories and completed the PortSwigger lab.

## Key Lesson
Never trust user input when constructing database queries. Applications should use parameterized queries to prevent SQL injection.

## Status
SOLVED ✅
