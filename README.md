#Documentation
#####DCM (DracOS Connection Manager) is a CLI (Command Line Interface) based program written in Python. This program help DracOS Linux's users to manage their connection ex: wifi connection
***
***
##Release
####V1.0 Dec 4th, 2016

##Installation
DCM needs some python module:
- colorama: `sudo pip install colorama`
- terminaltables: `sudo pip install terminaltables `
- pbkdf2: `sudo pip install pbkdf2`

DCM needs some program/binary in sudoers file's whitelist so it won't ask for password while executing those program:
- iwlist
- wpa_supplicant 
- dhclient
- pkill

Create directory `/usr/share/dcm` then clone/copy all dcm files on it. 

To make you easier in installing DCM, just use install.sh script. You just need to supply the active id that will use DCM as the parameter, ex: johndoe. So installation will be `sudo ./install.sh johndoe`  

##DracOS Connection Manager v1.0
Don't forget to run dcm as with `sudo dcm`, type `help` inside DCM to get information about available commands

![](screenshots/help.jpeg) 

###Dashboard section
####See available interfaces
DCM will detect interfaces on your system, categorize them into three types of interface (wireless, ethernet, localhost).
Use `show interface` to print those interface

![](screenshots/show_interfaces.jpeg) 

###Wifi-wizard section
####Specifying wireless interface to used by DCM
Before you can ask DCM to scan available networks and connecting to one of them using profile that you've been created (see profile explanation), you should specify wireless interface that DCM will use to do those activity, type `use [wireless_interface]`.

![](screenshots/use_interface.jpeg) 

####Scan available wifi networks
To scan available network, simply type `scan`.

![](screenshots/scan_networks.jpeg) 

####Creating profile
Profile in DCM is a configuration file that has information about wifi connection like SSID, type of connection (Open/WPA), and passphrase if the connection is WPA type.
To create a profile, simply input value to available option (name, ssid, type, passphrase) using `set name [value]`, `set ssid [value]`, `set type [value]`, `set passphrase [value]`. `show options` to see available options. For Open type connection, you just need to input name, ssid, and type, no need to supply passphrase information.
After all informations needed to create a profile have been provided, simply `save profile` and your profile will be saved. To see all information about all profiles that have been saved, type `show profile`.

![](screenshots/create_profile.jpeg) 

####Connecting to a network
To connecting DCM to a network use a specified profile name, type `connect [profile]`. To disconnect it, simply type `CTRL+C`.

![](screenshots/connect_wifi.jpeg)

 
