<h1>In-band Error-based SQL Injection (Classic SQLi)</h1> 


<h2>Description</h2>
This lab focuses on SQL injection vulnerabilities in the "AltoroMutual" demo site. By exploiting these vulnerabilities, particularly in the login functionality, I gained unauthorized access to the admin account without needing a password. Through this hands-on experience, I learned about cybersecurity risks associated with insecure web applications and the importance of secure coding practices.
<br />


<h2>Thought Process</h2>

During the lab's initial phase, I examined the website's security setup systematically. By entering `admin'` as the username in the login interface, I triggered a syntax error, revealing a vulnerability prone to an SQL injection attack. Recognizing the unsafe code, I injected a simple SQL payload into the database by entering `admin' --` as the username. This effectively bypassed the password check by commenting out parts of the query. I then experimented with another technique, entering `admin' OR '1'='1` as the username, I tricked the system into authenticating me as "<b>True</b>". This happened because I met the criteria needed to be granted access to the account which had to do with the following:

Conditional A: The inputted username must match the one in the database (✅True)</br>
Conditional B: `OR` the value of 1 has to be equal to 1 (✅True)</br>
Conditional C: `AND` the inputted password must match the one in the database  (❌N/A)</br>

<p align="center">
Behind the scenes:
<img src="https://imgur.com/v4fwGDV.png" height="80%" width="100%" alt="Classic-SQLi-Lab"/>

During this lab, working with SQL injection techniques helped me understand how web applications can be vulnerable. I learned how important it is to have strong security measures in place and to follow secure coding practices. By seeing the risks that come with vulnerable web apps, I gained a better understanding of cybersecurity concepts and how to respond to incidents. This experience deepened my knowledge of cybersecurity and improved my ability to protect digital assets from threats.


<h2>Languages and Utilities Used</h2>

- <b>SQL</b> 
- <b>https://altoro.testfire.net/</b> (demo site)


<h2>Exploit Walk-Through:</h2>

<p align="center">
Login failure, typed <b> admin </b> as common username: <br/>
<img src="https://imgur.com/BlGWiwp.png" height="80%" width="80%" alt="Classic-SQLi-Lab"/>
<br />
<br />
Testing login functionality with username <b>admin'</b>. Returned syntax error indicating a potential vulnerability:  <br/>
<img src="https://imgur.com/fF7oEnI.png" height="80%" width="80%" alt="Classic-SQLi-Lab"/>
<br />
<br />
Simple SQLi payload <b>admin' --</b>: <br/>
<img src="https://imgur.com/XbBdljF.png" height="80%" width="80%" alt="Classic-SQLi-Lab"/>
<br />
<br />
Payload variation <b>admin' OR '1'='1</b>:  <br/>
<img src="https://imgur.com/vqooZnT.png" height="80%" width="80%" alt="Classic-SQLi-Lab"/>
<br />
<br />
Access granted:  <br/>
<img src="https://imgur.com/7NXhuiH.png" height="80%" width="80%" alt="Classic-SQLi-Lab"/>
<br />
<br />
</p>
