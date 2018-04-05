# Project 8 - Pentesting Live Targets

Time spent: **X** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Blue

Vulnerability #1: SQL Injection -
  It is clear that the blue site is not sanitizing its input. When looking at the salespeople you can change the salesperson's id to an SQL injection, such as ' OR SLEEP(10)=0--'. By doing this you can observe that the blue site is not sanitizing for SQL injections because this SQL injection forces the query to stall for 10 seconds. This is observable when the site takes an extra 10 seconds to load, which the red and green sites are not doing.

Video walkthrough -
<img src="XSS_Blue.gif" width="800">

Vulnerability #2: __________________


## Green

Vulnerability #1: Username Enumeration -
  The vulnerability that is evident here is gaining insight into users information from a false login attempt. The green site provides this information to an attacker. If you enter a username that does not have a valid account the error message is "Log in was unsuccessful" in plain print, however, if you enter a username that does exist within the system but just with an incorrect password the error message is bolded, informing the attacker that they have entered a valid username.
  
Video walkthrough - 
 <img src="Username_Enumeration_Green.gif" width = "800">

Vulnerability #2: XSS attack - 
  An attacker can insert malicious code into the feedback form from the public site and then when the admin goes to view that feedback an "attack" message occurs. Code such as <script> alert('attack') </script> is sufficient to carry out this attack
  
Video walkthrough - 
<img src = "XSS_Green.gif" width = "800">


## Red

Vulnerability #1: Insecure Direct Object Reference - 
  By changing the id number of the salespeople you can access salespersons who have not yet begun to work or who have been fired. For example, changing the ID number to 10 or 11 reveals two salespeople who are not seen on the public site and even provides the reason that one of them was fired for "FIRED FOR STEALING". The blue and green sites avoid this by sending you back to the salespersons general page when you enter a salesperson ID number that is not currently working for the company.
  
Video walkthrough - 
<img src = "IDOR_Red.gif" width = "800">

Vulnerability #2: __________________


## Notes

After last weeks lab, I found these challenges to be much more straight forward
