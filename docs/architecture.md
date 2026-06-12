# Architecture

## Overview

This lab is built on Proxmox VE and uses Zabbix as a central monitoring platform.

The infrastructure is segmented with OPNsense into multiple networks, including LAN, SERVERS and DMZ.

Zabbix is deployed in the SERVERS network and monitors Linux servers, Windows servers, Veeam Backup & Replication and OPNsense.

## Network Layout

| System | IP Address | Role |
|---|---:|---|
| zabbix-monitor01 | 10.10.20.80 | Zabbix server |
| SRV-AD01 | 10.10.20.10 | Active Directory and DNS |
| veeam-backup01 | 10.10.20.70 | Veeam backup server |
| debian-dmz-web01 | 10.10.30.10 | Debian/Nginx web server |
| opnsense-lab | 10.10.20.1 | Firewall / SERVERS gateway |

## Monitoring Methods

| Target | Method |
|---|---|
| Linux servers | Zabbix Agent 2 |
| Windows servers | Zabbix Agent for Windows |
| HTTP services | Zabbix Web scenarios |
| DNS services | Zabbix simple checks |
| Veeam services | Windows service monitoring |
| OPNsense | SNMP |

## Final Design

The final design allows Zabbix to monitor both system-level metrics and service-level availability.

This makes it possible to detect if a server is online, if an important service is running and if network devices are reachable.
