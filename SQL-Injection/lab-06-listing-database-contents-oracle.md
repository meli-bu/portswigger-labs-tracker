# Lab 06: SQL Injection – Listing the Database Contents on Oracle

## Lab Information

- **Platform:** PortSwigger Web Security Academy
- **Category:** SQL Injection
- **Difficulty:** Apprentice
- **Vulnerability:** SQL Injection
- **Database:** Oracle
- **Status:** In Progress / Solved (confirm final completion)

## 1. Objective

The objective of this lab is to exploit a SQL injection vulnerability to identify database tables and columns, retrieve user credentials, and access the administrator account.

## 2. Identifying the Injection Point

I opened the product category filter and intercepted the HTTP request using Burp Suite.

Original request:

```http
GET /filter?category=Lifestyle HTTP/2
```

The `category` parameter was selected as the injection point.

## 3. Determining the Number of Columns

I used a UNION SELECT statement to determine the number of columns returned by the original query.

Payload:

```sql
Lifestyle'+UNION+SELECT+NULL,NULL+FROM+dual--
```

The request returned HTTP 200, indicating that the query was accepted.

## 4. Identifying Compatible Data Types

Next, I tested whether both columns could return text values.

Payload:

```sql
Lifestyle'+UNION+SELECT+'abc','def'+FROM+dual--
```

The request returned HTTP 200, confirming that both columns accepted text data.

## 5. Discovering Database Tables

Because the database was Oracle, I queried the `all_tables` data dictionary view to identify available tables.

Payload:

```sql
Lifestyle'+UNION+SELECT+table_name,NULL+FROM+all_tables--
```

Among the returned table names, I identified:

- `USERS_DTKRKT`
- `SDO_PREFERRED_OPS_USER`

The `USERS_DTKRKT` table appeared to contain the user account information.

## 6. Discovering Table Columns

I queried the Oracle `all_tab_columns` view to identify the columns belonging to the users table.

Payload:

```sql
Lifestyle'+UNION+SELECT+column_name,NULL+FROM+all_tab_columns+WHERE+table_name='USERS_DTKRKT'--
```

The relevant columns discovered were:

- `USERNAME_HPACZC`
- `PASSWORD_VBWGRB`

## 7. Retrieving User Credentials

After discovering the table and its columns, I used another UNION SELECT statement to retrieve the username and password records.

Payload:

```sql
Lifestyle'+UNION+SELECT+USERNAME_HPACZC,PASSWORD_VBWGRB+FROM+USERS_DTKRKT--
```

The query retrieves usernames and their corresponding passwords from the identified table.

Credentials are intentionally not included in this public write-up.

## 8. Conclusion

This lab demonstrates how SQL injection can be used to enumerate an Oracle database and retrieve sensitive information.

I practiced:

- Determining the number of columns using UNION SELECT.
- Identifying compatible data types.
- Querying Oracle's `all_tables` view.
- Querying Oracle's `all_tab_columns` view.
- Retrieving records from a discovered database table.

## 9. Tools Used

- Burp Suite Community Edition
- PortSwigger Web Security Academy
- Oracle SQL syntax

## 10. Key Learning

Oracle databases provide data dictionary views that can reveal information about database tables and columns. When an application is vulnerable to SQL injection, attackers may abuse these views to discover database structure and access sensitive records.

**Security lesson:** Applications should use parameterized queries and properly validate database input to prevent SQL injection.
