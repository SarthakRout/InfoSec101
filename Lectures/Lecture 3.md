# Web Exploitation

> ## SQL Injection

 (SQL Query is a condition)

- `Classical Form` - Code injection technique used to attack data-driven applications, in which malicious SQL statements are inserted into an entry field for execution using Boolean logic.
- `Error Based` - The error output from the SQL database is used to manipulate the data inside the database.
- `Blind SQL` - SQL Injection attack that asks the database true or false questions and determines the answer based on the applications response.
- `Time Based` - Sending an SQL query to the database which forces the database to wait for a specified amount of time (in seconds) before responding.

> ## XSS (Cross Site Scripting)

- `Persistent XSS` - We send some script which gets embeded in the code of web page.
- `Reflected XSS` - Force the user to click on some link which executes a malicious script.

> ## CSRF (Cross-Site Request Forgery)

Forces an end user to execute unwanted actions on a web application in which they are currently authenticated.

> ## XXE (Cross XML Entity)

Web security vulnerability that allows an attacker to interfere with an application's processing of XML data.
> ## Directory Traversal (Local file inclusion)

Attack which allows attackers to access restricted directories and execute commands outside of the web server's root directory.
