# Network Analysis
# Time Thieves

- At least two users on the network have been wasting time on YouTube. Usually, IT wouldn't pay much mind to this behavior, but it seems these people have created their own      web server on the corporate network. So far, Security knows the following about these time thieves:
   -  They have set up an Active Directory network.
   -  They are constantly watching videos on YouTube.
   -  Their IP addresses are somewhere in the range 10.6.12.0/24.

- You must inspect your traffic capture to answer the following questions:

1. What is the domain name of the users' custom site?
    - Domain name: frank-n-ted.com
  
![](Images/Domain%20Name%20frank-n-ted.com%20%26%20IP%20adress%20of%20Domain.png)
  
    

2. What is the IP address of the Domain Controller (DC) of the AD network?
    - Ip address of the domain controller is: 10.6.12.12
 
![](Images/Domain%20Name%20frank-n-ted.com%20%26%20IP%20adress%20of%20Domain.png)

 
3. What is the name of the malware downloaded to the 10.6.12.203 machine?
    - Name of malware is: june.dll
     
![](Images/june11.dll%20(1).png)

![](Images/june11.dll%20(2).png)

- Once you have found the file, export it to your Kali machine's desktop.
          
 
4. Upload the file to VirusTotal.com. What kind of malware is this classified as?
    - The Malware is classified as a Trojan
   
![](Images/Malware%20Classified%20as%20Trojan.png)

 
# Vulnerable Windows Machines

- The Security team received reports of an infected Windows host on the network. They know the following:
  - Machines in the network live in the range 172.16.4.0/24.
  - The domain mind-hammer.net is associated with the infected computer.
  - The DC for this network lives at 172.16.4.4 and is named Mind-Hammer-DC.
  - The network has standard gateway and broadcast addresses.
  
- Inspect your traffic to answer the following questions:

1. Find the following information about the infected Windows machine:
   - Host name: Rotterdam-PC.mind-hammer.net
    ![](Images/Host%20Name%20Rotterdam.png)
   - IP address: 172.16.4.205
    ![](Images/Host%20IP%20Address.png)
   - MAC address: 00:59:07:b0:63:a4
    ![](Images/Host%20MAC%20Address.png)
  
   
2. What is the username of the Windows user whose computer is infected?
   - Username of infected computer is: matthijs.devries
  
![](Images/User%20Nmae%20of%20Infected%20computer.png)

3. What are the IP addresses used in the actual infection traffic?
   - ip address are: 166.62.11.64 and 185.243.115.84
   
![](Images/Infection%20IP%20Address.png)

 
4. As a bonus, retrieve the desktop background of the Windows host.

![](Images/Desktop%20windows%20HostBackround.png)

 
# Illegal Downloads

- IT was informed that some users are torrenting on the network. The Security team does not forbid the use of torrents for legitimate purposes, such as downloading operating systems. However, they have a strict policy against copyright infringement.
- IT shared the following about the torrent activity:
  - The machines using torrents live in the range 10.0.0.0/24 and are clients of an AD domain.
  - The DC of this domain lives at 10.0.0.2 and is named DogOfTheYear-DC.
  - The DC is associated with the domain dogoftheyear.net.
  
- Your task is to isolate torrent traffic and answer the following questions:

1. Find the following information about the machine with IP address 10.0.0.201:
   - MAC address: 00:16:17:18:66:c8
![](Images/MAC%20Address%2010.0.0.201.png)
   - Windows username: elmer.blanco
![](Images/Windows%20Username%20elmer.blanco.png)
    - OS version: Windows NT 10.0; win64; x64
![](Images/Windows%20OS%20version%20Windows%20NT%2010.0.png)


2. Which torrent file did the user download?

   - Torrent file: Betty_Boop_on_the _reservation.avi.torrent

![](Images/torrent%20file%20Betty_Boop_on_the%20_reservation.avi.torrent.png)

 
