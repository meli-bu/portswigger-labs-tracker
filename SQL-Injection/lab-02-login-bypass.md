# Lab 02 – SQL Injection: Login Bypass

## Lab Information

| Detail | Description |
|---|---|
| Platform | PortSwigger Web Security Academy |
| Category | SQL Injection |
| Difficulty | Apprentice |
| Status | Completed |
| Tool | Burp Suite Community Edition |

## Objective

Bypass the login authentication system and access the application as the administrator without knowing the administrator's password.

## Vulnerability

The login form was vulnerable to SQL injection because user input was not safely handled in the SQL query.

## Tools Used

- Burp Suite Community Edition
- Proxy
- Repeater
- PortSwigger Web Security Academy

## Steps Taken

1. Opened the lab and navigated to the login page.
2. Entered a normal test username and password.
3. Intercepted the login request using Burp Suite.
4. Sent the POST request to Repeater.
5. Observed that the normal login attempt returned `Invalid username or password`.
6. Modified the username parameter with the SQL injection payload:

   `administrator'--`

7. Sent the modified request and received:

   `HTTP/2 302 Found`

8. The response redirected to:

   `/my-account?id=administrator`

9. Repeated the injection through the browser and successfully logged in as administrator.

## SQL Injection Payload

```sql
administrator'--
```

## How It Worked

- `administrator` specifies the target username.
- `'` closes the SQL string.
- `--` comments out the remaining part of the SQL query.

This causes the password condition to be ignored, allowing the application to authenticate as administrator.

## Result

**LAB SOLVED!**

Successfully bypassed the login authentication and accessed the application as administrator without knowing the password.

## Key Lessons Learned

- Login forms can be vulnerable to SQL injection.
- SQL injection can bypass authentication.
- SQL comments can change how a query is executed.
- Burp Repeater helps test and modify HTTP requests.
- A successful response in Repeater should be confirmed through the browser when necessary.

## Prevention

- Use parameterized queries (prepared statements).
- Never build SQL queries by directly concatenating user input.
- Apply proper input handling.
- Use secure authentication practices.

## References

- [PortSwigger – SQL Injection](https://portswigger.net/web-security/sql-injection)
- [PortSwigger – Login Bypass Lab](https://portswigger.net/web-security/sql-injection/lab-login-bypass)
