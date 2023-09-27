## TERMINOLOGY

[Glossary](https://csrc.nist.gov/glossary)

**Compliance** is the process of adhering to internal standards and external regulations and enables organizations to avoid fines and security breaches.

[Security frameworks](Security_frameworks.md) are guidelines used for building plans to help mitigate risks and threats to data and privacy.

[Security controls](Security_controls.md) are safeguards designed to reduce specific security risks. They are used with security frameworks to establish a strong security posture.

**Security posture** is an organization’s ability to manage its defense of critical assets and data and react to change. A strong security posture leads to lower risk for the organization.

A **threat actor**, or malicious attacker, is any person or group who presents a security risk. This risk can relate to computers, applications, networks, and data.

An **internal threat** can be a current or former employee, an external vendor, or a trusted partner who poses a security risk. At times, an internal threat is accidental. For example, an employee who accidentally clicks on a malicious email link would be considered an accidental threat. Other times, the internal threat actor intentionally engages in risky activities, such as unauthorized data access.

**Network security** is the practice of keeping an organization's network infrastructure secure from unauthorized access. This includes data, services, systems, and devices that are stored in an organization’s network.

**Cloud security** is the process of ensuring that assets stored in the cloud are properly configured, or set up correctly, and access to those assets is limited to authorized users.

**Security audit** is a systematic evaluation of the security of a company's information system by measuring how well it conforms to an established set of criteria. 

**Social engineering** is a manipulation technique that exploits human error to gain private information, access, or valuables.

**Personally identifiable information (PII)**: Any information used to infer an individual’s identity

**Sensitive personally identifiable information (SPII)**: A specific type of PII that falls under stricter handling guidelines

## ATTACKS

**Phishing**:
*    *Business Email Compromise (BEC)*:A threat actor sends an email message that seems to be from a known source to make a seemingly legitimate request for information, in order to obtain a financial advantage.
*    *Spear phishing*: A malicious email attack that targets a specific user or group of users. The email seems to originate from a trusted source.
*    *Whaling*: A form of spear phishing. Threat actors target company executives to gain access to sensitive data.
*    *Vishing*: The exploitation of electronic voice communication to obtain sensitive information or to impersonate a known source.
*    *Smishing*: The use of text messages to trick users, in order to obtain sensitive information or to impersonate a known source.

**Supply-chain attack** target systems, applications, hardware and software to locate vulnerabilities.

**Cryptographic attack** affects secure forms to communicate between sender and reciver.
*    *Birthday*
*    *Collision*
*    *Downgrade*


## CISSP DOMAINS

**Security and risk managment** focuses on defining security goals and objectives, risk mitigation, compliance, business continuity, and the law(security analysts may need to update company policies related to private health information if a change is made)
**Asset security** ensecure physical and digital assets, is related to storage,maintenance, retention and descrution of data.
**Security architecture and engineering** focuses in optimazing data security by ensuring effective tools, systems and processes(setup a firewall).
**Communication and network security** focuses on managing and securing physical networks and wireless communications.
**Identity and access management** focuses on keeping data secure by force users follows certain polices to control and manage physical assets and logic assets.
**Security assessment and testing** focuses on conducting security control testing, collecting and analyzing data and conducting security audits to monitor for risks, threats and vulnerabilities(set up differents access levels for each user). 
**Security operations**  focuses on conducting investigations and implementing preventative measures.
**Software development security** focuses on using secure coding practice.

## COMMON TOOLS

SIEM is an application that collects and analyzes log data to monitor critical activities.
Splunk is a data analysis platform. Splunk Enterprise is used to retain, analyze and search an organization's log data.
Google's Chronicle, is a cloud native SIEM that stores security data for search and analysis.
Playbook is a manual that provides details about any operational action(how to respond to an accident), these change from company to another.

*    **Chain of custody** is the process of documenting evidence possession and control during an incident lifecycle.

*    **Protecting and preserving evidence** is the process of properlyworking with fragile and volatile digital evidence, understand wich ones are fragile and volatiles is crucial. You will consult the *order of volatility* which is a sequence outlining the order of data that must be preserved from first to alst(it prioritizes volatile data). 

Network protocol analyzer(packet sniffer).