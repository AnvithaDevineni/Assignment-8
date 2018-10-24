Project 8 Pentesting Live Targets

Time spent: ___ hours spent in total

Objective: identify vulnerabilities in three different version of the Globitek website: blue, green, and red.

6 exploits possible:

Username Enumeration
Insecure Direct Object Reference (IDOR)
SQL Injection (SQLi)
Cross-Site Scripting (XSS)
Cross-Site Request Forgery (CSRF)
Session Hijacking/Fixation

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

Blue:
-
Vulnerability #1: SQL Injection
-

- User may inject SQL code into the salesperson page (URL). They just have to request %27%20OR%20SLEEP(5)=0%27 in the stead of the salesperson's ID number

- In order to prevent this sites may sanitize URL input paramaters with the command "mysql_real_escape_string()"

Vulnerbility #2: Session Hijacking/Fixation
-

- By setting the current session ID to an older session ID from a user that has been previously logged in, the The user can log in without a username or password by setting the current session ID to an old session ID from a previously logged in user. 

- In order to prevent this, sites may regenerate session ID's every half hour. This will prevent illegal log-ins using expired session ID's.

Green:
-
Vulnerability #1: Username Enumeration
-
- The error here, is that the failure to log in message is different from the username that exists and the username that does not exist. 

- I was able to find that the developer assigns two different classes, "failed"/"failure" to the error messsage in accordance to the log-in occurance. I was able to find this by using Google Chrome's debugging tool. 

Vulnerability #2: Cross-Site Scripting (XSS)

- People can inject XSS in the feedback form-- for example : <script>alert('attacker is here XSS');</script> 


Red:
-
Vulnerability #1: Insecure Direct Object Reference
-

-By modifying the ID parameter in the URL (change GET request), a person can get access to hidden user's accounts. 

Vulnerability #2: Cross-Site Requeest Forgery (CSRF)
-
- User will have permission to update information in the database through the "edit pages" without a valid CSRF token.

- In order to prevent this, sites should / can / are validate the CSRF tokens on forms. This will reulst in an invalid request error on forms with invalid CSRF tokens. 
