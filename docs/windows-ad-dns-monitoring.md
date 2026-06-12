# Windows AD and DNS Monitoring

## Overview

The Windows Server domain controller `SRV-AD01` was added to Zabbix using the Windows agent.

## Host Details

| Setting | Value |
|---|---|
| Host name | SRV-AD01 |
| IP address | 10.10.20.10 |
| Role | Active Directory Domain Controller and DNS |
| Agent port | 10050 |
| Template | Windows by Zabbix agent |

## Collected Metrics

Zabbix collects Windows metrics such as:

- CPU usage
- Memory usage
- Disk usage
- Network activity
- Windows service state
- System uptime

## DNS Monitoring

A custom simple check was created to validate DNS availability.

| Setting | Value |
|---|---|
| Item name | DNS TCP 53 availability |
| Target | 10.10.20.10 |
| Port | TCP 53 |
| Expected value | 1 |

A trigger was created to alert if DNS TCP 53 becomes unavailable.

The alert was tested by simulating a failure and validating the PROBLEM to RESOLVED workflow.
