BTS Archive Server Documentation
================================

The archive server is a virtual machine (VM) running on the DDaT-provided SU server on campus. 
This VM acts as a high-capacity network-attached storage medium, intended for use as a video/audio
archive for Backstage, because such files are too big to transfer easily onto cloud services such 
as the BTS GSuite.

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

Unlike a cloud service such as Google Drive, the shared drive on the archive server is "mapped"
directly into the computer's file manager. This means that, in effect, it appears to the
computer as a USB stick or hard drive. For large files, this is particularly advantageous as it
mitigates the need to upload/download large volumes of data through a web browser.

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

The archive server VM is implemented as a Ubuntu LXC container running on the aforementioned 
SU server. This VM runs the _Samba_ software, which allows Linux folder(s) to be shared to 
Windows (or Windows-compatible) computers by means of the well-established _SMB_ protocol.

To access the server VM, use SSH from Eduroam (or Docking) with the following credentials:

- Username: `su2bc`
- Password: `[REDACTED]`

Upon successful login, one is greeted with a regular Bash shell, from which administrative
commands may be run.
