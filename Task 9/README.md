# SQL Injection Exploitation - DVWA

## Objective
The goal of this task was to set up a vulnerable web application (DVWA) and perform an SQL Injection (SQLi) attack to exploit it. This helps understand how SQLi works and how to mitigate it.

---

## Tools Used
- **Kali Linux**
- **DVWA (Damn Vulnerable Web Application)**
- **Firefox Browser (for accessing DVWA locally)**

---

## Setup Steps

1. **Installed DVWA**  
   Command used:
   ```bash
   sudo apt install dvwa
   ```

2. **Started DVWA**
   ```bash
   dvwa-start
   ```

3. **Accessed in browser**  
   Opened:
   ```
   http://127.0.0.1:42001
   ```

4. **Navigated to**
   
   `SQL Injection` module from the left panel.

---

## SQL Injection Performed

- **Tested User ID with SQL Injection:**
  ```
  1' OR '1'='1
  
  &
  
  1
  ```

- **Result:**  
  Successfully bypassed the user ID filter and retrieved multiple users from the database including:
  ```
  For 1' OR '1'='1
  ID: 1' OR '1'='1
  First name: admin
  Surname: admin
  First name: Gordon
  Surname: Brown
  First name: Pablo
  Surname: Picasso
  First name: Bob
  Surname: Smith
  
  &
  
  For 1
  ID: 1
  First name: admin
  Surname: admin
  ```

---

## How It Works

The payload:
```
1' OR '1'='1
```
Breaks the SQL query logic and forces the database to always return true, retrieving all records.
```
1
```
Shows only user with ID 1

---

## How to Patch This Vulnerability

To fix SQL Injection in real applications:
- Use **prepared statements** (parameterized queries)
- Validate and sanitize all user inputs
- Limit database permissions
- Implement **Web Application Firewalls (WAF)**
- Regularly test for vulnerabilities using scanners

---

## Deliverables

- **Screenshots Provided** showing:
  - DVWA installation
  - DVWA SQL Injection module usage
  - Successful SQLi execution

- **Note:** No `.sh` script was created since the process was entirely manual via web browser.

---

## Conclusion

This exercise helped in understanding how a basic SQL injection attack works and the importance of input validation and prepared statements to secure web applications.


