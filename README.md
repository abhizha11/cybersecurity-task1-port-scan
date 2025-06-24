🛡️ Cybersecurity Internship – Task 1: Port Scan and Network Analysis

This task involved scanning the local network using Nmap, analyzing network traffic using Wireshark, and identifying security risks from exposed ports.

🔧 Tools Used

- Nmap – Network scanner
- Wireshark – Packet analyzer (optional)
- Command Prompt / Terminal – To execute network commands
- Browser – For researching ports and services
- Text Editor – For documentation

🚀 Steps Performed

1. Installed Nmap from https://nmap.org/
2. Identified local IP range using ipconfig
3. Ran TCP SYN scan using:

   nmap -sS 192.168.1.0/24
_________________________________________________

4. Saved scan results with:

   nmap -sS 192.168.1.0/24 -oN scan_results.txt
_________________________________________________

5. Analyzed traffic with Wireshark using filters:
   - SYN packets: tcp.flags.syn == 1 && tcp.flags.ack == 0
   - SYN-ACK: tcp.flags.syn == 1 && tcp.flags.ack == 1

📊 Port Findings & Risks

| Port | Service         | Risk                                              | Mitigation                                  |
|------|------------------|---------------------------------------------------|---------------------------------------------|
| 80   | HTTP            | MITM, sniffing                                    | Use HTTPS                                   |
| 443  | HTTPS           | TLS config issues                                 | Strong TLS settings                         |
| 5431 | park-agent      | UPnP exposure                                     | Disable UPnP                                |
| 135  | MSRPC           | RPC exploits                                      | Restrict access, patch OS                   |
| 139  | NetBIOS-SSN     | Legacy exposure                                   | Disable if unnecessary                      |
| 445  | Microsoft-DS    | SMB exploits like WannaCry                        | Block externally, use firewall              |
| 902  | iss-realsecure  | VMware or intrusion system control channel        | Restrict by IP, disable if unused           |
| 912  | apex-mesh       | Unknown IoT risk                                  | Investigate and restrict or close           |
| 3306 | MySQL           | Database attacks                                  | Bind to localhost, use strong credentials   |
| 5357 | WSDAPI          | Device info exposure                              | Disable if not needed                       |

📝 Author
Name: Sagar  Jha
Internship Task: Cybersecurity – Task 1
Date: 24/03/2025

