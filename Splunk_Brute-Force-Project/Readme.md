# Brute Force Attack Detection using Splunk

## Project Overview
This project demonstrates how to detect brute force login attacks using Splunk SIEM.

## Tools Used
- Splunk Enterprise
- Windows Logs
- SPL (Search Processing Language)

## Use Case
Detect multiple failed login attempts followed by a successful login.

## Splunk Query

index=main "Failed login"
| rex "from (?<ip>\d+\.\d+\.\d+\.\d+)"
| stats count by ip
| sort -count

## Detection Logic
If multiple failed login attempts occur within a short time, it indicates a possible brute force attack.



## Author
Jagdish Champia
SOC Analyst (Aspiring)v
