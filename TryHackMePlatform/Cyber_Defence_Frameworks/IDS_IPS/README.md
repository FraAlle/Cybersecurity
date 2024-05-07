# SNORT
## directory utili
/etc/snort/snort.conf
/etc/snort/rules/local.rules

## Tipi di controlli IPS
*   Full: da tutte le informazioni possibili, in piú si crea un file con tutte le allerte che vengono trovate, posso crearne una io usando -l <directory>
*   cmg: da dettagli sull'header dei pacchetti che fanno saltare l'allerta
*   console: riassunto, displaya il minutaggio e il messaggio specificato nella regola, mi ha salvato un log con solo le detection della regola inserita(in questo caso mi ha creato un log con solo pacchetti ICMP)

## SNORT rules
IP Filtering	
alert icmp 192.168.1.56 any <> any any  (msg: "ICMP Packet From "; sid: 100001; rev:1;)
This rule will create an alert for each ICMP packet originating from the 192.168.1.56 IP address.

Filter an IP range  
alert icmp 192.168.1.0/24 any <> any any  (msg: "ICMP Packet Found"; sid: 100001; rev:1;)
This rule will create an alert for each ICMP packet originating from the 192.168.1.0/24 subnet.

Filter multiple IP ranges
alert icmp [192.168.1.0/24, 10.1.1.0/24] any <> any any  (msg: "ICMP Packet Found"; sid: 100001; rev:1;)
This rule will create an alert for each ICMP packet originating from the 192.168.1.0/24 and 10.1.1.0/24 subnets.

Exclude IP addresses/ranges
"negation operator" is used for excluding specific addresses and ports. Negation operator is indicated with "!"
alert icmp !192.168.1.0/24 any <> any any  (msg: "ICMP Packet Found"; sid: 100001; rev:1;)
This rule will create an alert for each ICMP packet not originating from the 192.168.1.0/24 subnet.

Port Filtering	
alert tcp any any <> any 21  (msg: "FTP Port 21 Command Activity Detected"; sid: 100001; rev:1;)
This rule will create an alert for each TCP packet sent to port 21.

Exclude a specific port
alert tcp any any <> any !21  (msg: "Traffic Activity Without FTP Port 21 Command Channel"; sid: 100001; rev:1;)
This rule will create an alert for each TCP packet not sent to port 21.

Filter a port range (Type 1)
alert tcp any any <> any 1:1024   (msg: "TCP 1-1024 System Port Activity"; sid: 100001; rev:1;)
This rule will create an alert for each TCP packet sent to ports between 1-1024.

Filter a port range (Type 2)
alert tcp any any <> any :1024   (msg: "TCP 0-1024 System Port Activity"; sid: 100001; rev:1;)
This rule will create an alert for each TCP packet sent to ports less than or equal to 1024.

Filter a port range (Type 3)
alert tcp any any <> any 1025: (msg: "TCP Non-System Port Activity"; sid: 100001; rev:1;)
This rule will create an alert for each TCP packet sent to source port higher than or equal to 1025.

Filter a port range (Type 4)
alert tcp any any <> any [21,23] (msg: "FTP and Telnet Port 21-23 Activity Detected"; sid: 100001; rev:1;)
This rule will create an alert for each TCP packet sent to port 21 and 23.

## Rules types
**General**: fundamentals rules for snort
**Payload**: help investigate payload data
*   Content: `alert tcp any any <> any 80  (msg: "GET Request Found"; content:"GET"; sid: 100001; rev:1;)` in ASCII or `alert tcp any any <> any 80  (msg: "GET Request Found"; content:"|47 45 54|"; sid: 100001; rev:1;)` in HEX
*   Nocase: ignore the case sentivity   `alert tcp any any <> any 80  (msg: "GET Request Found"; content:"GET"; nocase; sid: 100001; rev:1;)`
*   Fast_pattern: prioritise the content search to speed up `alert tcp any any <> any 80  (msg: "GET Request Found"; content:"GET"; fast_pattern; content:"www";  sid:100001; rev:1;)`
**Non-payload**: is used to identify network issues
*   ID: `alert tcp any any <> any any (msg: "ID TEST"; id:123456; sid: 100001; rev:1;)`
*   Flasg: F - FIN // S - SYN // R - RST // P - PSH // A -ACK // U - URG `alert tcp any any <> any any (msg: "FLAG TEST"; flags:S;  sid: 100001; rev:1;)`
*   Dsize: filter by size `alert ip any any <> any any (msg: "SEQ TEST"; dsize:100<>300;  sid: 100001; rev:1;)`
*   Sameip: filtering source and destination IP addresses for duplication `alert ip any any <> any any (msg: "SAME-IP TEST";  sameip; sid: 100001; rev:1;)`