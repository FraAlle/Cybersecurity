## Fast Flux

Is a DNS technique used by botnets to hide hishing, web proxying, malware delivery and malware communications activities behind compromised hosts acting as proxies. The true purpoes behind this technique is to hide the malware communication and make it hard for security professionals to discover the malware.
The primary concept it having multiple IP addresses with a domain name, which is constantly changing.

## TTPs(Tactics, Techniques & Procedures)

An example is the Pass-The-Hash attack: an attacker capture an hash password and pass it through for authentication and lateral access(is usable after gaining access to move deeper into a network searching for assets, the attacker maintains ongoing access by moving in the environment and obtaining more privileges) to other networked systems

## Cyber kill chain

This framework define the steps to make use for hackers.
1. Reconnaissance: is discovering and collecting info on the victim, utilizing OSINT(Open-Source Intelligence-> free services where you can found info about one person) too. Email harvesting is the process to obtain emails from public, paid or free services and can be used for an phishing attack. Some site to gather info are: [theHarvester](https://github.com/laramies/theHarvester) / [Hunter.io](Hunter.io) / [OSINT](https://osintframework.com/)
2. Weaponization
3. Delivery
4. Exploitation
5. Installation
6. Command & control
7. Actions on objectives