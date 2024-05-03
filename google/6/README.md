# Incident response lifecycle

CSIRT(Computer Security Incident Response Teams) are a specialized group of security professionals that are trained in incident management and reponse. There are multiple roles on an CSIRT team but these are always necessary:
* Security analyst: continuosly monitor an environment for any security threats. When an threath is found he escalate it to the appropriate team lead.
* Technical lead: manage all of the technical aspects of the incident response process, they do first determining the rppt cause of the incident, than elaborated the strategy to contain, eradicate and recover from the incident.
* Incident coordinator: coordinate with the relevant departments during a security incident, during so the lines of communication are open and clear. Incident coordinator can also be found in other team like SOC.

## SOC(Security operation center)

Is dedicated to monitoring networks, systems and devices for security threats or attacks. Normally if separated from the CSIRT team. A SOC is involved in various types of blue team activities, such as network monitoring, analysis and respons to incidents.

*   Tier 1(L1) analyst: monitoring, reviewing and prioritizing alerts based on criticality, creating and closing alerts using ticketing systems and escalating alert tickets to tier 2 or tier 3
*   Tier 2(L2) analyst: receiving escalated tickets from L1 and conducting deeper investigations, configuring and refining security tool and report to the SOC lead.
*   Tier 3(L3) lead: managing the operations of their team, exploring method of detection by performing advanced detection techniques and report to the SOC manager
*   SOC manager: hiring, training and evaluating the SOC team members, create perform metrics of the SOC team, develop reports related to incidents and communicate to stakeholder


The cybersecurity analyst investigate security alerts to determine if an incident has occurred. If something has been found the analyst will declare a critical rating of the incident. If the problem can be easily remediated by the analyst he can solve it alone, but if the problem is high critical, it gets escaleted to the technical lead.

Skills:
*   Command refers to having the appropriate leadership and direction to oversee the response.
*   Control refers to the ability to manage technical aspects during incident response, like coordinating resources and assigning tasks.
*   Communication refers to the ability to keep stakeholders informed.

## NIST lifecycle
*   Preparation
*   Detection and Analysis
*   Containment, Eradication, and Recovery
*   Post-incident activity

# Detection tools

**Intrusion detection system(IDS)** is an app that monitors system activity and alerts on possible intrusions. Provides continuos monitoring of network events to help protect against security threats or attacks. This don't stop or prevent the activity.
*       True positive: correctly detects the presence of an attack
*       True negative: no detection of malicious activity
*       False positive: incorrectly detects the presence of a threat.
*       False negative: the presence of a threat is not detected, this is when an malicious activity occurs but the IDS don't detect it.
**Intrusion prevention system(IPS)** is an application that monitors system activity for intrusive activity and takes action to stop it.(Some IDS tool can operate like IPS like Suricata,Snort and Sagan)
**Endpoint detection and response(EDR)** monitors endpoint for malicious activity and are installed on endpoints. These tools monitor, record and analyze endpoint activity to identify, alert and respond to suspicious activity. Only the EDR collecto endpoint activity data and perform behavioral analysis to identify threat patterns happening on an endpoint.

# How SIEM works

1: SIEM collect and aggregate data, this data is typically in the form of logs which are basically a record of all the events that happened. These data come from IDS or IPS, db, firewalls and applications.
2: Normalize data by taking all the raw data that SIEM has collected and cleans it up by removing non essential attributes so that only what's relevant is included.
3: The normalized data gets analyzed according to configured rules to detect any possible security incidents, then they get categorized or reported as alerts for security analysts to review.
Some SIEM tools are Chronicle and Splunk.

# Monitoring networks

Baseline in security help establish a standard of expected or normal behavior for systems, devices and networks, in less words, if you know the baseline of a normal network behaviour you'll be better able to identify abnormal network behaviour.
Once you have determinated a baseline you can monitor a network to identify any deviations from that baseline. Some example of network components that can be monitored:
**Flow analysis** refers to the movement of network communications and includes information related to packets, protocol and ports. Hackers can sue ports not commonly associated to maintain communications between the compomised system and their own machine. These communications are known as command and control(C2).
**Packet payload information** Network packets contian component related to the transmission of the packet, this include details like source and destination IP address and the packet payload information. Often this data is encrypted and requires decryption for it to be readable.
**Temporal patterns** Network packets contain information relating to time, this information is usefull to understand patterns.

Organizations may deploy a network operations center(NOC) which is an organizational unit that minitors the performance of a network and responds to any network disruption. A NOC is responsable for maintaining netwrok performance, availability and uptime.

Security analyst monitor networks to identify any sign of potential security incidents known as indicators of compromise(IoC) and protect networks from threats or attacks. IoCs help security analysts detect network traffic abnormalities by providing a way to identify an attack. IoCs provide analysts with specific evidence associated with an attack, such as a known malicious IP address, which can help quickly identify and respond to a potential security incident.

# Capture and view network traffic

A packet capture(P-cap) is a file containing data packets intercepted from an interface or network. It's used during incident investigation.

