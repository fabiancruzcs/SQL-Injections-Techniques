<h1>Classic error-based SQLi</h1>


<h2>Description</h2>
This project focused on SQL injection vulnerabilities in the "AltoroMutual" demo site. By exploiting these vulnerabilities, particularly in the login functionality, I gained unauthorized access to the admin account without needing a password. Through this hands-on experience, I learned about cybersecurity risks associated with insecure web applications and the importance of secure coding practices.
<br />


<h2>Languages and Utilities Used</h2>

- <b>SQL</b> 
- <b>https://altoro.testfire.net/</b>


<h2>Exploit Walk-Through:</h2>

<p align="center">
Login failure, typed  typed <b> admin </b> as common username: <br/>
<img src="https://imgur.com/BlGWiwp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Testing login functionality with username ` <b> admin' </b> `. Returned syntax error indicating a potential vulnerability:  <br/>
<img src="https://imgur.com/fF7oEnI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Simple SQLi payload ` <b> admin' -- </b> `: <br/>
<img src="https://imgur.com/XbBdljF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Payload variation ` <b> admin' OR '1'='1 </b> `:  <br/>
<img src="https://imgur.com/vqooZnT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Access granted:  <br/>
<img src="https://imgur.com/7NXhuiH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>
