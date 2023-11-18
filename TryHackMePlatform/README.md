## DB for check IPs
[AbuseIPDB] https://www.abuseipdb.com/
[Cisco Talos Intelligence] (https://www.talosintelligence.com/)

## Three-Way Handshake

1. SYN      sync the two devices
2. SYN/ACK  the packet is sent
3. ACK      can be used by the client or server to acknowledge that packets have been received
4. DATA
5. FIN      close connection(FIN to receiver, ACK and FIN to sender, ACK to receiver)
0. RST       end all communication, problem during process
Any sent data has a random number and is reconstructed by using that number and incrementing it by 1

Al the firewlls we have discussed can be either stateful or stateless.
*   Statefull firewall: analyzes network traffic for characteristics and behavior that appers suspicious and stops them from entering the network. This only acts according to preconfigures rules set by the firewall administrator.
*   Stateless firewall: operates based on predefined rules and does not keep track of information from data packets. This doesn't store analyzed information neither discover suspicious trends like the stateful firewall does.

## VPN techonologies

*   PPP: allow authentication and provide encryption
*   PPTP: Point to Point Tunneling Protocol allow the data from PPP to travel and leave a network.
*   IPSec: encryots data using the existing IP framework

## HTTP errors


*   200 - OK	The request was completed successfully.
*   201 - Created	A resource has been created (for example a new user or new blog post).
*   301 - Moved Permanently	This redirects the client's browser to a new webpage or tells search engines that the page has moved somewhere else and to look there instead.
*   302 - Found	Similar to the above permanent redirect, but as the name suggests, this is only a temporary change and it may change again in the near future.
*   400 - Bad Request	This tells the browser that something was either wrong or missing in their request. This could sometimes be used if the web server resource that is being requested expected a certain parameter that the client didn't send.
*   401 - Not Authorised	You are not currently allowed to view this resource until you have authorised with the web application, most commonly with a username and password.
*   403 - Forbidden	You do not have permission to view this resource whether you are logged in or not.
*   405 - Method Not Allowed	The resource does not allow this method request, for example, you send a GET request to the resource /create-account when it was expecting a POST request instead.
*   404 - Page Not Found	The page/resource you requested does not exist.
*   500 - Internal Service Error	The server has encountered some kind of error with your request that it doesn't know how to handle properly.
*   503 - Service Unavailable	
This server cannot handle your request as it's either overloaded or down for maintenance.