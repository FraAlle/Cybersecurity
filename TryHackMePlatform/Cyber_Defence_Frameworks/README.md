## Fast Flux

Is a DNS technique used by botnets to hide hishing, web proxying, malware delivery and malware communications activities behind compromised hosts acting as proxies. The true purpoes behind this technique is to hide the malware communication and make it hard for security professionals to discover the malware.
The primary concept it having multiple IP addresses with a domain name, which is constantly changing.

## TTPs(Tactics, Techniques & Procedures)

An example is the Pass-The-Hash attack: an attacker capture an hash password and pass it through for authentication and lateral access(is usable after gaining access to move deeper into a network searching for assets, the attacker maintains ongoing access by moving in the environment and obtaining more privileges) to other networked systems

## Cyber kill chain

This framework define the steps to make use for hackers.
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