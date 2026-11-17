# Sysmon Investigation — SOC Analyst Portfolio

## Project Overview

This project demonstrates practical Windows endpoint monitoring and threat investigation using Sysmon (System Monitor) telemetry.

The investigations were performed in a controlled TryHackMe lab environment. The objective was to analyze endpoint telemetry, identify suspicious behavior, investigate process execution, examine network connections, and recognize potential persistence techniques.

## Investigation Objectives

- Analyze process creation and execution chains.
- Investigate suspicious PowerShell activity.
- Identify USB device activity.
- Examine raw disk access events.
- Analyze network connections and potential Command and Control (C2) communication.
- Investigate registry modifications.
- Identify potential persistence mechanisms.

## Tools and Technologies

- Windows Event Viewer
- Sysmon
- Windows PowerShell
- TryHackMe AttackBox
- Windows Event Logs

## Key Investigations

### 1. USB Device and Raw Disk Access

**Events analyzed:** Event ID 13 and Event ID 9.

- Identified a SanDisk U3 Cruzer Micro USB device through registry information.
- Examined RawAccessRead activity involving the USB storage device.

### 2. Process Execution Analysis

**Event analyzed:** Event ID 1 — Process Creation.

- Investigated `rundll32.exe` execution.
- Examined a suspicious `mshta.exe` execution involving an HTA file.
- Reviewed process command lines and parent-process information.

### 3. Network Connection Analysis

**Event analyzed:** Event ID 3 — Network Connection.

- Identified network activity associated with suspicious processes.
- Examined source and destination IP addresses.
- Investigated a connection to `10.0.2.18` on port `4443`.
- Identified the destination `172.30.1.253`, hostname `empirec2`, on port `80` in another investigation.

### 4. Registry and PowerShell Investigation

**Event analyzed:** Event ID 13 — Registry Value Set.

- Examined a suspicious registry modification.
- Identified a PowerShell execution command stored in registry-related data.
- Investigated encoded PowerShell activity.

### 5. Persistence and Alternate Data Stream Investigation

- Examined a PowerShell command referencing `C:\Users\q\AppData:blah.txt`.
- Investigated suspicious scheduled-task activity.
- Reviewed the relationship between the command execution and the potential persistence mechanism.

## SOC Analyst Skills Demonstrated

- Windows endpoint monitoring
- Sysmon event analysis
- Process execution investigation
- Network connection analysis
- PowerShell investigation
- Registry analysis
- Detection of suspicious activity
- Basic incident investigation and documentation

## Evidence

Screenshots documenting the investigations are available in the `Evidence/` directory.

## Lab Environment

This project was completed in a controlled educational environment using TryHackMe.

The findings represent simulated investigation scenarios and should not be interpreted as evidence of a real-world compromise.

## References

- Microsoft Sysinternals — Sysmon
- Microsoft Learn — Understanding Sysmon Events
- TryHackMe — Sysmon Room