IPv4 packets camps:
```
Version: This field indicates the IP version. For an IPv4 header, IPv4 is used. 
Internet Header Length (IHL): This field specifies the length of the IPv4 header including any Options.
Type of Service (ToS): This field provides information about packet priority for delivery. It is provided in hexadecimal value.
Total Length: This field specifies the total length of the entire IP packet including the header and the data.
Identification: Packets that are too large to send are fragmented into smaller pieces. This field specifies a unique identifier for fragments of an original IP packet so that they can be reassembled once they reach their destination.
Flags: This field provides information about packet fragmentation including whether the original packet has been fragmented and if there are more fragments in transit(DF stands for Don'w fragment).
Fragment Offset: This field is used to identify the correct sequence of fragments.
Time to Live (TTL): This field limits how long a packet can be circulated in a network, preventing packets from being forwarded by routers indefinitely.
Protocol: This field specifies the protocol used for the data portion of the packet.
Header Checksum: This field specifies a checksum value which is used for error-checking the header.
Source Address: This field specifies the source address of the sender.
Destination Address: This field specifies the destination address of the receiver.
Options: This field is optional and can be used to apply security options to a packet.
The payload component directly follows the header and contains the actual data being delivered. Think back to the example of uploading an image to a website; the payload of this packet would be the image itself.
The footer, also known as the trailer, is located at the end of a packet. The Ethernet protocol uses footers to provide error-checking information to determine if data has been corrupted.
```

IPv6 packets camps:
```
Version: This field indicates the IP version. For an IPv6 header, IPv6 is used.
Traffic Class: This field is similar to the IPv4 Type of Service field. The Traffic Class field provides information about the packet's priority or class to help with packet delivery.
Flow Label: This field identifies the packets of a flow. A flow is the sequence of packets sent from a specific source. 
Payload Length: This field specifies the length of the data portion of the packet.
Next Header: This field indicates the type of header that follows the IPv6 header such as TCP.
Hop Limit: This field is similar to the IPv4 Time to Live field. The Hop Limit limits how long a packet can travel in a network before being discarded.
Source Address: This field specifies the source address of the sender.
Destination Address: This field specifies the destination address of the receiver.
```

# Incident detecrion methods

**Threat hunting** is the proactive search for threats on a network. Security professionals use threat hunting to uncover malicious activity that was not identified by detection tools and as a way to do further analysis on detections. Threat hunting is also used to detect threats before they cause damage. 

**Threat intelligence** is an evidence-based threat information that provides context about existing or emerging threats. These can come from private or public sources like:
*   Industry reports: often include details about attacker's tactics, techniques and procedures(TTP).
*   Government advisories: include details about attackers' TTP
*   Threat data feeds: provide a stream of threat-related data that can be used to help protect against sophisticated attackers like advanced persistent threats(APTs). By accessing additional information related to IoCs, security analyst can expand their viewpoint to obvserve the bigger picture.

**Cyber deception** involvers techniques that deliberately deceive malicious actors with the goal of increasing detection and improving defensive strategies.

**Honeypots** are systems or resources that are created as decoys vulnerable to attacks with the purpose of attracting potential intruders.

# Indicators of compromise 

