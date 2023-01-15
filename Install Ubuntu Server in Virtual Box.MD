# Resources
## Downloads:
**Virtual Box:** https://download.virtualbox.org/virtualbox/7.0.4/VirtualBox-7.0.4-154605-Win.exe
**Ubuntu Server:** https://ubuntu.com/download/server
## Commands:
Run in order
1. sudo apt update
2. sudo apt install nginx
3. sudo systemctl status nginx
4. sudo ufw allow http
5. sudo ufw reload

# Steps
## Creating Virtual Machine:
1. Open virtual box manager
2. CLick on new
3. Give a new to Virtual Machine `Ubuntu Server`
4. Select the Ubuntu Server ISO image
5. Click `Next`
6. Give username `ubuntu`
7. Set a password
8. Set host name `Ubuntu`
9. Click `Next` 
10. Set Base Memory, `4096mb`
11. Processors `2 CPU`
12. Click `Next`
13. Disk size `25 GB`
14. Click `Next`
15. Review Summary
16. Click `Finish`
17. Close Virtual Machine. Need to setup network
18. Select `ubuntu Server` virtual machine
19. Click on `Network`
20. In Adapater 1, change to `Bridge Adapter` from `NAT`
21. Select your Machine's Driver in `Name`
22. Click `Ok`
23. Start virtual machine
## Install Ubuntu Server
**Use `TAB` to change selection**
1. Select install Ubuntu Server
2. Select your preferred language, `English`
3. If update is available, select `Update to new installer`
4. Select preferred, then click `Done`
5. Select `Ubuntu Server`, selected by default
6. In `Network connections` screen, select `Done`. As Network Adapater is already selected as Bridge, virtual machine will automatically select a IP address from DHCP server. Host machine can connect to virtual machine using this IP Address.
7.  If you have a proxy server in your network, then you need to add the proxy address. Let it remain empty, click on `Done`.
8.  No need to change, Mirror address. Clicl `Done`
9.  Select `Use an entire disk`, selected by default. Click `Done`
10.  Review system summary
11.  Click `Done`
12.  Click `Continue`
13.  Fill the form. **Name:** Ritwik Math, **Server name:** ubuntu, **username:** ubuntu, **password:** secret.
14.  Click `Done`
15.  Select `Install OpenSSH Server`, not selected by default
16.  Click `Done`
17.  Click `Done`. No need to select any software
18.  Once installation finished, click `Reboot Now`
## Verify Installation
1. Login using username and password
2. Run `ping google.com`
3. Run in order `sudo apt update`, `sudo apt install nginx`, `sudo systemctl status nginx` or `sudo systemctl is-active nginx`, `sudo fuw status`, if result is inactive then `sudo ufw enable`, `sudo ufw allow http`, `sudo ufw reload`
4. Type `ip addr` to get IP address, `192.168.0.195` IP addresses always change so check each time a new Virtual Machine is created
5. Open IP address in browser, Nginx welcome page should be visible
6. To use SSH, need to know the PORT on which OpenSSH is running
7. Run `sudo apt install net-tools`
8. Run `sudo netstat -ltnp | grep sshd` to check on which PORT OpenSSH is running
9. Run `sudo ufw allow 22/tcp`, assuming 22 is the port
10. Run `sudo ufw reload` and `sudo ufw status` to check 22 port is allowed
11. Opne terminal in Host. Run `ssh ubuntu@192.168.0.195` and enter yes if promted and then yes to login to system.
