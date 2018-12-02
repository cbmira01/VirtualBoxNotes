# VirtualBoxNotes
Notes on Oracle VirtualBox and Bitnami virtual machines.

Install Oracle VirtualBox on Windows 7 or 10
- check Windows 64-bit
- check at least 4GB memory
- enable virtualization and VT-d in BIOS; save settings
- recycle power and reboot may be needed after BIOS setup
- check HyperV disabled
- install Oracle VirtualBox
- check 64-bit guests can be hosted by Oracle VirtualBox
- check host IP address appears on 192.168.56.1

Install Oracle VirtualBox on Mac
- https://stackoverflow.com/questions/13580491/how-to-enable-support-of-cpu-virtualization-on-macbook-pro
- https://www.youtube.com/watch?v=lEvM-No4eQo

Install SSH tools for Windows
- Putty
- WinScp

Install SSH tools for Mac
- https://accc.uic.edu/answer/how-do-i-use-ssh-and-sftp-mac-os-x

Bitnami LAMP stack VM instructions
- download the Bitnami LAMP stack OVA (Oracle VirtualBox Archive)
- check MD5 hash: http://onlinemd5.com/
- start Oracle VirtualBox, import OVA
- check guest: Type="Linux", Version="Debian 64-bit"
- check guest: video memory >= 24 MB
- check guest: network card set to host-only
- boot the guest (look for double-splash)
- note application password on the splash screen
- login to guest (bitnami/bitnami)
- note guest's IP address (sudo ifconfig)
- set Bitnami user password if desired
- enable sshd on Bitnami guest
- sudo reboot
- sudo shutdown -h now

Login to LAMP stack
- create Putty connections to the VM for console and tunnel
- create a WinSCP connection to the VM for file transfer
- check all stack services are available: sudo /opt/bitnami/ctlscript.sh status

Debian administration notes
- enable ssh daemon
	sudo rm -f /etc/ssh/sshd_not_to_be_run  
	sudo systemctl enable ssh  
	sudo systemctl start ssh  
  
Clone and run PHP projects from Github
- Simple LAMP Web Application https://github.com/qyjohn/simple-lamp
- Neighborhood Web Site https://github.com/cbmira01/NWS
