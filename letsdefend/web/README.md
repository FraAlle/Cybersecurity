# HTTP request
```Upgrade-Insecure-Requests: 1``` means thath SSL is activated
```Connection: close``` whows how the HTTP connection is made. With "close" we understand that the TCP will be close after receiving the HTTP response. With "keep-alive" means that the connection will be maintained.  

# SQL injection
(Classic SQLi): When an SQL query is sent and responded to on the same channel, we call this in-band SQLi.

(Blind SQLi): SQL queries that receive a response that cannot be seen.

Out-of-band SQLi: If the response to an SQL query is communicated through another channel, this type of SQLi is called "out-of-band SQLi". For example, if the attacker receives replies to the SQL queries via DNS, this is called out-of-band SQLi.

## Prevent SQL injection
Use a framework
Keep your framework up to date
Avoid the use of raw SQL queries: You may be in the habit of writing raw SQL queries, but you should take advantage of the security provided by the framework.

## Detect SQL injection
Look at the User-Agent: You can look at the User-Agent to detect these automated tools.

Check the frequency of requests: Automated tools are designed to send an estimated number of requests per second to test payloads as quickly as possible. A normal user might send 1 request per second, so looking at the number of requests per second will tell you if the requests are from an automated tool or not.

Look at the content of the payload: Automated tools usually include their own names in their payloads. For example, an SQL injection payload sent by an automated tool might look like this: sqlmap’ OR 1=1

## Identify an SQL injection
In the url we can see a lot of "%", this is a symbol to let understand the url that a special character is inserted(space, !,",&, etc).
[Example of SQLInjection](https://ld-images-2.s3.us-east-2.amazonaws.com/Detecting+Web+Attacks/images/Access-logs-with-URL-decoding.png)

# XSS
Non-Persistent: This is a non-persistent type of XSS where the XSS payload must be present in the request. It is the most common type of XSS.

Persistent: This type of XSS is where the attacker can permanently upload the XSS payload to the web application. Compared to other types, Stored XSS is the most dangerous type of XSS.

DOM Based XSS: DOM Based XSS is an XSS attack where the attack payload is executed as a result of modifying the DOM "environment" in the victim's browser used by the original client-side script so that the client-side code runs in an "unexpected" manner. (OWASP)

## Detect XSS
Look for keywords: The easiest way to detect XSS attacks is to look for keywords such as "alert" and "script" that are commonly used in XSS payloads.
Learn about commonly used XSS payloads: Attackers tend to use the same payloads to look for vulnerabilities before exploiting an XSS vulnerability. Therefore, familiarizing yourself with commonly used XSS payloads would make it easier for you to detect XSS vulnerabilities. You can examine some commonly used payloads [here](https://github.com/payloadbox/xss-payload-list).
Check for the use of special characters: Check data coming from a user to see if any special characters commonly used in XSS payloads, such as greater than (>) or less than (<), are present.
[Example of XSS](https://ld-images-2.s3.us-east-2.amazonaws.com/Detecting+Web+Attacks/images/xss-apache-access-log-with-url-decoding.png)

# Command Injection
Is an attack that occurs when data received from a user is not sanitized and is passed directly to the operationg system shell.

## Protect against Command Injection
Always sanitize data received from a user: Never trust data received from a user. Not even a file name!
Limit user rights: Adjust web application user rights to a lower level whenever possible. 
Make use of virtualization technologies such as dockers

## Detect Command Injection
When examining a web request look at all the areas: The command injection vulnerability may be located in various areas depending on the operation of the web application.
Look for keywords related to the terminal language: Check the data received from the user for keywords that are related to terminal commands such as: dir, ls, cp, cat, type, etc.
Familiarize yourself with frequently used Command Injection payloads: When attackers detect a command injection vulnerability they usually create a reverse shell in order to work more easily. This is why knowing frequently used Command Injection payloads will make it easier to detect a command injection attack.

# Detecting Insecure Direct Object Reference(IDOR)
Is caused by the lack of an authorization mechanism or because it is not used properly.
This is an example:
"Let’s imagine a basic web application. It retrieves the “id” variable from the user, then it displays data that belongs to the user who made the request. 
URL: https://letsdefend.io/get_user_information?id=1
When a request is made in our web application, like the one above, it displays the information of the user with an id value of 1.
If I am the user who made the request and my id value is 1 everything will work normally. When I make the request I will see my personal information.
But what happens if we make a request with 2 as the “id” parameter? Or 3?
If the web application is not controlling: “Does the “id” value in the request belong to the person making the request?” then anyone can make this request and see my personal information.This web vulnerability is called IDOR."

## Prevent IDOR
Always check if the person who made the request has any authority.

## Detecting IDOR attacks
Check all parameters: an IDOR vulnerability may occur in any parameter. This is why you should not forget to check all parameters.
Look at the amount of requests made for the same page: When attackers detect an IDOR vulnerability they also want to access the information related to all other users so they usually perform a brute force attack.
Try to find a pattern: Attackers will plan a brute force attack to reach all objects. Because they will perform the attack on successive and foreseeable values like integer values you can try to find a pattern in these requests. For example: if you see requests such as id=1, id=2, id=3, you may suspect something.
[Example of IDOR](https://ld-images-2.s3.us-east-2.amazonaws.com/Detecting+Web+Attacks/images/idor-apache-access-log.png)

# Local File Inclusion (LFI) and Remote File Inclusion(RFI)
LFI is a vulnerability that happens when a file is included without sanitizing the data obtained from a user.
RFI is the same as LFI but the file is hosted in a different server.

## Prevent LFI & RFI
Sanitize any data received from a user before using it. The controls should be done on client and server side.

## Detecting LFI & FRI attacks
When examining a web request from a user, examine all the fields.
Check for any special characters: Within the data that is received from users, especially look for notations such as ‘/’,  `.`, `\`.
Familiarize yourself with files frequently used in LFI attacks: In an LFI attack the attacker reads the files that are on the server. If you familiarize yourself with the critical file names on the server, you can detect LFI attacks more easily.
Search for acronyms such as HTTP and HTTPS: In RFI attacks the attacker includes the file on his own device and enables the file to execute. 
In order to include a file, attackers usually set up a small web server on their own device and display the file over an HTTP protocol. This is why you should search for notations such as “http” and “https” to be able to detect RFI attacks more easily.
