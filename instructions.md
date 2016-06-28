{{{
  "title": "NEM - Getting Started",
  "date": "06-27-2016",
  "author": "Ryan Todd",
  "attachments": [],
  "contentIsHTML": false,
  "sticky": true
}}}

### Overview of the NEM Runner job
We currently support with Runner two options for deploying NEM on a VM to get you up and running quickly.

1. Is an option to build a Ubuntu 14 server in the Data Center of your choice and deploy NEM upon it.
2. Is an option to deploy NEM to an Ubuntu 14 server that has been put into the CLC inventory and is already stood up.

### Prerequisites
* A CenturyLink Cloud Account
* A network existing in the Datacenter you want to deploy to. Run the network builder Runner job.

### Installation Process

1. Log into **runner.ctl.io**.
2. Search for **NEM** in the Public Products section then click on it
  ![Search NEM](../images/BaaS/nem1.png)
3. Click on run button
  ![Click on Run](../images/BaaS/nem2.png)
4. Choose the Datacenter you want to deploy a server to, CPU, and RAM. Recommend 2 CPU and 4 GB RAM
  ![Config Server](../images/BaaS/nem3.png)
5. It is now building your server and you should be able to hit the {new servers ip}:8989 in a web browser

### Running and Configuring a Supernode

1. cd into /opt/NEM/servant
2. vi config.properties 
3. You need to edit the following 
     nem.host = <put vps ip address here>
     servant.key = <put your NIS boot key here>
4. service servant start


### Troubleshooting
To make sure your services are running try the following

1. ssh into your server from a terminal(ex: ssh root@ipaddress)
2. Make sure nis and ncc are running by typing. screen -ls
3. You should see two sessions(3 if a supernode). One labeled somenumber.nis and another number.ncc
4. If one of them are missing you can type service nis start or service ncc start to bring back up
5. You can also go into the session for further trouble shooting by typing screen -r nis or screen -r ncc