## Cloud computing

A cloud service provider(CSP) is a company that offers cloud computing services. 
*   **Software as a Service(SaaS)** refers to software suites operated by the CSP that a company can use remotely
*   **Infrastructure as a service(Iaas)** refers to the use of virtual computer component offered by the CSP, includes virtual containers and storage that are configured remotly through the CSP's API web or console.
*   **Platform as a service(PaaS)** refers to tools that application developers can use to design custom applications for their company.

The benefits of using cloud computing are: Reliability, Cost and Scalability.

## TCP/IP layers

*   **1 Network access** deals with creation of data packets and their transmission across a network. ARP(Address Resolution Protocol) help IP with directing data packets on the same physical networking by mapping IP to MAC addresses on the same local network.
*   **2 Internet** is where IP are attached to data packets to indicate the location of the sender and receiver. This layer is responsible for delivering the data packets:
    *   **IP** send the data packets to the correct destination and relies on the TCPUDP protocol
    *   **Internet Control Message Protocol(ICMP)** shares error information and status updates of data packets. This is useful for detecting and toubleshooting network errors.
*   **3 Transport** includes protocols to control the flow of traffic across a network.
*   **4 Application** determine how the data packets will interact with receiving devices. Some commons protocols are: HTTP, SMTP(Simple Mail Tranfer Protocol), SSH, FTP(File Transfer Protocol),DNS

## OSI layers

*   Layer 7 Application: this includes all of the networking protocols that software applications use to connect a user to the internet.(HTTP, HTTPS, SMTP, DNS)
*   Layer 6 Presentation: involve data translation and encrypting for the network. SSl encrypts data between web servers and browsers as part of the websites with HTTPS.
*   Layer 5 Session: describes when a connection is established between two devices. Also is responsible for authentication, reconnection and setting checkpoints during a data transfer.
*   Layer 4 Transport: is responsible for delivering data betwwen devices, also handle the speed of data transfer, flow and breaking data down into smaller segments to make them easier to transport.
*   Layer 3 Network: oversees receiving the frames from the data link layer and delivers them to the intended destination. The destination is found in the frames that each packets sends.
*   Layer 2 Data linker: organizes sending and receiving data packets within a single network.
*   Layer 1 Physical: correspond to the physical hardware involved in network transmission.

## IPv4 header fields

