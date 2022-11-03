# Pen Testing Live Targets

Time spent: **X** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:

* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each color is vulnerable to only 2 of the 6 possible exploits. First discover which color has the specific vulnerability, then write a short description of how to exploit it, and finally demonstrate it using screenshots compiled into a GIF.

## Blue

- [ ] Vulnerability #1: SQL Injection (SQLi)

* The Attacker is Injects a sql command instead of the proper Salesperson's ID Number.
* Injected SQL Command: ``%27%20OR%20SLEEP(5)=0--%27``

<img src="2022-11-02 23-56-43.gif">

- [ ] Vulnerability #1: Session Hijacking/Fixation

* The Victim's session ID is obtained through the tool that is provided by the codepath

<img src="2022-11-03 01-21-48_Trim.gif">

* Using burp, we can intercept the attacker's access attempt to and secure site
* From the intercepted packet, we can modify the session ID to the one we obtained from the Victim

<img src="2022-11-03 01-26-48.gif">

* Once the packet is forwarded, the attacker is logged in using the Victim's session ID

## Green

- [ ] Vulnerability #1: Cross-Site Scripting (XSS)

* Attacker can inject an XSS in their feedback form.
* Injected XSS Command:
``<script>alert('Jinwoo found the XSS!');</script>``
* This XSS runs as soon as the account holder checks their feedback page

<img src="2022-11-03 00-24-27.gif">

- [ ] Vulnerability #2: Username Enumeration

* As you can see, the Green Website has the Username Enumeration error where the failure to login message differs for the Username that exists vs doesn't exist.
* I used Chrome's debugging tool and was able to see that the Developer assigns two different classes, failed and failure, to the error message depending on the login senerio.
* The "failure" class is applied an bold style in css while "failed" class doesn't.

<img src="2022-11-03 00-02-51.gif">

<img src="Screenshot 2022-11-03 001251.png">

## Red

- [ ] Vulnerability #1: __________________

Description:

<img src="red-vuln1.gif">


## Notes

Describe any challenges encountered while doing the work
