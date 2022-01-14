# Common Problems & their Solutions List :- 
## Problem with Installing Python 3.7 on Ubuntu with Apt
========================================================================
1. Start by updating the packages list and installing the prerequisites:
   - `sudo apt update`
   - `sudo apt install software-properties-common`
  
2. Next, add the deadsnakes PPA to your sources list:
   - `sudo add-apt-repository ppa:deadsnakes/ppa`

3. Once the repository is enabled, install Python 3.7 with:
    - `sudo apt install python3.7`
  
4. You can verify it by typing:
   - `python3.7 --version`


### Alternative [ Installing Python 3.7 on Ubuntu from Source ] :-
========================================================================

- `sudo apt update`
- `sudo apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libsqlite3-dev libreadline-dev libffi-dev wget libbz2-dev`
- `wget https://www.python.org/ftp/python/3.7.4/Python-3.7.4.tgz`
- `tar -xf Python-3.7.4.tgz`
- `cd Python-3.7.4`
- `./configure --enable-optimizations`
- `make -j 8`
- `sudo make altinstall`
- `python3.7 --version`


## Problem with Mysql Access denied for user issue
========================================================================

- `alter user 'root'@'localhost' identified with mysql_native_password by 'me123';`



## Problem with DNS Nameserver on Ubuntu 20.04 
========================================================================

#### like in my pc wifi was connected but no internet access

1. <h2 align="left">Change DNS Nameserver via GUI : </h2>
<a href="#"><img width="100%" height="auto" src="https://i.ibb.co/41bSrQw/Screenshot-from-2022-01-14-21-30-44.png" height="175px"/></a>

2. Change DNS Nameserver via Config File
   -  Go to the Netplan directory: `cd /etc/netplan`
   -  List the directory contents with ls to see the name of the yaml file containing network configuration.`sudo nano 01-network-manager.yaml`

- Replace the addresses located in the file with the DNS addresses you want to use. You can enter more than two addresses. Save the changes and exit.
<a href="#"><img width="100%" height="auto" src="https://i.ibb.co/kSZ0v3k/editing-netplan-yaml-file-in-nano.png" height="175px"/></a>

- Apply the changes you made in the config file:
- `sudo netplan apply`
- `systemd-resolve --status | grep 'DNS Servers' -A2`
