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

In this task we used the IP tables on the firewall to prevent it from forwarding any traffic to the server unless it is SSH or HTTP traffic. 

After place the rules needed to verify that SSH and HTTP were being allowed while also disallowing other traffic such as telnet.

SSH proof

![image](https://github.com/user-attachments/assets/a521fd11-bfa8-482f-9fd8-4c85f89459fa)

![image](https://github.com/user-attachments/assets/db7d420d-33da-4821-bbb3-0d2629d46ee4)

I knew that SSH was working because on the client, after running the “ssh server’ command, I was prompted to input a password. I could also see that the client and the server initiated a three way handshake as shown in the screen shot. The server and client also exchanged a key via the diffie-hellman protocol which showed that encryption had started which is used by SSH.

HTTP proof

![image](https://github.com/user-attachments/assets/095826f0-0b2b-4369-97da-a53cda751de3)

![image](https://github.com/user-attachments/assets/06cacea6-2533-44d6-b676-d0c3d7304dc9)

I knew that HTTP was working because on the client, after I ran the wget server command, I was given a message that stated connected. Additionally, I was given the index.html.3 file. When looking at Wireshark, I could see that a three way handshake was completed, further proving that HTTP traffic was allowed to pass the firewall. 

Telnet Proof

![image](https://github.com/user-attachments/assets/a0410418-d949-419d-9cfd-8a100099f088)

![image](https://github.com/user-attachments/assets/feea8b87-ae4d-43e9-9e6d-687fd0ceee1a)

When running the “telnet server” command, the console did not change from “Trying 172.25.0.3". This proves that telnet is not connecting. Additionally when looking at the Wireshark capture, we can see that a TCP handshake was never completed. 

Finally I ran an NMAP scan on the client for open ports on the server.

![image](https://github.com/user-attachments/assets/88f7bdd4-06db-4f18-a29c-1d34dc366d09)

## Task 4: Open a new service port

In task four the client computer needed the wizbang program to be allowed to send traffic to the server.

When running ./wizbang I needed to see what port it attempted to connect to (port 10021). Next I needed to alter the iptables to allow the service. 

wizbang on client

![image](https://github.com/user-attachments/assets/09561c0c-f5ed-4e75-83d7-162bfbb3f452)

wizbang file capture via wireshark

![image](https://github.com/user-attachments/assets/1329364a-0bd3-4590-901c-59b7559af902)

I knew that wizbang was allowed to pass traffic because on the client console, when I ran the “./wizbang Good Morning” it ran the command and then presented me with “bye”. Before I created the rule, this did not happen. Additionally, when looking at the Wireshark scans, I could see that a TCP handshake was created on port 10021, which is what wizbang uses. 

Finally I performed an NMAP scan for what ports were open on the server. As you can see below, port 10021 is open. 

![image](https://github.com/user-attachments/assets/1f56a9af-00db-483e-a596-a927c66555c6)

## Tools/Software 
wizbang

wireshark

nmap

kali

iptables 
