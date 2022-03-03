 # Blue Team: Summary of Operations
 
# Table of Contents

- Network Topology
- Description of Targets
- Monitoring the Targets
- Patterns of Traffic & Behavior
- Suggestions for Going Further

# Network Topology

The following machines were identified on the network:

- Host name: ML-REFVM-684427
  - Purpose: Host machine
  - OS: Window 10 Pro
  - IPv4: 192.168.1.1

- Host name: Capstone (Server1) 
   - Ubuntu 18.04.1
   - OS: Linux
   - Purpose: Testing Alerts
   - IPv4: 192.168.1.105

          
- Host name: ELK 
  - Ubuntu 18.04.4
  - Purpose: Log Capture
  - IPv4: 192.168.1.100
  - OS: Linux


- Host name: Kali (Attacker)      
  - OS: Kali Linux 
  - Purpose: Attacker 
  - IPv4: 192.168.1.90


- Host name: Target1
  - OS : Debian GNU/Linux 8
  - Purpose: Vuln WordPress:
  - IPv4: 192.168.1.110
  - Ports: 
  - 22/tcp     open   ssh
  - 80/tcp     open   http
  - 111/tcp    open   rpcbind
  - 139/tcp   open   netbios-ssn
  - 445/tcp   open   netbios-ssn

# Description of Targets

The target of this attack was: `192.168.1.110`

Target 1 is an Apache web server and has SSH enabled, so ports 80 and 22 are possible ports of entry for attackers. As such, the following alerts have been implemented:

# Monitoring the Targets

Traffic to these services should be carefully monitored. To this end, we have implemented the alerts below:

### Alert 1: Excessive HTTP Errors
  - Alert 1 is implemented as follows:
  - Metric: Packetbeat
  - Threshold: WHEN count() GROUPED OVER top 5 'http.response.status_code' IS ABOVE 400 FOR THE LAST 5 minutes
  - Vulnerability Mitigated: It mitigates a brute Force attack.
  - Reliability: This alert does not generate a lot of false positives, and the rate of reliability is medium or high. 
 
![](Images/Alert%201%20Rules.png)

![](Images/Kibana%20Alert%201.png)



### Alert 2: HTTP Request Size Monitor
  - Alert 2 is implemented as follows:
  - Metric: Packetbeat
  - Threshold: WHEN sum() of http.request.bytes OVER all documents IS ABOVE 3500 FOR THE LAST 1 minute
  - Vulnerability Mitigated: Code injection in HTTP,or DDOs attack
  - Reliability: This alert does not generate lots of false positives/false negatives. The rate of reliability for this alert is high. 

![](Images/Alert%202%20rules.png)

![](Images/Kibana%20Alert%202.png)



### Alert 3: CPU Usage Monitor
  - Alert 3 is implemented as follows:
  - Metric: Metricbeat
  - Threshold: WHEN max() OF system.process.cpu.total.pct OVER all documents IS ABOVE 0.5 FOR THE LAST 5 minutes
  - Vulnerability Mitigated:  DDOs 
  - Reliability: This alert does not generate lots of false positives/false negatives. The rate of reliability for this alert is high.
  
![](Images/Alert%203%20Rules.png)

![](Images/Kibana%20Alert%203.png)












