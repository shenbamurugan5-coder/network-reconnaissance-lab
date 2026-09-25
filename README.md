Network Reconnaissance Lab

Project Overview :
  A hands-on cybersecurity lab focused on network reconnaissance using Nmap against an authorized OWASP Juice Shop Docker target. The project demonstrates host discovery, port scanning, service detection, HTTP enumeration, and analysis of exposed network services.

Objective :
1. Discover an active target host
2. Identify open TCP ports
3. Detect running services
4. Analyze HTTP responses
5. Perform detailed Nmap reconnaissance
6. Document the scan results

Lab Environment :
Component                      	Details

Operating System	              Kali Linux
Architecture	                  ARM64 / aarch64
Target	                        OWASP Juice Shop
Target Environment	            Docker
Reconnaissance Tool	            Nmap 7.99
Network	                        Docker bridge network

Methodology :

Target Setup
     ↓
Host Discovery
     ↓
Port Scanning
     ↓
Service Detection
     ↓
HTTP Enumeration
     ↓
Detailed Nmap Scan
     ↓
Full TCP Port Scan
     ↓
Result Analysis

1. Host Discovery 

Command: nmap -sn 172.17.0.2
The scan confirmed that the target host was active.
Screenshot: 01-host-discovery.png

2. Service Detection

Command: nmap -sV 172.17.0.2
The scan identified an open service on TCP port 3000 and detected the OWASP Juice Shop application.
Screenshot: 02-service-detection.png

3. HTTP Service Enumeration

Command: nmap -p 3000 --script http-title 172.17.0.2
This was used to gather information about the HTTP service running on port 3000.
Screenshot: 03-http-service.png

4. Web Response Analysis

Command: curl http://172.17.0.2:3000
The target returned an HTML response, confirming that a web application was accessible through the HTTP service.
Screenshot: 04-web-response.png

5. Detailed Nmap Scan

Command: sudo nmap -A -p 3000 172.17.0.2
The scan provided additional information about the running service and HTTP response.
Screenshot: 05-detailed-nmap-scan.png

6. Scan Result Documentation

Command: nmap -sV -p 3000 172.17.0.2 -oN scan-results.txt
The Nmap output was saved as a text file for documentation and future reference.
Screenshot: 06-final-scan-result.png

7. Full TCP Port Scan

Command: nmap -p- 172.17.0.2
The scan checked all TCP ports.

Findings :

Item	                  Result
Target IP	              172.17.0.2
Host Status	            Up
Open Port	              3000/tcp
Application	            OWASP Juice Shop
HTTP Status	            200 OK
Other TCP Ports	        65,534 closed

Screenshot: 07-full-port-scan.png

Tools & Technologies :

1. Nmap
2. Kali Linux
3. Docker
4. OWASP Juice Shop
5. Linux
6. TCP/IP
7. Network Security

Project Evidence :
  The screenshots/ directory contains the practical evidence collected during the reconnaissance process.
SCREENSHOTS/
├── 01-host-discovery.png
├── 02-service-detection.png
├── 03-http-service.png
├── 04-web-response.png
├── 05-detailed-nmap-scan.png
├── 06-final-scan-result.png
└── 07-full-port-scan.png

Conclusion :
  This lab provided practical experience with the network reconnaissance phase of security testing. It demonstrated how Nmap can be used to identify active hosts, discover exposed ports, detect services, and collect information about a web application in an authorized lab environment.
Note: All scanning activities in this project were performed against an intentionally configured local Docker lab environment.
