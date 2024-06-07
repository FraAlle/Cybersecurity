# OSINT
For this purpose, you can use some existing OSINT specialized machines like Trace Lab Osint VM, or you can create your own OSINT Linux Distribution (you will find an excellent guide for DIY Machines in one of the following links).

TL OSINT VM: https://www.tracelabs.org/initiatives/osint-vm
DIY OSINT VM Guide: https://nixintel.info/tag/diy-buscador/

## Sock Puppetry
These are alter-egos created to carry out various types of projects or research.
https://web.archive.org/web/20210125191016/https://jakecreps.com/2018/11/02/sock-puppets/

## The Harvester
Is a CMD information-gathering tool that use OSINT sources to get info about the target domain and take hostnames, IP addresses, employees, emails, etc.
```theHarvester -d google.com -l 20 -b urlscan```

## Maltego
Data mining and info gathering tool, capture real data on different types of entities(companies, people, websites) and represent every connection.

## Tweetdeck(Not Usable rn bc is a pay service)
Is a tool to monitor tweets, trends about cyberattacks, vulnerabilities, etc.

## Google Dorks
Is a way to make a more aimed search using operator:keyword(filetype:pdf).
It's used to take files from domains, finding hidden web pages and login portals, subdomain enumeration etc.
```Cyber Security filetype:pdf```
```site:Facebook.com -site:www.facebook.com```(look for sites that include .Facebook.com)(but not www.facebook.com)
```inurl: admin``` we can see differents admin login portals.

## Defending against Google Dorks
*   Geofencing is a method to block IPs associated with countries, so it is possible to stop people with IP range we don't want.
*   IP whitelisting it just allow certains IPs to access resources.
*   Crawler restrictions is a method to block their crawlers from being able to access any of the content. This can be achieves by creating a file ```robots.txt```. 
```User-agent: * Disallow: /``` this disallow any user-agents from crawling any directory on the website.
*   Request content removal to temporaly remove the content from the search engine(90 days) or permanently.

## Frameworks
https://osintframework.com

## Tineye