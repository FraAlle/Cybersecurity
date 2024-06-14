# PHISHING
SPF(Sender Policy Framework), DKIM(Domain Keys Identifies Mail), and DMARC are protocols used to determine if the sender of an email is fake or real.

## Important fields in emails
From
The 'From' field in an Internet header shows the name and email address of the sender.

To
This field in the mail header contains the details of the recipient of the email, including their name and email address.

Subject
The subject is the topic of the email.

Return-Path
This email header field is also known as Reply-To. When you reply to an email, the reply is sent to the address specified in the Return-Path field.

Domain Key and DKIM Signatures
Domain Key and Domain Key Identified Mail (DKIM) are email signatures that help email service providers identify and authenticate your emails, similar to SPF signatures.

Message-ID
The Message-ID header is a unique combination of letters and numbers that identifies each email.

MIME-Version
Multipurpose Internet Mail Extensions (MIME) is an Internet coding standard. It converts non-text content, such as images, videos, and other attachments, into text so that non-text content can be attached to an email and sent via SMTP (Simple Mail Transfer Protocol).

Received
The Received section lists each mail server that an email has passed through before arriving in the recipient's inbox. It's listed in reverse chronological order.

X-Spam Status
The X-Spam Status shows you the spam score of an email message.
First, it'll highlight if a message is classified as spam.
It then shows the spam score of the email and the spam threshold for the email.
An email can either meet or exceed an inbox's spam threshold. If it's too spammy and exceeds the threshold, it's automatically classified as spam and sent to the Spam folder.

## Check sender
Use this site to see if the sender use the correct SMTP server mxtoolbox.com.
