# Lab 05 – SQL Injection: Listing the Database Contents on Non-Oracle Databases

**Platform:** PortSwigger Web Security Academy  
**Category:** SQL Injection  
**Vulnerability:** UNION-based SQL Injection  
**Status:** Solved ✅

## Objective

The objective was to exploit a SQL injection vulnerability to discover the database structure, identify tables and columns, retrieve user records, and log in as the administrator.

## Steps Performed

### 1. Identify the number of columns

I tested a UNION SELECT payload to determine how many columns the original query returned.

```sql
'+UNION+SELECT+'abc','def'--
```

The payload worked, confirming that the query returned two columns.

### 2. Discover database tables

I queried `information_schema.tables` to identify the tables in the database.

```sql
'+UNION+SELECT+table_name,NULL+FROM+information_schema.tables--
```

This revealed the users table.

### 3. Discover table columns

I queried `information_schema.columns` to discover the column names in the users table.

```sql
'+UNION+SELECT+column_name,NULL+FROM+information_schema.columns+WHERE+table_name='USERS_TABLE'--
```

I identified the username and password columns.

### 4. Retrieve user records

I used the discovered table and column names to retrieve the user records.

```sql
'+UNION+SELECT+USERNAME_COLUMN,PASSWORD_COLUMN+FROM+USERS_TABLE--
```

### 5. Log in as administrator

I used the administrator credentials retrieved in the lab to log in successfully.

## Result

**Lab successfully solved!**

I demonstrated how UNION-based SQL injection can expose database structure and sensitive records.

## What I Learned

- How UNION-based SQL injection works.
- How to enumerate database tables.
- How to discover column names.
- How to use `information_schema` to inspect database structure.
- How database information can be exposed through vulnerable queries.

## Prevention

- Use parameterized queries and prepared statements.
- Never directly concatenate user input into SQL queries.
- Apply proper input validation.
- Follow the principle of least privilege.
- Avoid exposing sensitive database information.

**Note:** Actual lab credentials and session tokens are intentionally excluded from this public write-up.
