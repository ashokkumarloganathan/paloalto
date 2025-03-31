# Paloalto Firewalls

## Types

### Hardware

![Palo Alto Firewalls](https://private-user-images.githubusercontent.com/146918896/415894996-6bb37971-8113-4aeb-9eee-b28e9304f8cd.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDM0MTUzNTksIm5iZiI6MTc0MzQxNTA1OSwicGF0aCI6Ii8xNDY5MTg4OTYvNDE1ODk0OTk2LTZiYjM3OTcxLTgxMTMtNGFlYi05ZWVlLWIyOGU5MzA0ZjhjZC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwMzMxJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDMzMVQwOTU3MzlaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0yNzFmODRmODg0Yjc5NWE3MTYyN2NkYjA3YjkxYTU1NDJlODU2MmFlYzgxMzgxMjc4NzEyNmU5MjIxZTQxOTk2JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.iOEZ12xU8fDTST_3ELEfIr1Aja2a50NJIeTp5G8rK3M)

### Software:- 

Supports KVM, VMWare esxi, All Major Cloud Platforms and Containers.

# Accessing Paloalto Firewalls
## Management Access through

1. GUI
2. CLI
3. Console
4. REST API

### Default IP Address:-

#### All Hardware Models :-

IP Address - 192.168.1.1/24 with DHCP Server enabled - Just plug in the system which will receive the IP. then we can access the paloalto GUI or CLI.

#### VM Firewalls:-

By default it will be configured as DHCP Client on the management port, this can be changed through Console using the following commands.

```
configure

set deviceconfig system type static

set deviceconfig system ip-address 192.168.1.1 netmask 255.255.255.0

commit
```

Configure Network Interface Ethernet1/1 through console to assign ip address and enable management access.
```

configure

set network profiles interface-management-profile Management-Access allow-ssh yes

set network profiles interface-management-profile Management-Access allow-https yes

set network interface ethernet ethernet1/1 layer3 ip 10.0.0.1/24

set network interface ethernet ethernet1/1 layer3 interface-management-profile Management-Access

commit
```

Navigate to Next Page[https://github.com/ashokkumarloganathan/paloalto/page2.md]