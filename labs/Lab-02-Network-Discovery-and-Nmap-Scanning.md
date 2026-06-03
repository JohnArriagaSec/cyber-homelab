# Lab 02 - Network Discovery and Nmap Scanning

## Overview

In this lab, I explored network discovery and service enumeration using Nmap. My goal was to determine whether a Windows virtual machine was reachable from my Kali Linux virtual machine and identify any services running on it.

## Environment

* Kali Linux VM: 192.168.56.107
* Windows VM: 192.168.56.109
* VirtualBox Host-Only Network

## Initial Connectivity Test

I first attempted to ping the Windows VM from Kali:

```bash
ping 192.168.56.109
```

The result was 100% packet loss. Initially, I assumed the Windows machine might be offline or unreachable.

## Host Discovery

To verify whether the Windows system was actually offline, I used Nmap with the `-Pn` option, which treats the host as online and skips the ping discovery phase.

```bash
nmap -Pn 192.168.56.109
```

Nmap reported that the host was up, even though it did not respond to ICMP echo requests. Most scanned ports appeared filtered.

## Service Enumeration

Next, I performed a service and version scan:

```bash
nmap -Pn -sV 192.168.56.109
```

Results:

* Port 5357/tcp open
* Service: Microsoft HTTPAPI httpd 2.0
* Operating System: Windows

This confirmed that the Windows VM was reachable and running network services despite not responding to ping requests.

## Findings

* A host can be online even if it does not respond to ping.
* Nmap can identify hosts and services when ICMP is unavailable.
* Port 5357 was discovered running Microsoft HTTPAPI.
* Most ports were filtered, indicating that Windows was restricting network access to many services.

## Lessons Learned

One of the most important lessons from this lab is that a failed ping does not necessarily mean a host is offline.

Using Nmap allowed me to confirm that the Windows VM was active and identify a running service. This demonstrated the importance of using multiple methods for host discovery rather than relying solely on ICMP responses.

## Next Steps

* Install Wireshark and capture Nmap traffic
* Learn additional Nmap scan types
* Investigate Windows firewall behavior
* Add an Ubuntu VM and configure SSH
* Continue building my cybersecurity homelab
