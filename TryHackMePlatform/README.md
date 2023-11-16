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