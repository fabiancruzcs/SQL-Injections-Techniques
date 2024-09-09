<h1>SQL Injection Techniques</h1> 

This lab focuses on SQL injection vulnerabilities in the "AltoroMutual" demo site. By exploiting these vulnerabilities, particularly in the login functionality, I gained unauthorized access to the admin account without needing a password. Through this hands-on experience, I learned about cybersecurity risks associated with insecure web applications and the importance of secure coding practices.

### Contents
- <a href="https://github.com/fabiancruzcs/SQL-Injections-Techniques/blob/main/README.md#in-band-error-based-sql-injection-classic-sqli---thought-process">In-band Error-based SQL Injection (Classic SQLi)</a> </br>
- In-band Union-based SQL Injection (Classic SQLi) - To be added

<h2>Languages and Utilities Used</h2>

| Used          | Description                                     |
|---------------|-------------------------------------------------|
| SQL           | Language for managing relational databases.     |
| [https://altoro.testfire.net/](https://altoro.testfire.net/) | Demo site for testing web security.             |

## In-band Error-based SQL Injection (Classic SQLi) - Thought Process

In the first part of the lab, I checked how the website handles security. I tested it by using admin' as the username on the login page. This caused a syntax error, showing that the site might be vulnerable to SQL injection attacks.

Next, I tried a basic SQL injection by entering `admin' --` as the username. The `--` part comments out the rest of the SQL query, letting me bypass the password check.

Then, I tested another technique with `admin' OR '1'='1`. This tricked the system into thinking the condition was always true, so it logged me in. Here’s why this worked:

Condition A: The username `admin` exists in the database (✅True) </br>
Condition B: `'1'='1` is always true (✅True) </br>
Condition C: The password doesn’t need to be checked (❌N/A) </br>

So, by meeting the first two conditions, I was able to gain access without needing a valid password. </br>

<p align="center">
Behind the scenes:
<p align="center">
<img src="https://imgur.com/v4fwGDV.png" height="80%" width="100%" alt="Classic-SQLi-Lab"/>

<h2>Exploit Walk-Through:</h2>

<p align="center">
Login failure, typed <b>admin</b> as common username: <br/>
<p align="center">
<img src="https://imgur.com/BlGWiwp.png" height="80%" width="80%" alt="Classic-SQLi-Lab"/>
<br />
<br />
Testing login functionality with username <b>admin'</b>. Returned syntax error indicating a potential vulnerability:  <br/>
<p align="center">
<img src="https://imgur.com/fF7oEnI.png" height="80%" width="80%" alt="Classic-SQLi-Lab"/>
<br />
<br />
Simple SQLi payload <b>admin' --</b>: <br/>
<p align="center">
<img src="https://imgur.com/XbBdljF.png" height="80%" width="80%" alt="Classic-SQLi-Lab"/>
<br />
<br />
Payload variation <b>admin' OR '1'='1</b>:  <br/>
<p align="center">
<img src="https://imgur.com/vqooZnT.png" height="80%" width="80%" alt="Classic-SQLi-Lab"/>
<br />
<br />
Access granted:  <br/>
<p align="center">
<img src="https://imgur.com/7NXhuiH.png" height="80%" width="80%" alt="Classic-SQLi-Lab"/>
<br />
<br />
</p>
