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
Find out the ip address of the attackers system

## OUTPUT:

![244957536-3124bd5e-f8c7-49c8-843f-f798d3c2a6fc](https://github.com/prithviraj5703/Metasploit-for-reconnaissance/assets/121418418/6a92561c-0161-4c39-ac80-3ad69b6ccb64)

Invoke msfconsole:

![244957563-ab8fc40d-0e55-40fb-aa28-a2567dffd231](https://github.com/prithviraj5703/Metasploit-for-reconnaissance/assets/121418418/747e0baf-678d-42f1-9142-3329af318d37)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

![244957577-9418b63d-9976-49f0-b2f1-23f505936edf](https://github.com/prithviraj5703/Metasploit-for-reconnaissance/assets/121418418/eea3b4bc-f2f2-42c7-b9e5-e94b7ecd2671)


### Port Scanning:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

### Output:

![244957590-3e461f4c-1e49-4477-9455-e695fb8b050f](https://github.com/prithviraj5703/Metasploit-for-reconnaissance/assets/121418418/a84ed579-95dc-49d2-aba2-2fe2787d0ddd)

the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

### Output:

![244957531-78cf8911-1cfc-4b2e-96a1-319c70156555](https://github.com/prithviraj5703/Metasploit-for-reconnaissance/assets/121418418/17c9e654-4086-4a54-82e7-386599ede0d4)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

### OUTPUT:

![244957527-87dd0e6a-ba3a-4066-af83-fdb2daa0aae9](https://github.com/prithviraj5703/Metasploit-for-reconnaissance/assets/121418418/9766d190-c63e-4b46-8450-acefa0c4e66e)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

The info command provides information regarding a module or platform,

### Output:



![244957605-dc038257-ee12-4ee7-8477-c2a7192cab98](https://github.com/prithviraj5703/Metasploit-for-reconnaissance/assets/121418418/4730bf61-dd12-4af9-a4ab-d9a1f3826938)


Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init

### MYSQL ENUMERATION:

Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>


![244957531-78cf8911-1cfc-4b2e-96a1-319c70156555](https://github.com/prithviraj5703/Metasploit-for-reconnaissance/assets/121418418/7844f413-340f-40b1-814a-c82c02788cca)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql


![244957715-420e94f9-8eeb-44e9-9f06-925cb627eb66](https://github.com/prithviraj5703/Metasploit-for-reconnaissance/assets/121418418/35964dd2-0452-480f-89a8-2db2ba18d91c)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version


![244957783-521e3966-f0f2-4e28-b4a4-19133ddb8220](https://github.com/prithviraj5703/Metasploit-for-reconnaissance/assets/121418418/1fdb965f-938b-482b-84d3-9baa590751bb)

Use the set rhosts command to set the parameter and run the module, as follows:


![244957758-d129eec5-a1d3-4372-a95d-883e8add8c8e](https://github.com/prithviraj5703/Metasploit-for-reconnaissance/assets/121418418/549366c7-761f-49c8-a185-ba073ada09dc)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.


![244957645-27c829a5-e0e3-4488-a0a9-87156cff2ea7](https://github.com/prithviraj5703/Metasploit-for-reconnaissance/assets/121418418/c96d56e3-b1a3-46fe-adc6-d66616b846b7)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true


![244957684-fa4a5ed2-12c3-409b-9af3-ae5b8c543615](https://github.com/prithviraj5703/Metasploit-for-reconnaissance/assets/121418418/29b46f10-a776-43a7-8a9e-975f2e721842)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
