IP: 10.129.1.12

Nmap Scan
```bash
PORT    STATE SERVICE       REASON  VERSION
135/tcp open  msrpc         syn-ack Microsoft Windows RPC
139/tcp open  netbios-ssn   syn-ack Microsoft Windows netbios-ssn
445/tcp open  microsoft-ds? syn-ack
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:
|_clock-skew: 3h59m58s
| p2p-conficker: 
|   Checking for Conficker.C or higher...
|   Check 1 (port 65128/tcp): CLEAN (Couldn't connect)
|   Check 2 (port 64947/tcp): CLEAN (Couldn't connect)
|   Check 3 (port 11542/udp): CLEAN (Failed to receive data)
|   Check 4 (port 15467/udp): CLEAN (Timeout)
|_  0/4 checks are positive: Host is CLEAN or ports are blocked
| smb2-security-mode: 
|   2.02: 
|_    Message signing enabled but not required
| smb2-time: 
|   date: 2022-04-28T10:10:18
|_  start_date: N/A

```

Task 1.

- What does the 3-letter acronym SMB stand for? 

	- Server message block


Task 2.

- What port does SMB use to operate at? 
	- 445


Task 3.

- What network communication model does SMB use, architecturally speaking? 
	- client-server model


Task 4.

- What is the service name for port 445 that came up in our nmap scan? 
	- microsoft-ds


Task 5.

- What is the tool we use to connect to SMB shares from our Linux distribution? 
	- smbclient


Task 6.

- What is the `flag` or `switch` we can use with the SMB tool to `list` the contents of the share? 
	- -L


Task 7.

- What is the name of the share we are able to access in the end? 
	- workshares


Task 8.

- What is the command we can use within the SMB shell to download the files we find? 
	- get


Task 9.

- Submit the root flag:
	- Go into the WorkShares share
	```bash
	smbclient \\\\<ip>\\<share>
	```
	- then get the flag in James.P folder
	cat it out: 
	```
	5f61c10dffbc77a704d76016a22f1664
	``` 
