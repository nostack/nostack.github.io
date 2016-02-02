---
title: Scripting E-mail Notifications
date: 2016-02-02T16:50:24-05:00
---
Recently, I've been looking into setting up e-mail notifications for this blog (soon to come, I promise), and it's been difficult setting up a script to send out emails. I initially looked at sending email's through terminal using a service called postfix, but that went way above my head and I didn't know what was going on. I spend about 8 hours looking at a billion different ways to do this. Finally, after endless searching, I managed to do it. I ended up using python, and I was surprised on how easy it was. It took me ~10 minutes to set it up once I knew how to, much less than the amount of time I spend on trying to do it through terminal.

So how exactly did I do it? The code is below:

```python
import smtplib
from email.MIMEMultipart import MIMEMultipart
from email.MIMEText import MIMEText
from email.MIMEBase import MIMEBase
from email import encoders

#Credentials
credFile = open('creds.txt')
password = credFile.readline()

#Mailing list - add users here
mailingList = ['email1', 'email2']
fromaddr = 'youremail@domain.com'

msg = MIMEMultipart()

#Open post
post = open("post.txt") #Used to send preview of post to followers
body = ""
counter = 1
for line in post.readline():
    if counter > 300 and line == ".":
        body += line
        break #Terrible programming practice I know
    body += line

msg['From'] = fromaddr

#Send email to each person in the mailinglist
for toaddr in mailingList:
    msg['To'] = toaddr
    msg['Subject'] = "The Ultimate Switch"

    body = body + "\nRead More at nostack.github.io :)"

    msg.attach(MIMEText(body, 'plain'))

    server = smtplib.SMTP('smtp.gmail.com', 587)
    server.starttls()
    server.login(fromaddr, password)
    text = msg.as_string()
    server.sendmail(fromaddr, toaddr, text)
    server.quit()

```
That's it! I hope this would help you in the future :) Until next time - ciao!
