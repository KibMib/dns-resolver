# DNS Resolver on VM

A DNS resolver built with BIND9 on a virtual machine (Ubuntu Server) for LAN.

## Features
- Caching DNS resolver using BIND9.
- Custom local domain (`mylan.local`) with sample records.
- Restricted to LAN queries for security.

## Setup Instructions
1. Create a VM with Ubuntu Server in VirtualBox.
2. Set a static IP (e.g., `192.168.0.110`).
3. Install BIND9: `sudo apt install bind9 bind9utils dnsutils`.
4. Configure BIND9 (see `configs/`).
5. Test with: `dig @192.168.0.110 google.com` or `dig @192.168.0.110 www.mylan.local`.

## Files
- `configs/01-netcfg.yaml`: netplan config for statis IP
- `configs/named.conf.options`: BIND9 main config.
- `configs/named.conf.local`: Local zone config.
- `configs/db.mylan.local`: Zone file for `mylan.local`.

## Usage
Set LAN devices DNS to the VM’s IP (e.g., `192.168.0.110`).
Or, set LAN WiFi Router or APs DNS to VM's IP, so it will get shared with DHCP.
