# Splunk-Deploying-a-Forwarder-and-Generating-Real-Time-Alerts

<h2>Description</h2>
In this SIEM task, I installed a Splunk forwarder onto my windows vm to send security and system logs to my splunk isntance. I then cleared the security logs to trigger a saved alert for event code 1102 and confirmed the alert was triggered in Splunk. 

<h2>Languages and Utilities Used</h2>

- <b>linux CLI</b>

<h2>Environments Used </h2>

- <b>Splunk</b>
- <b>Unbuntu</b> 

<br />
<br />
In Splunk, go to settings>forwarding and receiving. 

![1) settings forwarding and receiving](https://github.com/user-attachments/assets/02c388fa-3989-49ac-827b-7850de2162f1)

<br />
<br />
Enter the port for reciving logs, default 9997.

![2) inputing default listener tcp 9997](https://github.com/user-attachments/assets/f010a56b-9a72-4ac4-afc9-960a05ab924f)

<br />
<br />  
On my windows vm install the windows 64bit splunk forwarder.

![3) choosing windows 64 bit for my windows 10 vm](https://github.com/user-attachments/assets/0f055503-7f85-45be-b69a-b8a9bc771615)

<br />
<br />
Created an outbound and inboudn firewall rule to allow for tcp port 8089, and 9997 called Splunk Forwarder.

![4) new firwall outbound rule for tcp 8089 9997](https://github.com/user-attachments/assets/a0202142-2e1d-4f37-85bd-878b9d5a93af)

<br />
<br />
Running and installing the Splunk Forwarder setting default ports of 8089 and 9997. 

![5) set up forwarder using linux ip and 8089, 9997 ports](https://github.com/user-attachments/assets/b1100b90-bbe5-41f7-87c6-32ad7780a327)

<br />
<br />
Confirmed that the windows vm is connected with 2 sources, windows security and system logs. 

![6) connection established, system and security logs forwarding from windows](https://github.com/user-attachments/assets/c15dc0ab-3a90-4194-8c32-13bbabc080a8)

<br />
<br />  
Searching for all indexes with and event code of 4624 plls up 59 windows events. 

![7) searching for event code 4624 shows 59 logon events in the last 24 hrs](https://github.com/user-attachments/assets/0612035c-1531-4507-9272-d2657bba72b1)

<br />
<br />  
Searching for event code 1102 under windwos security logs and saving it as an alert will trigger an alert for cleared security logs. 

![8) creating an alert when windows host clears event logs](https://github.com/user-attachments/assets/7df04ac3-2e56-4f3c-84ae-083d4c1d39d3)

<br />
<br />
Clearing the windows vm security logs through the command line "wevtutil cl Security".

![9) clearing windows security logs to trigger alert](https://github.com/user-attachments/assets/e87cda65-ceb4-4fc2-81cb-9e6826f9956c)

<br />
<br />  
In Activity>triggered alerts> an alert was generated. 

![10) alert triggered](https://github.com/user-attachments/assets/93f3388a-26cf-4ee3-a11f-97edbfb5f9d6)

<br />
<br />  
