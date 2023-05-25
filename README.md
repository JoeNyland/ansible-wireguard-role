joenyland.wireguard
===================

[![CI](https://github.com/JoeNyland/ansible-wireguard-role/actions/workflows/ci.yml/badge.svg)](https://github.com/JoeNyland/ansible-wireguard-role/actions/workflows/ci.yml)

Installs [WireGuard](https://www.wireguard.com/).

Requirements
------------

None.

Role Variables
--------------

### `wireguard_interfaces`

Defines the WireGuard interfaces to configure.

#### Example

```yaml
wireguard_interfaces:
  wg0:
    address:
    mtu:
    post_up:
      - wg set %i private-key /etc/wireguard/private.key # Recommended. This key is generated on install of the role.
    dns: # Optional
      - 1.1.1.1 # DNS server 1
      - 2.2.2.2 # DNS server 2
      - vpn # Search domain
    peers:
      - name: # Optional
        public_key:
        allowed_ips:
        endpoint:  # Optional
        keep_alive: # Optional
    enabled: true # Should this interface start at boot?
    state: started # What state should the interface be in?
```

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- hosts: server
  roles:
    - joenyland.wireguard
```

License
-------

MIT

Author Information
------------------

⌨️ with ❤️ by [Joe Nyland](https://joe.nyland.io)
