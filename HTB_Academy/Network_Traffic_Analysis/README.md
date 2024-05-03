# Protocol Data Units(PDU)

PDU is a packet made up of control information and data encapsulated from each layer of the OSI model.
https://academy.hackthebox.com/storage/modules/81/pdu-wireshark.png

# HTTPS handshake
1. Client and server exchange hello messages to agree on connection parameters.
2. Client and server exchange necessary cryptographic parameters to establish a premaster secret.
3. Client and server will exchange x.509 certificates and cryptographic information allowing for authentication within the session.
4. Generate a master secret from the premaster secret and exchanged random values.
5. Client and server issue negotiated security parameters to the record layer portion of the TLS protocol.
6. Client and server verify that their peer has calculated the same security parameters and that the handshake occurred without tampering by an attacker.

# FTP(File Transfer Protocol)

Insecure protocol, because has been developed the SFTP. Use port 20 for file transfer, port 21 for using commands.
It goes on:
*   active: the server listens for a control command PORT from the client, starting what port to use for data tranfer
*   passive: access FTP servers located behind firewalls or a NAT-enable link that makes direct TCP connection impossible, in this case the client send the PASV command and wait for response from the server informing with the client IP and the port to utilize for the data transfer

Commands:
*   USER	specifies the user to log in as.
*   PASS	sends the password for the user attempting to log in.
*   PORT	when in active mode, this will change the data port used.
*   PASV	switches the connection to the server from active mode to passive.
*   LIST	displays a list of the files in the current directory.
*   CWD	    will change the current working directory to one specified.
*   PWD	    prints out the directory you are currently working in.
*   SIZE	will return the size of a file specified.
*   RETR	retrieves the file from the FTP server.
*   QUIT	ends the session.

# Server Message Block(SMB)

is an connection-oriented protocol that requires user authentication from the host to the resource to ensure the user has correct permissions to use that resource. Support TCP transport over port 445, NetBOIS over port 139.