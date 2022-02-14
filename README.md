# Ansible Role: networkconfig

Most basic network config on a host.

## Mandatory Role Variables

This role requires you to set the config files which should be deployed to the host and their content in an array of hashes:

```
networkconfig__configs:
  - filepath: "/etc/network/interfaces.d/enp1s0"
    content: |
      auto enp1s0
      allow-hotplug enp1s0
      iface enp1s0 inet manual
  - filepath: "/etc/network/interfaces.d/br0"
    content: |
      auto br0
      iface br0 inet static
          bridge_ports enp1s0
              address 192.168.122.144
              broadcast 192.168.122.255
              netmask 255.255.255.0
              gateway 192.168.122.1
  - filepath: "/etc/resolv.conf"
    content: |
      nameserver 9.9.9.9
```

## Optional Role Variables

None.