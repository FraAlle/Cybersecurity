## Fast Flux

Is a DNS technique used by botnets to hide hishing, web proxying, malware delivery and malware communications activities behind compromised hosts acting as proxies. The true purpoes behind this technique is to hide the malware communication and make it hard for security professionals to discover the malware.
The primary concept it having multiple IP addresses with a domain name, which is constantly changing.

## TTPs(Tactics, Techniques & Procedures)

An example is the Pass-The-Hash attack: an attacker capture an hash password and pass it through for authentication and lateral access(is usable after gaining access to move deeper into a network searching for assets, the attacker maintains ongoing access by moving in the environment and obtaining more privileges) to other networked systems

## Cyber kill chain

This framework define the steps to make use for hackers. Is usefull to protect against ransomware, security breaches and APTs(Advanced Persistent Threats).
1. Reconnaissance: is discovering and collecting info on the victim, utilizing OSINT(Open-Source Intelligence-> free services where you can found info about one person) too. Email harvesting is the process to obtain emails from public, paid or free services and can be used for an phishing attack. Some site to gather info are: [theHarvester](https://github.com/laramies/theHarvester) / [Hunter.io](https://Hunter.io) / [OSINT](https://osintframework.com/)
2. Weaponization: here the attacker has differents options to make
    a. Create an Office document containing malicious macro or VBA scripts
    b. Create a payload or a sophisticated worm, implant it on the USB drive and distribuite them in public
    c. Command and Control(C2) for executing the command on the victim's machine
    d. Create a backdoor
3. Delivery: is the way for the attacker to deliver the payload or malware.
    a. Phishing email
    b. Distributing infected USB drives
    c. Watering hole attack, is an targeted attack designed to aim at a specific group of people. The attacker look for a known vulnerability and exploit it.
4. Exploitation: these are ways to carry an exploitation
    a. Trigger the exploit by opening an email with malicious file attached
    b. Zero-day exploit
    c. Exploit software, hardware
    d. Trigger the exploit for server-based vulnerabilities
5. Installation: this is when the hacker install an persistent backdoor in the system
    a. Web shell, is a script made in PHP or JSP used to maintain access to the system
    b. Using [Meterpreter framework](https://www.offsec.com/metasploit-unleashed/meterpreter-backdoor/) to install a backdoor
    c. Creating or modifying Windows services, with this the attacker can execute malicious scripts or payloads
    d. Adding the entry to the run keys for the malicious payload in the Registry or the Startup folder
    In addiction, an hacker can utilize the [Timestomping](https://attack.mitre.org/techniques/T1070/006/) to avois detection by the forensic investigator, it allows the hacker to modify the file's timestamps to mimic files that are in the same folder.
6. Command & control: the host will always be communicating with the C2 server, with this the attacker will have full control fo the victim's machine. Most usable channels for C2 are:
    a. port 80 or 443 to hide the traffic with the legitimate traffic 
    b. the infected machines makes constant DNS requests to the DNS server that belongs to an attacker, DNS tunneling
7. Actions on objectives: in the end the hacker can do whatever he want with the victim's machine

## Unified kill chain

Is a way to explain various stages of an attack, for example: after an attacker scanning, exploiting a web vulnerability and escaleting privileges will be a "Kill Chain".
# Threat modelling
Is a series of steps to ultimately improve the security of a system.
1. Idetifying what systems and applications need to be secured and what function they serve in the environment.
2. Assessing what vulnerabilities and weaknesses these systems and applications may have and how they could be potentially exploited.
3. Create a plan to protect these systems and applications.
4. Putting policies to prevent these vulnerabilities from occuring again where possible.

The UKC states that there are 18 phases to an attack.[Immage of the 18 phases](https://tryhackme-images.s3.amazonaws.com/user-uploads/5de96d9ca744773ea7ef8c00/room-content/708e85cf63230b21bacee32bfbd6d311.png).

# Initial Foothold
The main focus for an attacker to gain access to a system or network. This series of phases also accomodates for an attacker to creat a form of persistence.
1. Reconnaissance: gather information about the victim. Discover what system and services are running on the target, finding contact lists of employees that can be impersonated or used, looking for potential credential and understanding the network topology.
2. Weaponization: Setting up the necessary infrastructure to make an attack.
3. Delivery: techiques to transmit a weapon to the victim.
4. Social engineering: describes techniques that can be emplyed to manipulate employees to perform actions that will aid the attacker.
5. Exploitation: how an attacker takes advantage of weaknesses or vulnerabilities present in a system.
    a. Uploading and executing a reverse shell
    b. Interfering with an automated script
    c. Abusign a web application vulnerability to execute code
6. Persistence: describe techniques used to maint access to a system.
7. Defensive evasion: techniques used to evade defensive measures put in place in the system or network.
    a. WAF(Web Application Firewall)
    b. Network Firewalls
    c. Anti-virus systems on the target machines
    d. Intrusion detection systems
8. C2: execute commands, steal data and use the controlled server to pivot other systems.
9. Pivoting: is used to reach other systems within a network that is no other way accessible.

# Network propagation
The attacker try to gain additional access and privileges to systems and data to fulfil their goals.
10. Discovery: the attacker would uncover information about the network it is connected to. Is important to gather info about active accounts, permission granted, applications and software in use, web browser activity, files, directories, network shares and system configuration.
11. Privilege escalation: the attacker will try to gain more permissions with the pivot system, he will leverage the information from accout presents with vulnerabilities or misconfiguration. 
12. Execution: this is when the attacker use the pivos system as host to deploy malicious code. Trojans, C2 scripts, malicious links and scheduled tasks.
13. Credential Access: the attacker try to steal account names and passwords through various attacks method, keylogging and credential dumping.
14. Lateral movement: move throught the network and jump onto another targeted systems to achieve their primary objective.

# Action on Objectives
15. Collection: seek to gather all the valuable data of interest.
16. Exfiltration: steal data which can be packaged using encryption measures and compression to avoid any detection
17. Impact: if the adversary seek to compromise the integritu and availability of the data assets they would manilulate, interrupt or destroy assets.
18. Objectives: here the attacker can reach his goals.

## Diamond model
It helps identihy the elements of an intrusion.
Is composed by four features:
*   adversary: is the person behind the cyberattack. 
    *   Operator: is the hacker or person conducting the intrusion activity
    *   Customer: is the entity that stands to benefit from the intrusion, is may be the same person who stands behind the operator.
*   infrasstructure: is the physical or logical interconnections that the hacker uses to deliver a capability or maintain control of capabilities.
    *   Type 1: is the infrastructure controlled or owned by the hacker
    *   Type 2: is the infrastructure controlled by an intermediary. This has the job to obfuscating the source and attribution of the activity.
    *   Providers: are organizations that provide services considered critical for the adversary avaiability of Type 1 and Type 2.
*   capability: are the skill, tools and techniques used by the hacker
    *   Capacity: is all of the vulnerabilities and exposures that the individual capability can use
    *   Arsenal: is a set of capabilities that belong to an adversary.
*   victim: is the target of the adversary. 
    *   Personae: are the people and organizations being targeted and whose assets are being attacked and exploited.
    *   Assets: include the set of systems, networks, email, host, IP, addresses, social network accounts etc.
And two more:
*   social-political: describe the needs and intent of the adversary. P.E. financial gain, gaining acceptance, hacktivism or espionage.
*   technology: highlits the relationship between capability and infrastructure. They togheter describes how the hacker operates and communicates.
Plus we can add 6 more meta-feture, those are not required but can add valuable information about the diamond model:
*   Timestamp: it can include when the event is started and ended.
*   Phase: are the phases of an intrusion, attack or breach. An example is the Cyber Kill Chain.
*   Result: the results and post-conditions of an hacker's operation can be really valuable. It is crucial to capture them. They can be related to the CIA triad.
*   Direction: help describe host-based and network based events and represents the attack.
*   Methodology: allow an analyst to describe the general classification of intrusion(phishing DDoS, breach, port scan, etc)
*   Resources: every intrusion event needs one or more external resources to be satisfied to succeed.

## MITRE
APT(Advanced Persistence Threat), can be considered a team or coutry that engages a long-term attacks against organizations or countris.
TTP(Tactics, Techniques and Procedures):
*   Tactic: is the hacker goal
*   Technique: is the method to achieve that goal
*   Procedure: is how those techniques are executed 
CAR(Cyber Analytics Repository) is a knowledfe base of analytics developed by MITRE.
# MITRE ENGAGE
Is a framework for planning adversary engagement operations that empowers you to engage your adversaries and achieve your goals.
*   Cyber Denial: prevent the adversary's ability to conduct thei operations.
*   Cyber Deception: we intentionally plan artifacts to mislead the adversary.
MITRE formed an organization named CTID(Center of Threat-Informed Defense). This organization consists of various companies and vendors from around the globe.

## CTI(Cyber Threat Intelligence)
Evidence-based knowledge about adversaries, including their indicators, tactics, motivations and actionable advice against them.
In this environmente some common words change their meaning:
1. Data: IP addresses, URLs and hashes
2. Information: combination of multiple data points that answer questions sucha as "How much employees accessed a website within the mouth?"
3. Intelligence: the correlation of data and information to extract patterns of actions based on contextual analysis
Classification:
*   Strategic intel: intel that looks on organization's threat landscape and maps out the risk areas based on trends, patterns and emerging
*   Technical intel: evidence and artefacts of attack used by an adversary, incident response teeam use this intel to create a baseline attack surface to analyse and develop defence mechanisms
*   Tactical intel: take TTPs
*   Operational intel: looks for specific motives and intent to perform an attack

The CTI ligecycle:
*   Direction: every threat intel program need an objective and a goal, we can follow these parameters:
    *   information assets and business processes that require defending
    *   potential impact to be experienced on losing the assets or through process interruptions
*   Collection: once objectives have been defined, security analysts will gather the required data to address them. Analyst will do this by using commercial, private and open.source resources available.
*   Processing: raw logs, vulnerability information, malware and network traffic usually come in different formats and can be disconnected when used to investigate an incident.
*   Analysis: once the information gathering  is complete they must derive insights
    *   investigating a potential threat
    *   defending an action plan to avert an attacck and defend the infrastructure
    *   increase defense security controls or justifying investment for additional resources
*   Dissemination: differents stakeholders will consume the intelligence in varying languages and formats
*   Feedback: analysts rely on the response provided by stakeholders to improve the threat intelligence process and implementation of security controls

TAXII(The Trusted Automated eXchange of Indicator Information) defines protocols for securely exchanging threat intel to have near real-time detection, prevention and mitigation of threats. It supports 2 models:
*   Collection: threath intel is collected and hosted by a producer upon request by users using a request-response model
*   Channel: threath intel is pushed to users from a central server through a publish-subscribe model

STIX(Structured Threat Information Expression) is a language developed for the "specification, capture, characterisation and communication of standardised cyber threat information".

# Threat intelligence tools

*   Strategic intel: high level intel that looks into the organisation's threat landscape and maps out the risk areas based on trend, patterns and emerging threats that may impact business decision
*   Tecnical intel: looks for evidance used by an adversary, this can be used by response teams to create a baseline attack surface to analyse and develop defence mechanisms
*   Tactical intel: TTPs, this can improve security controls and address vulnerabilities through real-time investigations
*   Operational intel: looks for adversary's specific motives and intent to perform an attack, this can be used to understand the critical assets available in the organisation

[urlscan.io](https://www.urlscan.io)
[abuse.ch](https://www.abuse.ch) identify and tack malware and botnets through several operational platforms
