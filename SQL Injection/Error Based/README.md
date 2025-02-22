<h1>Error Based SQL Injection Attack</h1>

<h3>Description</h3>
Project consists of performing a Error Based SQL Injection Attack on the Mutillidae vulnerable Metasploitable 2 web server.
<br>

<h3>Languages and Utilities Used</h3>

- <b>VMWare</b>
- <b>MySQL</b>

<h3>Environments Used </h3>

- <b>Kali Linux</b>
- <b>Metasploitable 2</b>
<!------------------------------------------------------------------------------------------------------------------------------------------------------------------------>

<h1>Performing the Error Based SQL Injection Attack</h1>
<p align="center">
To begin, I input the string " '"()[]{} " in order to induce a syntax error:<br>
<img src="https://i.imgur.com/0cq5jnr.png" height="80%" width="80%" alt=""/><br>
Viewing said Error, the syntax is incorrect due to the single quote "'" at the beginning of my string, ending the username string, and placing an unexpected double quote """ after the username, causing an Error:<br>
<img src="https://i.imgur.com/ibiwOZB.png" height="80%" width="80%" alt=""/><br>
I input “’ or true#” within the username to gain access to every account detail. This works due to the username string ending and then creating an or statement that will always be true. After which, I end the query by commenting out any following portions of the previous command:<br>
<img src="https://i.imgur.com/NprzmEG.png" height="80%" width="80%" alt=""/><br>
Viewing account details as a result of the SQL error injection:<br>
<img src="https://i.imgur.com/SHPHhIf.png" height="80%" width="80%" alt=""/><br>
Altering my username string to admin’# in order to send the command SELECT * FROM account WHERE username =’admin’. This allowed me to view the account details for the admin account without knowing the password.:<br>
<img src="https://i.imgur.com/wzezJle.png" height="80%" width="80%" alt=""/><br>
Viewing the admin account details as a result of the SQL error injection:<br>
<img src="https://i.imgur.com/UxYbohG.png" height="80%" width="80%" alt=""/><br>
</p>
