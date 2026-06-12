# Linux Web Monitoring

## Overview

The Debian DMZ web server `debian-dmz-web01` was added to Zabbix using Zabbix Agent 2.

## Host Details

| Setting | Value |
|---|---|
| Host name | debian-dmz-web01 |
| IP address | 10.10.30.10 |
| Network | DMZ |
| Agent port | 10050 |
| Template | Linux by Zabbix agent |

## Collected Metrics

Zabbix collects Linux system metrics such as:

- CPU usage
- Memory usage
- Disk usage
- Filesystem usage
- Network traffic
- System uptime

## HTTP Check

A web scenario was created to validate that Nginx responds correctly.

| Setting | Value |
|---|---|
| Scenario name | web01 Nginx HTTP check |
| URL | http://10.10.30.10/ |
| Expected status code | 200 |
| Timeout | 15s |

The check confirmed that the Nginx web page returned HTTP 200 successfully.
