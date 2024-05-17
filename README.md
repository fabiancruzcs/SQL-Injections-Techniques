<h1>Error-based SQLi</h1> 


<h2>Description</h2>
This lab focused on SQL injection vulnerabilities in the "AltoroMutual" demo site. By exploiting these vulnerabilities, particularly in the login functionality, I gained unauthorized access to the admin account without needing a password. Through this hands-on experience, I learned about cybersecurity risks associated with insecure web applications and the importance of secure coding practices.
<br />


<h2>Thought Process</h2>

During the lab's initial phase, I examined the website's security setup systematically. By entering `admin'` as the username in the login interface, I triggered a syntax error, revealing a Classic SQL injection vulnerability. Realizing the risk, I used a simple SQL injection technique by entering `admin' --` as the username. This effectively bypassed the password check by commenting out parts of the query. I then experimented with another technique, entering `admin' OR '1'='1` as the username. This tricked the system into authenticating me as "<b>True</b>" irrespective of the password input, granting unauthorized access to the admin account.

<img src="https://imgur.com/v4fwGDV.png" height="80%" width="80%" alt="Classic-SQLi-Lab"/>

During this lab, working with SQL injection techniques helped me understand how web applications can be vulnerable. I learned how important it is to have strong security measures in place and to follow secure coding practices. By seeing the risks that come with vulnerable web apps, I gained a better understanding of cybersecurity concepts and how to respond to incidents. This experience deepened my knowledge of cybersecurity and improved my ability to protect digital assets from threats.


<h2>Languages and Utilities Used</h2>

- <b>SQL</b> 
- <b>https://altoro.testfire.net/</b> (demo site)


<h2>Exploit Walk-Through:</h2>

<p align="center">
Login failure, typed  typed <b> admin </b> as common username: <br/>
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
