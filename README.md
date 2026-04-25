# Navigation 🗺️
* [Overview](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki#overview-)
* [Infrastructure ](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki#infrastructure-%EF%B8%8F)
    * [Overview of Infrastructure](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki#overview-of-infrastructure-)
    * [Network Diagram](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki#network-diagram-)
* [Milestones](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki#milestones-)
* [RVTM](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki#rvtm-%EF%B8%8F)

# Overview ❓ 

Our final project involved building medium-sized enterprise from scratch for a client over the course of three weeks. 

# Infrastructure 🏘️  
## Overview of Infrastructure 📑 

| Hostname | LAN IP           | Description                                       | Notes                                                              |
|----------|------------------|---------------------------------------------------|--------------------------------------------------------------------|
| [FW01](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki/FW01)     | 172.16.1.2       | PFSense Firewall between SYS265-WAN and GROUP-LAN | WAN on 10.0.17.77 LAN on 172.16.1.2 WAN Assignments                |
| [DOCKER01](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki/DOCKER01)   | 172.16.1.5       | Ubuntu                                            | Docker Dockerized CMS                                              |
| [DHCP01](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki/DHCP01)   | 172.16.1.10      | CentOS 7                                          | Redundant DHCP Controlled by Ansible via SSH/RSA Keys              |
| [DHCP02](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki/DHCP02)   | 172.16.1.11      | CentOS 7                                          | Redundant DHCP  Controlled by Ansible via SSH/RSA Keys             |
| [DC01](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki/DC01)     | 172.16.1.12      | Server 2019 Core                                  | Redundant ADDS and DNS Services                                    |
| [DC02](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki/DC02)     | 172.16.1.13      | Server 2019 Core                                  | Redundant ADDS and DNS Services                                    |
| [MGMT01](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki/MGMT01)   | 172.16.1.14      | Server 2019 GUI                                   | Management                                                         |
| [MGMT02](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki/MGMT02)   | 172.16.1.20      | Ubuntu                                            | Ansible/Network Management                                         |
| [WKS01](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki/WKS01)    | 172.16.1.100-150 | Windows 10                                        | DHCP Client/Domain Joined .100-.150                                |
| [WKS02](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki/WKS02)    | 172.16.1.100-150 | Windows 10                                        | DHCP Client/Domain Joined .100-.150                                |
| [DFS01](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki/DFS01)    | 172.16.1.21      | Server 2019 Core                                  | Distributed File System that Stores Domain User Profiles & Desktop |
| [DFS02](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki/DFS02)    | 172.16.1.22      | Server 2019 Core                                  | Distributed File System that Stores Domain User Profiles & Desktop |
| [UTIL01](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki/UTIL01)   | 172.16.1.15      | CentOS 7                                          | Domain Joined                                                      |

## Network Diagram 🌐 

![Network Diagram drawio (1)](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/assets/122812369/fc97a297-c87b-4d55-aa72-f3ddc22611d8)

# Milestones 📝 
| Milestone:  | Description:                                                                                                                                                                                                                                                                                                                                                                           |
|-------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Milestone 1](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki/Milestone-1) | • Incorporating the following GitHub features: Wiki, Issues, Labels, Milestones and Boards <br> • Routing works (systems can talk to one another and route to the internet) <br> • Domain Users are created <br> • Domain Joined WKS01, WKS02 <br> • Redundant ADDS (this means that either can be down and that domain services are still provided) <br> • Documentation Updated <br> |
| [Milestone 2](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki/Milestone-2) | • Incorporating the following GitHub features: Wiki, Issues, Labels, Milestones and Boards <br> • Redundant Linux DHCP works <br> • Ansible Controller and nodes are configured <br> • UTIL01 is domain joined <br> • MGMT02 configured <br> • Documentation Updated <br>                                                                                                              |
| [Milestone 3](https://github.com/Isaiah-River/SYS-265-02-SYS-Admin-II-Final-Project/wiki/Milestone-3) | • Incorporating the following GitHub features: Wiki, Issues, Labels, Milestones and Boards <br> • Docker service is deployed <br> • DFS based profiles <br> • Ansible Services <br> • Ansible Users <br> • Group Policy completed <br> • Final Documentation Complete <br>                                                                                                             |
# RVTM ☑️ 

| Requirement | Description                                                                                                                                                                                                                                             | Test |
|-------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|
| 1           | Redundant AD infrastructure using DC1 + DC2. One should be able to turn off DC1 or DC2, and still be able to manage AD and login via W1 + W2 + MGMT1.                                                                                                   | 1    |
| 2           | DHCP1 and DHCP2 should provide DHCP services to your LAN. They should also be redundant. Turn off DHCP1 or 2 and ipconfig/release and /renew from W1.                                                                                                   | 1    |
| 3           | MGMT2 will be an Ansible controller system that can control your entire domain, with the exception of Windows workstations and the firewall. You should be able to run interactive commands against all these systems.                                  | 1    |
| 4           | UTIL01 will be a system that you can provision with a new application via MGMT2 and Ansible. It can also be used to assist in meeting other requirements. Deploy an application that has not been covered in class to UTIL01 using an Ansible Playbook. | 1    |
| 5           | MGMT1, DC1, DC2, DFS1, DFS2 and your workstations represent your Active Directory Infrastructure. Your domain should be your groupname.local. Join all Windows systems to the domain and at least one of your Linux systems.                            | 1    |
| 6           | Create an AD security group called linux-admins. Members of this group should be able to sudo to root on one of your Linux systems (this has some implied sub-requirements).                                                                            | 1    |
| 7           | Install docker and a wiki/application of your choice on docker. (NOT WORDPRESS!)                                                                                                                                                                        | 1    |
| 8           | Create a Domain Group Policy that allows W1 + W2 to remote desktop between one another.                                                                                                                                                                 | 1    |
| 9           | Create a Domain Group Policy that applies corporate wallpaper to W1 + W2 + MGMT1.                                                                                                                                                                       | 1    |
| 10          | Create a Domain group policy that moves W1 and W2 user profiles and home directories to a DFS share.                                                                                                                                                    | 1    |
| 11          | Use Ansible to install an apt-package.                                                                                                                                                                                                                  | 1    |
| 12          | Use Ansible to install a yum package.                                                                                                                                                                                                                   | 1    |
| 13          | Use Ansible to add a new Linux local user can be an SSH user or one with a password.                                                                                                                                                                    | 1    |
| 14          | Use Ansible to add a new Windows domain user.                                                                                                                                                                                                           | 1    |
