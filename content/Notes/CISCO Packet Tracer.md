---
created: 2025-07-21T14:08
updated: 2025-07-21T14:14
---
## Configuring Router with Switch

### Adding static IP

```bash
Router>en

Router#conf t

Enter configuration commands, one per line. End with CNTL/Z.

Router(config)#int f0/0

Router(config-if)#ip address 192.168.1.1 255.255.255.0

Router(config-if)#no shut
```

### Adding Dynamic IP

```bash
Router>en

Router#conf t

Enter configuration commands, one per line. End with CNTL/Z.

Router(config)#int f0/1

Router(config-if)#ip dhcp pool A

Router(dhcp-config)#network 192.168.2.0 255.255.255.0

Router(dhcp-config)#default 192.168.2.1

Router(dhcp-config)#no shut

```