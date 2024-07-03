BTS Archive Server Documentation
================================

The archive server is a virtual machine (VM) running on the DDaT-provided SU server on campus. 
This VM acts as a high-capacity network-attached storage medium, intended for use as a video/audio
archive, because such files are too big to transfer easily onto cloud services such as the BTS
GSuite.

The archive server may only be accessed from on campus (i.e. on devices connected to Eduroam/
Docking) or via the University VPN.

Access is possible via the "Map Network Drive" feature in Windows, Mac OS, or Linux. The
server access details are as follows:

- IP address: `138.38.11.55`
- Share name: `bts-archive`
- Username: `su2bc`
- Password: `[REDACTED]`

How to connect:
---------------

The "URL" format used to map the network drive is slightly different depending on the computer's
operating system. The URL includes one or more of the above details (IP address, share name, 
etc.). Once the URL is entered, the user is prompted to enter the username and password.

- Windows: `\\138.38.11.55\bts-archive`
  _Access by navigating to "This PC -> Toolbar -> Map Network Drive"_
  
- MacOS: `smb://138.38.11.55/bts-archive`
  _Access by navigating to "Finder -> Toolbar -> Go -> Connect to Server"_

- Linux (Ubuntu): `smb://138.38.11.55/bts-archive`
  _Access by navigating to "File Manager -> Connect to Server"_

Server details:
---------------

The archive server VM is an LXC container running on the aforementioned SU server. This VM runs
the _Samba_ software, which allows Linux folder(s) to be shared to Windows (or Windows-
compatible) computers by means of the well-established _SMB_ protocol.

To access the server VM, use SSH from Eduroam (or Docking) with the following credentials:

- Username: `su2bc`
- Password: `[REDACTED]`
