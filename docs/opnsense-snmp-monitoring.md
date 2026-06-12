# OPNsense SNMP Monitoring

## Overview

OPNsense was added to Zabbix using SNMP.

SNMP was used because it is a standard monitoring protocol for network devices such as firewalls, routers, switches and printers.

## OPNsense Details

| Setting | Value |
|---|---|
| Host name | opnsense-lab |
| IP address | 10.10.20.1 |
| Monitoring method | SNMP |
| SNMP version | v2c |
| SNMP port | UDP 161 |
| SNMP community | zbx_homelab_ro |
| Template | Network Generic Device by SNMP |

## Collected Metrics

Zabbix collects firewall and network metrics such as:

- ICMP availability
- ICMP response time
- Packet loss
- SNMP availability
- System name
- System uptime
- Interface status
- Interface traffic
- Interface errors

## Alerting

The SNMP template provides useful triggers, including:

- Unavailable by ICMP ping
- No SNMP data collection
- High ICMP ping loss
- High ICMP response time
- Interface link down
- High bandwidth usage
- High interface error rate

This makes OPNsense visible in Zabbix and helps detect firewall or network issues faster.
