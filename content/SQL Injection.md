## **1. Introduction**

**SQL Injection (SQLi)** is a type of security vulnerability that occurs when an attacker is able to manipulate a Structured Query Language (SQL) query by injecting malicious input into a web application. It typically results from improper input validation and poor coding practices, allowing unauthorized access to a database.

### **2. How It Works**

Web applications often use SQL queries to interact with databases. If user inputs are directly included in these queries without proper sanitization or parameterization, an attacker can modify the query structure to bypass authentication, read or delete data, or execute administrative operations on the database.
### **3. Example: SQL Injection**

**Vulnerability:**
```sql
SELECT * FROM users WHERE username = 'admin' AND password = '123';
```
**Attack Input:**
```vb
username: admin' -- 
```
**Resulting Query:**
```sql
SELECT * FROM users WHERE username = 'admin' -- ' AND password = '123';
```
**Effect:**
- Bypasses password check by commenting out the rest of the query.

### **4. Types of SQL Injection**

- **Classic SQLi** – Simple injection into query statements.
- **Blind SQLi** – No visible result; relies on observing application behavior.
- **Error-Based SQLi** – Uses SQL errors to extract information.
- **Union-Based SQLi** – Uses `UNION` to combine results from multiple queries.
- **Time-Based SQLi** – Uses delay commands to infer information from database response times.

### **5. Impact**

- Bypassing login authentication    
- Accessing, modifying, or deleting database content
- Executing administrative operations on the database
- Extracting sensitive information such as usernames and passwords

### **6. Prevention Techniques**

- **Use Prepared Statements (Parameterized Queries)**
- **Validate and sanitize user input**
- **Use ORM (Object Relational Mapping) frameworks**
- **Limit database user privileges**
- **Use Web Application Firewalls (WAFs)**

### **7. Conclusion**

SQL Injection remains one of the most dangerous and common vulnerabilities in web applications. Proper coding practices, input validation, and secure database handling are essential to defend against such attacks and protect sensitive information.