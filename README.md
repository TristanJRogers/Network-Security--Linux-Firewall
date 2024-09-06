# Network Security-Linux Firewall

In the project I was tasked with creating firewall rules on a firewall in Labtainer. 

## Task 1: Find IP Address

In this task I was to find the IP addresses of the client and the firewall. To do this i logged into both the client and the firewall and ran the command ifconfig

Client

![image](https://github.com/user-attachments/assets/8f4d9dc7-c68b-488f-b9e7-9ef6a02fbb70)


Firewall

![image](https://github.com/user-attachments/assets/39ee33a1-fb1b-4bf2-9546-673e8cc13825)

## Task 2: Nmap Scan

In task two we are told to use Wireshark to view network traffic through the firewall and to also debug the firewalls rules. 

One Wireshark was started I needed to get some traffic going through the firewall. I did this by doing an NMAP scan for open ports on a server. 

Next I used the wget command, ssh, and telnet while capturing the traffic from all three actions. 

NMAP Scan

![image](https://github.com/user-attachments/assets/83829c53-6fd2-4fde-8465-132f5cd6b3d3)

wget capture

![image](https://github.com/user-attachments/assets/684b0337-615b-442d-8bca-ef1849e4b982)

ssh capture

![image](https://github.com/user-attachments/assets/ee608667-b01d-48cd-884a-360cf43c6b64)

telnet capture

![image](https://github.com/user-attachments/assets/d984424f-c626-484a-94c4-1db65583bcb1)

## Task 3: Use iptables to limit traffic to the server

## Task 4: Open a new service port