[Header fields](https://en.wikipedia.org/wiki/Internet_Protocol_version_4#/media/File:IPv4_Packet-en.svg).

*   Version (VER): This 4 bit component tells receiving devices what protocol the packet is using. The packet used in the illustration above is an IPv4 packet.

*   IP Header Length (HLEN or IHL): HLEN is the packet’s header length. This value indicates where the packet header ends and the data segment begins. 

*   Type of Service (ToS): Routers prioritize packets for delivery to maintain quality of service on the network. The ToS field provides the router with this information.

*   Total Length: This field communicates the total length of the entire IP packet, including the header and data. The maximum size of an IPv4 packet is 65,535 bytes.

*   Identification: For IPv4 packets that are larger than 65, 535 bytes, the packets are divided, or fragmented, into smaller IP packets. The identification field provides a unique identifier for all the fragments of the original IP packet so that they can be reassembled once they reach their destination. 

*   Flags: This field provides the routing device with more information about whether the original packet has been fragmented and if there are more fragments in transit.

*   Fragmentation Offset: The fragment offset field tells routing devices where in the original packet the fragment belongs.

*   Time to Live (TTL): TTL prevents data packets from being forwarded by routers indefinitely. It contains a counter that is set by the source. The counter is decremented by one as it passes through each router along its path. When the TTL counter reaches zero, the router currently holding the packet will discard the packet and return an ICMP Time Exceeded error message to the sender. 

*   Protocol: The protocol field tells the receiving device which protocol will be used for the data portion of the packet.

*   Header Checksum: The header checksum field contains a checksum that can be used to detect corruption of the IP header in transit. Corrupted packets are discarded.

*   Source IP Address: The source IP address is the IPv4 address of the sending device.

*   Destination IP Address: The destination IP address is the IPv4 address of the destination device.

*   Options: The options field allows for security options to be applied to the packet if the HLEN value is greater than five. The field communicates these options to the routing devices.

[Difference between IPv4 and IPv6 header](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/PNld6YkmQNWyhZjFFHvC-Q_eb474e5ee3b3416fbc06a639503342f1_CS_R-044_IPv4-and-IPv6.png?expiry=1693958400000&hmac=CYAK2GN2CTXtekvkeh_wcuyUv-UV5VpRN895pRybewo).

## Network protocol

Is a set pf rules used by two or more devices on a network to describe the order of delivery and the structure of data.
There are 3 categories of networks protocols:
*   **Communication protocols** TCP, UDP, HTTP, DNS
*   **Management protocols** are used for monitoring and managing activity on a network, they include protocols for error reporting and optimizing on the network.
    *   Simple Network Management Protocol(SNMP): is a network protocol used for monitoring and managing devices on a network. It can reset a password on a network devices or change its baseline configuration.It is also usefull for a report on how much of the network's bandwidth is being used up.
    *   Internet Control Message Protocol(ICMP): is an internet protocol used by devices to tell each other about data transmission errors across the network. Is used by receiving device to send a report to the sending device about the data transmission. Is used as quick way to troubleshoot network connectivity and latency by issuing the ping command on Linux.
*   **Security protocols** are network protocols that ensure that data is sent and received securely across a network. They use encryption algorithms to protect data in transit.
    *   HTTPS: is a network protocol that provides a secure method of communication between clients and website servers.
    *   Secure File Transfer Protocol(SFTP): is a secure protocol used to transfer files from one device to another over a network. Those users use SSH through TCP port 22.

## More about networks protocols

**DHCP** uses port 67 for servers and 68 for clients.
**Telnet** uses port 23
**SSH** uses port 22.
**Post office protocol(POP)** is an application layer used to manage and retrieve email from a mail server. Plaintext uses port 110 and encrypted use SSL/SSL port 995.
**Internet MEssage Acces Protocol(IMAP)** is used for incoming email, it download the headers of emails but not the content. The content remains on the email server, this uses port 143 for unencrypted email and 993 over the TLS protocol(crypto protocol).
**Simple Mail Transfer Protocol(SMTP)** is used to transmit and route email from sender to rhe recipient's address. Uses port 25 for unencrypted emails and 587 using TLS for encrypted. Usually port 25 is an high-volume spam, for that SMTP helps to filter out spam by regulating how manu email a source can send at a time.

## IEEE802.11 (Wi-Fi)

IEEE is for Institue of Eletrical and Electronic Engineers, which is an organization that maintains Wi-Fi standards and the 802.11 is a suite of protocols used in wirelesse comunication.

## Firewall

Is a network security device that monitors traffic to and from your network.
**Hardware firewall** inspects each data packets before it's allowed to enter the network.
**Software firewall** performs the same functions as a hardware one, but it's a software program installed on an PC or a server.
There is the option of using an cloud firewall by utilizing FaaS(firewall as a service).

Al the firewlls we have discussed can be either stateful or stateless.
*   Statefull firewall: analyzes network traffic for characteristics and behavior that appera suspicious and stops them from entering the network. This only acts according to preconfigures rules set by the firewall administrator.
*   Stateless firewall: operates based on predefined rules and does not keep track of information from data packets. This doesn't store analyzed information neither discover suspicious trends like the stateful firewall does.

The next gen firewall, the NGFW, provides even more security than a statefull firewall, not only provide stateful inspection of incoming and outgoing traffic, but it also performs more in-depht security functions like deep packet inspection and intrusion protection.

## Security zones

Are a segment of a network that protects the internal network from the internet. They are a part of a security technique called network segmentation that divides the network into segments. Each segment has its own access permissions and security rules. Security zones act like a barrier to interal networks, maintain privacy within corporate groups and prevent issues from spreading to the whole network.(Free Wi-Fi hotel)

An organization's network is classified into two types of security zones.
*   Uncontrolled zone which is any network outside of the organization's control, like the internet.
*   Controlled zone which is a subnet that protects the interal network from the uncontrolled zone. There are several types of them. On the router layer is the demilitarized zone(DMZ) wich contais public-facing services that can access the servers tnat provides IP for internet users. The DMZ acts as a network perimeter to the internal network.
[Example](https://s3.amazonaws.com/kajabi-storefronts-production/blogs/3184/images/9hFpYzphSaawzqta0OQm_Picture2.png)

## Proxy

Proxy fulfills the request of a client by forwanding them on to other servers. The proxy is a dedicated server that sits between the itnernet and the rest of the network. When an request is coming, the proxy will determine if the connection request is safe. This hides the private IP address from malicious actors on the internet and adds a layer of security.
*   **Forward proxy server** regulates and restricts a person with access to the internet, the goal is to hide the IP address and approve all outgoing requests.
*   **Revers proxy server** regulates and restricts the internet access to an internal server. The goal is to accept traffic from external parties, approve it and forward it to the interal servers. Is used because it protects internal web servers containing confidential data from exposing thei IP to external parties.

## VPN protocols

WireGuards and IPSec are two different VPN protocols used to encrypt traffic over a secure network tunnel.
*   WireGuard: is an high-speed VPN protocol with advanced encryption to protect users. It's simple to set up and maintain, can be used to site-to-site and client-server connections. Is also open source, which makes it easier for users to deploy and debug.
*   IPSec: most VPN providers use IPSec to encrypt and authenticate data packets in order to establish secure, ecnrypted connections-

## DDoS attack

Distributed Denial of Service.

*   **SYN flood attack** is a type of DoS attack thay simulates the TCP connection and floods the server with SYN packets. First they send a SYN(synchronize) request to the server, than the server respond with an SYN/ACK packet to acknowledge the receipr of the devece's request and leaves a port open for the final step. Once the server receives the final ACK packet, a TCP connection is established. Hackers take advantage of the protocol by flooding a server with SYN packet requests for the first part of the handshake, but if the number of requests is higher than the number of ports avaiables then the server will be overwhelmed and become unable to function.
*   **ICMP(Internet Control Message Protocol) flood** is an internet protocol used by devices to tell each other about data transmission errors across the network(status request). An attacker repetedly sends ICMP packets to a network server. This force sthe server to send an ICMP packet and this eventually fill the whole bandwith for incoming and outgoing traffic.
*   **Ping of death** is caused when a hacker pings a system by sending it an oversized ICMP packet taht is bigger thay 64 kB, this will overload the system and cause it to crcash.

## tcpdump

This is a packet sniffer(or protocol analyzer, like wireshark). This is text based, this means that every command are executed in the terminal. It provides a brief packet analysis and converts key information about network traffic into formats easily read by humans.
tcpdump prints the output of the command as the sniffed packets in the command line after a command is executed. [Example of a packet](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/B-PaECh0ToSFgBWpFczYZg_4896abe8c06443f08eec4dc003dcf8f1_image.png?expiry=1694044800000&hmac=lPGLgqx9zDJf5V27aCMACRo5wbv1tWUbAHmKvrLx-PA).
*   Timestamp: formatted as hours minutes seconds and fraction of seconds
*   Source IP
*   Source port is where the packet is originated
*   Destination IP
*   Destinatio port

## Packet sniffing

*   Passive: packets are read in transit, since all the trafic is visible to any host on the hub, malicious actors can view all the information going in and out of the device they are targeting.
*   Active: packets are manipulated in transit.

# Way to defend from being sniffed

*   Using a VPN to encrypt your data 
*   Make sure that the websites used have HTTPS
*   Avoid using unprotected Wi-Fi

## IP spoofing

Is a network attack performed when an attacker changes the source IP of a data packet to impersonate and authorized system and gain access to a network, the hacker pretende to be someone they are not so they can communicate over the network with the target computer and get past firewall rules. Some commons spoofing attacks are on-path, reply and smurf.
*   On-path attack is an attack where the malicious actor places themselves in the middles of an authorized connection and intercepts or alters the data in transit. They gain access to the network and put themselves between two devices.
*   Replay attack is performed when a malicious actor intercepts a data packet in transit and delays it or repeats it at another time. It can cause connection issues between target computers, or a malicious acotr may take a network transmission that was sent by an authorized user and repeat it at a later time to impersonate the authorized user.
*   A smurf attack is a combination of DDoS attack and an IP spoofing attack. The attacker sniff an authorized user's IP and floods it with packets, this can bring down a server or the entire network.

# Way to defend from 

*   Encryption
*   Firewall can be configured to protect against IP spoofing, so if a firewall receive a data packet from the internet where the sender's IP is the same as the private network, then the firewall will deny the transmission since all the devices with that IP should already be on the local network.

## [Learn how to read wireshark](https://techcommunity.microsoft.com/t5/core-infrastructure-and-security/introduction-to-network-trace-analysis-3-tcp-performance/ba-p/3737115)

## Security hardening

This is the process of strenghening a system to reduce its vulneranility and attack surface. All the potential vulnerabilities that a threat actor could exploit are referred to as a system's attack surface.
*   Software updates
*   Removing unused application and services
*   Disabling unused prots
*   Reducing access permissions across devices
*   Regular penetration testing
*   Hardware and software destruction
*   Strong password policies

Tasks performed regularly:
*   Firewall rules maintenance
*   Network log analysis
*   Patch updates
*   Server backups

Tasks performed once:
*   Port filtering
*   Up to date wirless protocols
*   Network segmentation to separate different security zones
*   Communication encrypted

#   Sandboxes

Is a type of testing environment that allowa you to execute software or programs separate from your network. Can be stand-alone physical computers that are not connected to a network.

#   Prevent Brute force attacking
*   Salting and hasing: hashing converts information into a unique value that can then be used to determine its integrity, it's a one-way function and salting add random characters th hased password.
*   MFA and 2FA
*   CAPTCHA and reCAPTCHA
*   Password policies: standardize good password practices throughout the business

## Network security applications

**Intrusion detection system(IDS)** is an application that monitors system activity and alerts on possible intrusions. It detect known attacks, often sniff packets as they move across the network and analyze them for the characteristics of know attacks. IDS only scans for obvious anomalies, don't block them.

**Intrusion prevention system(IPS)** is an application that monitors system activity for intrusive activity and takes action to stop the activity, it actively stops anomalies when they are detected. This searches for signatures of known attacks and data anomalies and block a specific sender or drops network packets that seem suspect.

**Full packet capture devices** allowa you to record and analuze all of the data this i transmitted over your network.

## Cloud hardening

The cloud hardening utilize an server baseline image for all server instances stored in the cloud, this allow companies to compare data in the cloud to the baseline image to make sure there haven't been nay unverified change.
**Identify access management(IAM)** is a collection of precesses and technologies that helps organizations manage digital identities in their environment, this suthorizes how users can use different cloud resources.
**Configuration** each services implemented must be carefully configures to meet security and compliance requirments.
**Attack surface** cloud service providers(CSPs) offer numerous applications and services for organizations at low cost. Cloud networks that utilize many services introduce lots of entry points into an organization's network, if the network is configured correctly utilizing different services does not introduce more entry points.
**Zero day attacks** is an attack performed utilizing an exploit not yet documented.
**Visibility and tracking** network administrators have access to every data packet crossing the network with both on-premise and cloud networks. They can sniff and inspect data packets to learn about network performance or to check possible threats and attacks.

#   Key management in the cloud

*   Trusted platform module(TPM): is a computer chip that can securely store passwords, certificates and encryption keys
*   Cloud hardware security module(CloudHSM): is a computing device that provides secure storage for cryptographic keys and processes cryptographic operations.