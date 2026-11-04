# Lab 01 – SQL Injection: Retrieving Hidden Data

## Lab Information

| Detail | Description |
|---|---|
| Platform | PortSwigger Web Security Academy |
| Vulnerability | SQL Injection |
| Difficulty | Apprentice |
| Status | Completed |
| Tool | Burp Suite Community Edition |

## 1. Objective

The objective was to exploit a SQL injection vulnerability in a product category filter to retrieve products that were hidden by the application's database query.

## 2. Understanding the Vulnerability

SQL Injection happens when an application includes user input directly in an SQL query without safely handling it.

An attacker may manipulate the query to access data they should not normally see.

## 3. Tools Used

- Burp Suite Community Edition
- Burp Proxy
- Burp Repeater
- PortSwigger Web Security Academy

## 4. Testing Process

1. Opened the assigned PortSwigger lab.
2. Used Burp Suite to intercept the category filter request.
3. Sent the request to Burp Repeater.
4. Tested a single quote (`'`) and observed an Internal Server Error.
5. Tested the SQL comment marker (`--`).
6. Used a Boolean condition to manipulate the query.
7. Observed products from other categories in the response.
8. Confirmed that the lab was successfully solved.

## 5. Payload Used

```sql
' OR 1=1--
```

### Payload Explanation

- `'` closes the original SQL string.
- `OR` adds another condition.
- `1=1` is always true.
- `--` comments out the remaining part of the SQL query in the tested database context.

The injected condition caused the query to return products beyond the selected category.

## 6. Result

<badge color="success">Successfully Solved</badge>

The application returned products from multiple categories instead of only the selected category.

This confirmed that the category parameter was vulnerable to SQL injection.

## 7. What I Learned

- How SQL injection vulnerabilities occur.
- How to inspect HTTP requests with Burp Proxy.
- How to test requests using Burp Repeater.
- How SQL Boolean conditions affect query results.
- Why applications should use parameterized queries.

## 8. Prevention

Developers can prevent this vulnerability by:

- Using parameterized queries or prepared statements.
- Avoiding direct concatenation of user input into SQL queries.
- Applying appropriate input validation.
- Using database accounts with limited privileges.

## 9. References

- [PortSwigger – SQL Injection](https://portswigger.net/web-security/sql-injection)
- [PortSwigger – SQL Injection Labs](https://portswigger.net/web-security/all-labs#sql-injection)

---

**Status:** Completed ✅
