# Network-Analysis---Ransomware-Lab

## Objective

The Detection Lab project aimed to establish a controlled environment for simulating and detecting cyber attacks. The primary focus was to ingest and analyze logs within Wireshark, Tshark and TCPdump, generating test telemetry to mimic real-world attack scenarios. This hands-on experience was designed to deepen understanding of network protocol analysis and attack patterns. The lab scenario was to decrypt a crucial document from a company that was targeted by ransomware, suspected to be orchestrated by a rival firm, resulting in the encryption of the final version of the tender document.

### Skills Learned

- Conducting deep packet analysis, gaining insights into network traffic behaviors and identifying anomalies that could indicate security breaches..
- Enhancing skills in network troubleshooting and monitoring without a graphical interface.
- proficiency in capturing and analyzing network packets from a terminal, honing their understanding of network protocols and traffic patterns for effective network diagnosis and security assessments.

### Tools Used

- Wireshark.
- Tshark.
- TCPDump.
- VirusTotal

## Steps 1
<img width="422" alt="Screenshot 2024-03-07 at 22 26 10" src="https://github.com/AlCybx/Network-Analysis---Ransomware-Lab/assets/161755166/bec7ed7d-bafa-4547-8db7-81982ddecb68">
<img width="719" alt="Screenshot 2024-03-07 at 22 27 10" src="https://github.com/AlCybx/Network-Analysis---Ransomware-Lab/assets/161755166/5138e6a2-0de2-4604-b514-e686069d37ee">
*Ref 1:Finding the operating system of the host from which the network traffic was captured*
To determine the operating system of the host from which the network traffic was captured, one must navigate to the menu bar, select "Statistics," and then choose "Capture File Properties." This allows easy access to the OS information, as demonstrated in the screenshots.

## Steps 2
<img width="452" alt="Screenshot 2024-03-08 at 15 44 42" src="https://github.com/AlCybx/Network-Analysis---Ransomware-Lab/assets/161755166/5bc2954b-a69c-4af5-a4f5-724ab5d8dc8f">
<img width="550" alt="Screenshot 2024-03-08 at 15 46 59" src="https://github.com/AlCybx/Network-Analysis---Ransomware-Lab/assets/161755166/f2a6db4a-1de4-4c9f-97aa-5991ed2d527e">
*Ref 2:Identifying the URL from which the ransomware executable was downloaded*
To pinpoint the URL from which the ransomware executable was downloaded, proceed to File > Export objects > HTTP objects, where you'll locate a packet containing an executable file named "safecrypt." By manually examining the packet, the full URL within the GET request can be obtained. Alternatively, selecting to follow the HTTP stream provides another method to retrieve this information.

## Steps 3
<img width="550" alt="Screenshot 2024-03-08 at 15 46 59" src="https://github.com/AlCybx/Network-Analysis---Ransomware-Lab/assets/161755166/17642492-2c1b-403c-860a-38ff1751f9d3">
*Ref 3:Identifying the name of ransomware executable file*
The name of the ransomware executable as highlighted in the screenshot is safecrypt.exe.

## Steps 4
<img width="722" alt="Screenshot 2024-03-08 at 16 12 56" src="https://github.com/AlCybx/Network-Analysis---Ransomware-Lab/assets/161755166/0343231b-ff4a-4870-a944-49562e660d12">
*Ref 4:Identifying the md5sum of ransomeware*
Within the Linux terminal, one can utilize a tool named md5sum, followed by the file name, to retrieve its hash.

## Steps 5
<img width="752" alt="Screenshot 2024-03-08 at 16 29 33" src="https://github.com/AlCybx/Network-Analysis---Ransomware-Lab/assets/161755166/748422f9-7480-4bc4-a0ea-b3961c11d54c">
*Ref 4:Finding the name of the ransomware*
To obtain the name, we can check whether this hash appears in malware databases. Utilizing services like Virustotal, we can search for the hash of the binary or manually upload it. Upon examination, we discover that numerous security vendors identify it as TeslaCrypt.

## Steps 6
<img width="739" alt="Screenshot 2024-03-08 at 16 40 21" src="https://github.com/AlCybx/Network-Analysis---Ransomware-Lab/assets/161755166/3738106f-43e9-40b0-aa1e-e0faae06b2b1">
*Ref 4:Identifying the encryption algorithm used by the ransomware, according to the ransom note*
The encryption algorithm used by the ransomware, according to the ransom note is RSA-4096.

## Steps 7
<img width="739" alt="Screenshot 2024-03-08 at 17 11 11" src="https://github.com/AlCybx/Network-Analysis---Ransomware-Lab/assets/161755166/c7b0565c-ba1b-47f5-afd1-5d823c17439f">
*Ref 4:Finding the domain beginning with ‘d’ that is related to ransomware traffic*
To locate the domain associated with ransomware traffic starting with 'd', I filtered DNS traffic and manually examined the DNS queries.

## Steps 8
<img width="275" alt="Screenshot 2024-03-08 at 18 57 24" src="https://github.com/AlCybx/Network-Analysis---Ransomware-Lab/assets/161755166/0c9d12bc-44e6-4eb3-92e0-fdcf2b403d4e">
*Ref 8:Decrypting the Tender document and submit the flag*
The encrypted document was successfully decrypted using McAfee by adhering to the decryption procedure specified for the identified Ransomware. The process of decrypting the file was relatively straightforward, and upon opening the document, we were able to retrieve the flag.




