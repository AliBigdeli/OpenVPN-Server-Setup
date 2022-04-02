<h1 align="center">OpenVpn Server Setup</h1>
<h3 align="center">This is a tutorial to create open vpn server with user profiles to connect</h3>
<p align="center">
<a href="https://www.arduino.cc/" target="_blank"> <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/f5/OpenVPN_logo.svg/2560px-OpenVPN_logo.svg.png" alt="arduino" width="30%"/> </a> 

### Overview
- [Overview](#overview)
- [Requirements](#requirements)
- [Step 1 (getting ready)](#step-1-getting-ready)
- [Step 2 (setup server)](#step-2-setup-server)
- [Step 3 (create user)](#step-3-create-user)
- [Step 4 (download .ovpn)](#step-4-download-ovpn)
- [Step 5 (setup more clients)](#step-5-setup-more-clients)
- [Adding more users](#adding-more-users)



### Requirements

first of all you need to have a vps running ubuntu/centos/redhat
then in order to create connect to the server and make modifications your gonna need these programs:
- Putty 
- Filezilla or WinSCP
- OpenVpn Client (desktop/mobile)
### Step 1 (getting ready)
1- Create a directory where you want to store OpenVpn Configurations 
```shell
mkdir OpenVpn
```

2- then download the openvpn installer script through the command bellow
```shell
wget https://raw.githubusercontent.com/angristan/openvpn-install/master/openvpn-install.sh
```

3- change the mode of the file to be executable
```shell
chmod +x openvpn-install.sh
```

4- in order to run the script you need to have sudo permissions so add the sudo in the begging of the command for running the script and
```shell
sudo ./openvpn-install.sh
```

### Step 2 (setup server)

1- Keep the default ip and hit "Enter"

2- Do you want to enable IPv6 support (NAT)? (y/n): n

3- what port do you want OpenVpn to listen to? Port Choice [1-3]: 1

4- what protocol do you want OpenVpn to use? Protocol [1-2]: 1

5- what DNS resolvers d you want to use with the VPN? DNS[1-12]: 9 Google

6- do you want to use compression? [y/n]: n

7- do you want to customize encryption settings? [y/n]: y

8- choose which cipher you want to use for the data channel? [1-6]: 1

9- choose what kind of certificate you want to use? [1-2]: 1

10- choose which curve you want to use for the certificate's key? [1-3]: 1

11- choose which cipher you want to use for the control channel? [1-2]: 1

12- choose what kind of Diffie-Hllman key you want to use? [1-2]: 1

13- choose which curve you want o use for the ECDH key? [1-3]: 1

14- which digest algorithm do you want to use for HMAC? [1-3]: 1

15- you can add an additional layer of security to ...
Control channel additional security mechanism [1-2]: 1

16- Press any key to continue... (hit enter)

'''Wait until the process finish'''


### Step 3 (create user)
in order to use the server after setup you will need user profiles to be created:

1- Client name: "Enter any name you want for example: vpn-user-1"
2- do you want to protect the configuration file with a password?: [1-2]: 1
after this step user have been added and the installation is done

### Step 4 (download .ovpn)
in order to download the configuration file you have to connect to the server with any ftp client and downloading the username.ovpn file you already created to your system.

### Step 5 (setup more clients)
for client side just install openvpn app on your mobile or desktop and import the openvpn profile. then hit connect to start connecting to the server and enjoy using it.


### Adding more users
each profile can be connected by one device per time and for each device you have to create one seperated file. so again follow these steps to create more users:

1- run the script again
```shell
sudo ./openvpn-install.sh

```
2- select the 

    1) Add a new user

3- give a new user name

4- set no password 

5- download the .ovpn file and setup your vpn for connection





