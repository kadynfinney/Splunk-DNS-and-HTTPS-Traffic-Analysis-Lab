# Splunk-DNS-and-HTTPS-Traffic-Analysis-Lab
This home lab demonstrates how to use Splunk to analyze DNS and HTTPS traffic for security monitoring and threat detection. The goal is to understand how network activity is logged, searched, and investigated inside a SIEM environment.
# Splunk DNS and HTTPS Traffic Analysis Lab
[YouTube Demonstration](ADD-YOUR-YOUTUBE-LINK-HERE)

## Description
This home lab demonstrates how to use Splunk to analyze DNS and HTTPS traffic in a security monitoring environment. The goal of this lab is to understand how network activity is searched, filtered, and investigated inside a SIEM.

In this lab, a downloaded DNS dataset was imported into Splunk and used as sample log data for analysis. DNS traffic was reviewed to identify queried domains, repeated lookups, suspicious patterns, and unusual destinations. HTTPS traffic was reviewed to identify outbound connections, destination IPs, ports, and traffic patterns that could indicate suspicious activity.

This lab simulates the workflow of a SOC analyst reviewing network-based indicators of compromise, writing SPL searches, and identifying abnormal activity from log data.

## Lab Objectives
- Import sample DNS log data into Splunk
- Analyze DNS queries for repeated or suspicious domain lookups
- Review HTTPS traffic for unusual outbound connections
- Use SPL searches to filter and investigate network activity
- Identify possible indicators of compromise
- Build basic searches or dashboards to support analysis
- Practice SOC-style log analysis and investigation

## Tools and Utilities Used

### SIEM Platform
- Splunk Enterprise
- Splunk Search Processing Language
- Splunk dashboards and reports

### Log Data
- Downloaded DNS sample file
- DNS query logs
- HTTPS-related traffic fields included in the dataset

### Operating System
- Windows 10 or Windows Server
- Web browser
- File upload/import feature in Splunk

## Example SPL Searches

### View DNS Queries
```spl
index=* dns OR query
index=_* OR index=* sourcetype=dnslogs
index=_* OR index=* sourcetype=dnslogs | top domain, src_ip
index=_* OR index=* sourcetype=dnslogs | top limit=20 domain
index=_* OR index=* sourcetype=dnslogs | table src_ip, src_port dst_ip, dst_port