Indicators of compromise(IoCs) are observable evidence that suggests sign of a potential security incident, the charts specific pieces of evidence that are associated with an attack. [Pyramid of pain](http://detect-respond.blogspot.com/2013/03/the-pyramid-of-pain.html).

**Indicator of attack(IoA)** are the series of observed events that indicate a real-time incident. Focus on identifying the behavioral evidence of an attacker.

# Crowdsourcing

Is the practice of gathering information using public input and collaboration. Threat intelligence platforms use crowdsourcing to collect information from the global cybersecurity community. Without this, attac,ers can performs the same attacks against multiple organizations.

# Documentation

**Digital forensic** is the process the practice of collecting and analyzing data to determine what has happened after an attack.

**Chain of custody** is the process of documenting evidence possession and control during incident lifecycle. Once the evidence gets collected the chain of custody forms are introduced.

There are 3 types of playbooks:
*   non-automated: require step by step actions from the analyst
*   automated: automate tasks in incident response processes(categorizing the severity of the incident or gahtering evidence, SOAR(Security Orchestration, Automation and Response) and SIEM can be configured as automated playbooks.)
*   semi-automated: combine automated tasks with human actions

# Triage

Before an alert get escaleted it goes through a triage process, which they prioritizes incidents according to their level of importance or urgency.
*   Receive and assess: this involves gathering as much information as possible about the alert, including details about the activity that triggered the alert
*   Assign priority: security teams must prioritize how they respond to various incidents because not all incidents are equal
*   Collect and analyze: involves gathering evidence from different sources, conducting external and document the investigative process.

**Resilience** is the ability to prepare for, respond to and recover from disruptions. An example is site resilience, is used to ensure the availability of networks, data centers or other infrastructure when a disruption happens.
*   Hot sites: is a duplicate of an organization's primary environment.
*   Warm sites: contains a fully updated and configured version of the hot site. These are not fully operational and available for immediate use but can quickly be made operational after a  failure or disruption occurs.
*   Cold sites: a backup facility equipped with some of the necessary infrastructure required to operate an organization's site. When a failure occurs, cold sites might not be ready to use and might need additional work to be operational.

# Logs

Types:
*   Netowrk: network devices create logs, like firewall, routers or switches.
*   System: generated by OS
*   Application: generated by software applications and contain information relating to the events occurring within the application such as a smartphone app.
*   Security: various devices or systems such as antivirus and IDS, they contain security-related information such as file deletion.
*   Authentication: generate whenever authentication occurs such as successful login attempt.

Authentication log example: ```Login Event [05:45:15] User1 Authenticated successfully```
More verbous: ```Login Event [2022/11/16 05:45:15.892673] auth_performer.cc:470 User1 Authenticated successfully from device1 (192.168.1.2)```

# Log formats

*   JSON(JavaScript Object Notation): is a file format used to store and transmit data, is easy to read and write and used in cloud environment
*       Key-value pairs: is a set of data that represents two linked items `"Alert":"Malware"`
*       Commas: are used to separate data `"Alert": "Malware", "Alert code": 1090, "severity": 10`
*       Double quotes: are used for text data
*       Curly brackets: 
        ```
        "User"
        { 
            "id": "1234", 
            "name": "user",
            "role": "engineer"
        }
        ```
*       Square brackets: use on arrays


*   Syslog
    ```
    <236>1 2022-03-21T01:11:11.003Z virtual.machine.com evntslog - ID01 [user@32473 iut="1" eventSource="Application" eventID="9999"] 
    This is a log entry!
    ```
    *   Header: timestamp(2022-03-21T01:11:11.003Z) hostname(virtual.machine.com) application (evntslog) and message ID(ID01)
    *   Structured-data: contains additional logging information `[user@32473 iut="1" eventSource="Application" eventID="9999"]` 
    *   Message: `This is a log entry!`
    *   Priority(PRI): `<236>`

*   XML: 
    *   Tags: uses tags to identify data
    *   Elements: all XML entries must contain at least one root element, the root contains child elements. 
        ```
        <Event>	
        <EventID>4688</EventID>
        <Version>5</Version>
        </Event>
        ``` 
    *   Attributes: are used to provide more information about elements, are included as the second part of the tag itself and must be always quoted 
        ```
        <EventData>
            <Data Name='SubjectUserSid'>S-2-3-11-160321</Data>
            <Data Name='SubjectUserName'>JSMITH</Data>
            <Data Name='SubjectDomainName'>ADCOMP</Data>
            <Data Name='SubjectLogonId'>0x1cf1c12</Data>
            <Data Name='NewProcessId'>0x1404</Data>
        </EventData>
        ```

# IDS

**Host based intrusiond detection systems(HIDS)** monitors the activity of the host where is installed.
**Network based intrusion detection system(NIDS)** collect and monitors network traffic and network data. Is installed on devices located at specific parts of the netwrork that you want to monitor.

# Signature based analysis
is a detection method that is used to find events of interest. A signature is a pattern that is associated with malicious activity, can cointain a sequence of bincary numbers, bytes or even specific data like IP addresses.
*   Low rate of false positive
*   Signatures can be evaded like making slight modification to the malware to altern his signature
*   Signatures requires updates: relies on a databse of signatures to detect threats
*   Inability to detect unknown threats

## Anomaly based analysis
identify abnormal behavior, there are two phases: the training phase(a baseline of normal or expected behavior must be established) and the detection phase(the current system activity is compared against this baseline). Baseline are developed by collecting data that corresponds to normal system behavior. Activity that happens outside of the baseline gets logged and an alert is generated.
*   Ability to detect new and evolving threats
*   High rate of false positive
*   Pre-existing compromise: the existence of an attacker furing the training phase will include malicious beheavior in the baseline

# Suricata

*   EVE JSON: extensible event format javascritp object notation
*   FAST LOG: record minimal alert information including basic IP address and port details about the network traffic
Suricata creates two types of log data:
*   Alert logs: cotain information that's relevant to security investigations, output of signatures which have triggered an alert.
*   Network telemetry logs: contain information about network traffic flows, network telemetry is not always security relevant, it's simply recording wht's happening on a network such as connection being made to a specific port.

## Alert
The alert keyword instructs to alert on selected network traffic. The IDS will inspect the traffic packets and send out an alert in case it matches.
Note that the drop action also generates an alert, but it drops the traffic. A drop action only occurs when Suricata runs in IPS mode.
The pass action allows the traffic to pass through the network interface. The pass rule can be used to override other rules. An exception to a drop rule can be made with a pass rule.
The reject action does not allow the traffic to pass. Instead, a TCP reset packet will be sent, and Suricata will drop the matching packet. A TCP reset packet tells computers to stop sending messages to each other.

# SIEM tools

Is possible to manually upload data or use software to help collect data for log ingestion. Manually uoloading data is inefficient so is possible to use log forwarding programs. These automatically collect and send log data.