# dot-qmail
Auto Responder, Notification, an Vacation messages controlled by .qmail file

These utilites are used by writing files in the directory for each account.

A .qmail file using all 3 might look like this:

./Maildir/<br />
|externalnotify $SENDER $USER<br />
|vacation $SENDER $USER "I'm on vacation"<br />
|autoresponder $SENDER $USER "list" "the list"<br />

externalnotify: looks for a .notify file (same directory) containing the email address where the notification will be sent

vacation: uses the Subject specified in the 3rd argument and then looks for a .vacation file containing the body of the vacation email

autoresponder: looks for a substring match for the 3rd argument in the incoming email Subject, if there is a match it returns an email with the 4th argument as the Subject and the body of the email from a file called .autoresponse 
