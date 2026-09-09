# Web Application SQL Injection Detection 
 
## Overview 
This project demonstrates SQL Injection detection in a controlled DVWA lab environment using SQLMap and web server access logs. 
 
The objective was to generate SQL injection activity, analyze the resulting HTTP requests, and identify useful indicators that can help detect automated SQL injection attempts. 
 
## Lab Environment 
- Attacker Machine: Kali Linux 
- Target Application: DVWA 
- Target URL: `http://127.0.0.1:42001` 
- Tool Used: SQLMap 
- Log File: `/var/log/dvwa/access.log` 
- Database: MySQL / MariaDB 
 
## Execution 
SQLMap was used against the DVWA SQL Injection page. 
 
Example command: 
 
```bash 
sqlmap -u "http://127.0.0.1:42001/vulnerabilities/sqli/?id=1&Submit=Submit" \
--cookie="security=low; PHPSESSID=<SESSION_ID>" \
--batch --level=3
