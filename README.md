# Brute Force Detection Lab

## Overview
This lab simulates an unauthorized brute force authentication attempt against a Windows system to evaluate logging visibility and host-based detection in a home SOC environment.

## Environment
- Hypervisor: VMware
- Attacker VM: Kali Linux
- Target VM: Windows
- Network Type: Host-Only

## Tools Used
- Zenmap (Nmap)
- Hydra
- Windows Event Viewer
- Wireshark

## Methodology

### Step 1: Security Configuration
- Create an inbound firewall rule allowing SMB (TCP 445)
- Verify open port using Zenmap
![Allow SMB 445](images/AllowSMB445.png)

## Step 2: Logging Configuration
- Configured Windows Event Viewer to log failed authentication attempts
- Verified logging with manual failed login attempts
- Event ID monitored: 4625 (Failed Logon)

## Step 3: Attack Simulation
- Captured traffic using Wireshark
- Launched a brute force attempt using Hydra against the SMB service

## Detection & Analysis
- No new Event ID 4625 logs were generated
- Wireshark traffic confirmed unsuccessful authentication attempts
- Attack failed due to logging and security configuration

## Incident Response Considerations
Recommended actions:
- Improve audit policies
- Implement account lockout rules
- Deploy centralized logging (SIEM)

## Skills Demonstrated
- Security monitoring
- Log analysis
- Attack simulation
- Windows security configuration
- Incident analysis

⚠️ IP addresses have been redacted.  
This lab was conducted in a controlled environment for educational purposes.
