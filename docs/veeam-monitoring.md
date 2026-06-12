# Veeam Monitoring

## Overview

The Veeam Backup & Replication server `veeam-backup01` was added to Zabbix using the Windows agent.

The goal was to monitor the backup server itself, the backup repository disk and critical Veeam services.

## Host Details

| Setting | Value |
|---|---|
| Host name | veeam-backup01 |
| IP address | 10.10.20.70 |
| Role | Veeam Backup & Replication server |
| Agent port | 10050 |
| Template | Windows by Zabbix agent |

## Repository Monitoring

The Veeam repository disk was detected by Zabbix as drive `R:`.

| Setting | Value |
|---|---|
| Repository drive | R: |
| File system | ReFS |
| Repository path | R:\\VeeamRepository |
| Total size | 199.9 GB |
| Monitored metric | Space used in % |

A trigger was created to alert when the repository disk usage goes above 80%.

## Veeam Service Monitoring

Critical Veeam services were monitored through Windows service discovery.

Monitored services include:

- Veeam Backup Service
- Veeam Broker Service
- Veeam Data Mover Service
- Veeam PVE Service

Triggers were created to alert if any of these services are not running.
