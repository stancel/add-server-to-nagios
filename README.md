add-server-to-nagios
=========

Ansible playbook to install the Nagios NRPE client program onto a server and then added the needed config onto the Nagios4 monitoring server.


How to Use
------------

To use this playbook just run this command.

	1. ansible-galaxy install -r requirements.yml -p roles/ --force
	2. Create a file called .vault_pass in this folder and put a random string in it for decrypting your sensitive variables. Something like: QSkngTv#KTJ=WXpg6qVR
	3. Fill out needed variables in vars/all_vars.yml and vars/vault.yml files
	4. ansible-vault encrypt vars/vault.yml   #Encrypt the sensitive variables

Execution: 
  	
```
	ansible-playbook master.yml -e @vars/all_vars.yml -i /Users/Brad/.ansible/hosts
```


Requirements
------------

Used for personal / internal use. Must use Nagios for monitoring.

Variables
------------

Fully qualified domain name of your Nagios Server.
```
nagios_server_fqdn: "nagios.mydomain.com"
```
The fully qualified domain name or IP address of the machine you are adding to be monitored.
```
server_fqdn: "myserver-to-monitor.com"   
```
The hostname of the machine you are monitoring. Host names should not have spaces in them.
```
host_name: "my-server"   
```
The alias or Nagios friendly name to show in Nagios as the computer being monitored.
```
nagios_friendly_name: "My Important Server"    
```


Roles
------------

	- stancel.add-config-to-nagios-server	
	- stancel.install-nagios-client	

