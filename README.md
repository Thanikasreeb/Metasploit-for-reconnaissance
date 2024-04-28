# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:

## OUTPUT:
![image](https://github.com/Thanikasreeb/Metasploit-for-reconnaissance/assets/119557910/1ad37629-9e67-4dad-8c7b-de19defe870c)

Invoke msfconsole:
![image](https://github.com/Thanikasreeb/Metasploit-for-reconnaissance/assets/119557910/c2d91081-ac30-41ce-b2d2-73051271ab73)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

![image](https://github.com/Thanikasreeb/Metasploit-for-reconnaissance/assets/119557910/7b4868ef-c1a3-4ed1-971b-cd3597fc326a)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) 
looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000 OUTPUT:
![image](https://github.com/Thanikasreeb/Metasploit-for-reconnaissance/assets/119557910/bd1a76be-e1e8-424c-822e-157cc699f2b2)

step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. 
In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24 OUTPUT:
![image](https://github.com/Thanikasreeb/Metasploit-for-reconnaissance/assets/119557910/77164e4e-59fe-44c1-ae6b-20eecf45663f)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's 
auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

 OUTPUT:
 
![image](https://github.com/Thanikasreeb/Metasploit-for-reconnaissance/assets/119557910/636912ae-8753-4654-be7b-ecfe44ad23fe)

Search is a powerful command in Metasploit that you can use to find what you want to locate. 
msf >search name:Microsoft type:exploit

The info command provides information regarding a module or platform, OUTPUT
![image](https://github.com/Thanikasreeb/Metasploit-for-reconnaissance/assets/119557910/e84a6dfb-720b-4a0e-ab1c-225c9d77b537)


Before beginning, set up the Metasploit database by starting the PostgreSQL server and 
initialize msfconsole database as follows: systemctl start postgresql msfdb init

MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use 
the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 
3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![image](https://github.com/Thanikasreeb/Metasploit-for-reconnaissance/assets/119557910/578273de-6faa-432d-80e6-b4936d73274d)

Use the search option to look for an auxiliary module to scan and enumerate 
the MySQL database. search type:auxiliary mysql 
![image](https://github.com/Thanikasreeb/Metasploit-for-reconnaissance/assets/119557910/cb758770-a154-4354-92ee-2e8a0955ac29)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to 
scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![image](https://github.com/Thanikasreeb/Metasploit-for-reconnaissance/assets/119557910/2cfe01fa-4972-4669-aaf7-cbebff225686)

Use the set rhosts command to set the parameter and run the module, as follows:
![image](https://github.com/Thanikasreeb/Metasploit-for-reconnaissance/assets/119557910/91a4f4f7-e7b5-411d-b82e-abd083e501f9)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![image](https://github.com/Thanikasreeb/Metasploit-for-reconnaissance/assets/119557910/8fdd50d6-4bd9-497c-b049-6d86fa5d7a07)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: 
set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with 
the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. 
set BLANK_PASSWORDS true
![image](https://github.com/Thanikasreeb/Metasploit-for-reconnaissance/assets/119557910/c466e1ff-a57b-4ab6-9e6c-88c7620957f9)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
