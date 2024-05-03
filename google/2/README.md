# More about CISSP

**Security and risk managment** these are some of the usage areas:
*   **Defining security goals** can reduce risks to critical assets and data like PII
*   **Risk mitigation** means having the right procedures and rules in place to quickly reduce the impact of a risk.
*   **Compilance** is the primary method used to develop an organization's internal security policies, regulatory requirements and independent standards.
*   **Business continuity** relates to an organizatoin's ability to maintain productivity everyday by establishing risk disaster recovery plans.

**Asset security** is focused on securing digital and physocal assets, it also is related with storage, maintenance, retention and destruction of data.
**Security architecture and engineering** is focues on optimizing data security by ensuring effective tools, systems and procedded are in place to protect an organization's assets and data. The core concept is the *shared responsibility*(means that all individuals within an organization take an active role). 
**Communication and network security** is focused on managing and securing physical networks and wirless communications.
**Identity and access management(IAM)** his focus is on garantee acces and authorization to keep data secure by making follow established policies to control and manage assets.
**Security assessment and testing** this focues on conducting security control testing, collecting and analyzing data and conducting security audits to monitor for risks, threats and vulnerabilities. F.E. implement a 2 authenticator factor.
**Security operations**  is focused on conducting investigations and implementing preventative measures.
**Software development security** this focuses on using secure coding practices.

# National Institue of Standards and Technology(NIST) Risk Managment Framework(FRM)

*   **Prepare** refers to actions necessary to manager security and privacy risks before a breach occurs.
*   **Categorize** is used to develop risk management processes and tasks.
*   **Select** means to choose, customize and capture documentation of the controls that protect an organization.
*   **Implement** security and privacy plans for the organization.
*   **Assess** means to determine if established controls are implemented correctly.
*   **Authorize** means being accountable for the security and privacy risks that may exist in an organization.
*   **Monitor** means to be aware of how systems are operating.

## [Risks](risks.md)

## [Vulnerabilities](vulnerabilities.md)

## [CSF Framework](CSF_framework.m)

## [Open Web Apllication Security Project](OWASP.md)

## [Security audits](Security_audits.md)

## Log

*   **Firewall log** is a record of attempted connections for incoming traffic from the internet.
*   **Network log** is a record of all computers and devices that enter and leave the network.
*   **Server log** is a record of events related to services such as websites, emails or files shares.

SIEM tool is an application that colllects and analyzes log data to monitor critical activities in an organizaition.

## Differents SIEM tools

*   **Self hosted SIEM tools** require organizations to install. operate and mantain the tool using thei own physical infrastructure such as server capacity. Then these applications are managed and maintained by the IT departament. This is required when an organization is required to maintain physical control over confidential data.
*   **Cloud hosted SIEM tools** are maintened by the SIEM providers, making them accessible through the internet.
*   **Hybrid solution** is used to take the advantages from the cloud solution but maintaining physical control over confidential data.

*Splunk*

Some of the common SIEM tools are Splunk Enterprise, Splunk Cloud and Chronicle.
Splunk is a data analysis platform and the enterprise version provides SIEM solutions. Is a self hosted tool used to retain, analyze and search an organization's log data to provide security information and alerts in real time.
Splunk cloud is a cloud based hosted used to collect, search and monitor log data. It can be used for organization running hybrid or cloud only environments.
Splunk dashboards:
*   **Security posture dashboard** is designed for security operations centers(SOCs). It displays the last 24 hours of an organization's notable security-related events and trend and allowa security professionals to determine if security infrestructure an d policies are performing as designed.
*   **Executive summary dashboard** analyzed and monitors the overall health of the organization over time, this helps security teams improve security measures that reduce risk.
*   **Incident review dashboard** allows analysts to identify suspicious patterns that can occur in the event of an incident. It highlighting higher risk items that need immediate review by an analyst. This provide an visual timeline of the events leading up to an incident.
*   **Risk analysis dashboard** helps identify risk for each object(IP). It shows changes in risk-related activity or behaviour, such as a user logging in outside of normal working hours or unusually high network traffic from a specific computer.

*Google Chrnonicle*

Google Chronicle is a cloud native tool that provides log monitoring, data analysis and data collection. It helps u collecting and analyzing log data according to:
*   A specific asset
*   A domain name
*   A user
*   An IP address
His dashboard are:
*   **Enterprise insights dashboard** identifies suspicious domain names in logs(indicators of compromise IOCs). Each result is labeled with a confidence score to indicate the likelihood of a threat. It also provides a severity level that indicates the significance of each threat to the organization. It is used to monitor login acccess attempts related to critical assets.
*   **Data ingestion and health dashboard** shows the number of event logs, log sources and success rates of data being proceseed into Chronicle. This is used to ensure that log sources are correctly configured and that logs are received withouth error.
*   **IOC matched dashboard** indicate the top threats, risk and vulrenabilities to the organization. Pro uses this dashboard to observe domain names, IP and devices IOCs over time in order to identify trends.
*   **Main dashboard** displays a high-level summary of information related to the organization's data ingestion, alerting and event activity over time.
*   **Rule detections dashboard** provides statistics related to incidents with the ighest occurrences, severities and detections over time. This dashboard is used to access a list of all the alerts triggered by a specific detection rule, such as rule designed to alert wheever a suer opens a known malicious attachment from an email.
*   **User sign in overview dashboard** provides information about user access behaviour acress the organization, can use this dashboard to access a list of all user sign-in events to identify unusual user activity, such as a user signing in from multiple locations at the same time.

