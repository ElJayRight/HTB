IP: 10.129.123.136

Nmap scan
open ports
 - 135
 - 139
 - 445
 - 8500

Port 445 is smb

connect with smbclient
smbclient -L {IP}
Enter WORKGROUP\kali's password: 

        Sharename       Type      Comment
        ---------       ----      -------
        ADMIN$          Disk      Remote Admin
        C$              Disk      Default share
        IPC$            IPC       Remote IPC
        WorkShares      Disk      

Access share
 smbclient \\\\10.129.123.136\\WorkShares

Get flag:
5f61c10dffbc77a704d76016a22f1664
