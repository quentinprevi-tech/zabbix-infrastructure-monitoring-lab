# Zabbix Infrastructure Monitoring Lab

## Overview

This project documents a Zabbix infrastructure monitoring lab built on Proxmox VE.

The goal of this lab was to deploy a central monitoring server and supervise multiple parts of a segmented homelab infrastructure, including Linux servers, Windows servers, Veeam Backup & Replication, DNS services, HTTP checks and an OPNsense firewall through SNMP.

## Lab Objectives

The main objectives were to:

- Install and configure Zabbix Server.
- Monitor a Linux web server using Zabbix Agent 2.
- Monitor a Windows Server domain controller using Zabbix Agent.
- Monitor HTTP availability for an Nginx web server.
- Monitor DNS availability on the domain controller.
- Create and test Zabbix triggers.
- Monitor a Veeam Backup & Replication server.
- Monitor the Veeam backup repository disk usage.
- Monitor critical Veeam services.
- Monitor OPNsense using SNMP.
- Document the architecture, configuration and validation steps.

## Lab Environment

| Component | Role |
|---|---|
| Proxmox VE | Virtualization platform |
| OPNsense | Firewall and network segmentation |
| Zabbix Server 7.4 | Central monitoring platform |
| Debian 13 | Zabbix server operating system |
| PostgreSQL | Zabbix database |
| Apache / PHP | Zabbix web frontend |
| Debian / Nginx | Linux web server monitored by Zabbix |
| Windows Server AD | Domain controller and DNS server |
| Veeam Backup Server | Backup infrastructure server |
| SNMP | Firewall monitoring protocol |

## Network Layout

| System | IP Address | Network |
|---|---:|---|
| Zabbix Server | 10.10.20.80 | SERVERS |
| SRV-AD01 | 10.10.20.10 | SERVERS |
| Veeam Backup Server | 10.10.20.70 | SERVERS |
| Debian DMZ Web Server | 10.10.30.10 | DMZ |
| OPNsense Firewall | 10.10.20.1 | SERVERS gateway |

## Monitored Hosts

| Host | Monitoring Method | Purpose |
|---|---|---|
| zabbix-monitor01 | Local Zabbix Agent 2 | Monitor the Zabbix server itself |
| debian-dmz-web01 | Zabbix Agent 2 | Linux metrics and Nginx server |
| SRV-AD01 | Zabbix Agent for Windows | Windows Server and DNS monitoring |
| veeam-backup01 | Zabbix Agent for Windows | Backup server and repository monitoring |
| opnsense-lab | SNMP | Firewall and network interface monitoring |

## Monitoring Scope

This lab validates several monitoring scenarios:

- Linux host monitoring
- Windows Server monitoring
- HTTP service monitoring
- DNS service monitoring
- Veeam repository monitoring
- Critical Windows service monitoring
- OPNsense firewall monitoring through SNMP
- Trigger creation and alert validation

## Final Result

This lab validates a complete infrastructure monitoring setup using Zabbix.

The monitoring covers Linux, Windows Server, DNS, HTTP, Veeam Backup & Replication and OPNsense firewall metrics.

The project demonstrates how a system and network administrator can use Zabbix to monitor infrastructure health, detect service outages and validate alerting workflows.


## Screenshots

### Linux host metrics from debian-dmz-web01

![Linux latest data](screenshots/01-zabbix-web01-latest-data.png)

### Nginx HTTP check with response code 200

![HTTP check](screenshots/02-zabbix-web01-http-check.png)

### SRV-AD01 Windows agent availability

![SRV-AD01 agent](screenshots/03-zabbix-srv-ad01-agent-green.png)

### SRV-AD01 DNS TCP 53 check

![DNS check](screenshots/04-zabbix-srv-ad01-dns-check.png)

### DNS trigger configured

![DNS trigger](screenshots/05-zabbix-srv-ad01-dns-trigger-ok.png)

### DNS alert in PROBLEM state

![DNS alert problem](screenshots/06-zabbix-srv-ad01-dns-alert-problem.png)

### DNS alert resolved

![DNS alert resolved](screenshots/07-zabbix-srv-ad01-dns-alert-resolved.png)

### Veeam repository disk monitoring

![Veeam repository disk](screenshots/08-zabbix-veeam-repository-disk-monitoring.png)

### Veeam repository usage trigger

![Veeam repository trigger](screenshots/09-zabbix-veeam-repository-trigger-ok.png)

### Veeam services monitoring

![Veeam services](screenshots/10-zabbix-veeam-services-monitoring.png)

### Veeam services triggers

![Veeam service triggers](screenshots/11-zabbix-veeam-services-triggers-ok.png)

### OPNsense SNMP monitoring

![OPNsense SNMP](screenshots/12-zabbix-opnsense-snmp-latest-data.png)

