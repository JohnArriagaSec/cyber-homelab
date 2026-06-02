Lab 01 - Intial Homelab Setup

## Objective

setup my first cybersecurity homelab using virtual machines to learn networking, operating systems, and security concepts

# Lab Environment

# Host machine
  Windows PC
  16 Gb RAM

# Virtual Machines
  Kali Linux
  Windows

# Virtualization Software
  VirtualBox

Steps Completed

  1. installed Virtualbox
  2. Created a Kali Linux virtual machine
  3. Created a windows virtual machine
  4. Configured both Virtual machines to use a Host-Only network
  5. Verified IP Addresses on both systems

# Network Configuration

## Kali Linux
 Ip Address: 
 192.168.56.107

 Command used:
 ip a 

 # Windows

 IP Address:
 192.168.56.109

 Command Used:
 ipconfig

 # Connectivity Testing

# Windows to kali

## Command: 
ping 192.168.56.107

result: windows was able to communicate with kali

# Kali to windows:

## command:
ping 192.168.56.109

result: no result were recieved

output: 4 packets transmitted, 0 received, 100% packet loss

# troubleshooting performed:
  verified both systems were on the same subnet
  disabled Windows Firewall for testing.
  Confirmed both Vms were using a host-only adapter
  checked ip addressing on both systems

# Lessons learned

Virtual machines can be connected locally using a host only network
Network troubleshooting requires verifying ip addresses and connectivity 
communication may fail even when systems appear to be on the same network
cybersecurity involves understanding how systems communicate and diagnosing problems

# Next steps
  investigate why kali cannot reach windows
  learn how icmp and ping work
  install wireshark
  learn basic nmap scanning
  add an ubuntu vm to the lab

