# Alerting

## Overview

This lab includes several Zabbix triggers to validate alerting workflows.

The goal was not only to collect metrics, but also to detect service failures and confirm that alerts move from PROBLEM to RESOLVED.

## DNS Alert Test

A custom item was created to monitor DNS TCP 53 on `SRV-AD01`.

The DNS trigger was tested by temporarily changing the monitored port to simulate a failure.

The alert workflow was validated:

1. Normal state: OK
2. Simulated failure: PROBLEM
3. Restored configuration: RESOLVED

## Veeam Repository Alert

A trigger was created to alert if the Veeam repository disk usage goes above 80%.

This helps detect backup storage capacity issues before the repository becomes full.

## Veeam Services Alerts

Triggers were created for critical Veeam services:

- Veeam Backup Service
- Veeam Broker Service
- Veeam Data Mover Service
- Veeam PVE Service

If one of these services stops running, Zabbix creates a High severity alert.

## OPNsense Alerts

The OPNsense SNMP template includes alerts for firewall availability, SNMP data collection, interface status and network performance.

This helps detect if the firewall is unreachable or if an interface goes down.
