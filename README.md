joenyland.wireguard
===================

[![CI](https://github.com/JoeNyland/ansible-wireguard-role/actions/workflows/ci.yml/badge.svg)](https://github.com/JoeNyland/ansible-wireguard-role/actions/workflows/ci.yml)

Installs [WireGuard](https://www.wireguard.com/).

Requirements
------------

None.

Role Variables
--------------

### `wireguard_interface`

Defines the WireGuard interface configuration.

#### Example

```yaml
wireguard_interface:
  address:
  post_up:
    - wg set %i private-key /etc/wireguard/private.key # Recommended. This key is generated on install of the role.
  dns: # Optional
    - 1.1.1.1 # DNS server 1
    - 2.2.2.2 # DNS server 2
    - vpn # Search domain
```

### `wireguard_peers`

Defines the WireGuard peers to connect with.

#### Example

```yaml
wireguard_peers:
  - name: # Optional
    public_key:
    allowed_ips:
    endpoint:  # Optional
    keep_alive: # Optional
```

### `wireguard_service_enabled`

Should WireGuard start at boot?

### `wireguard_service_state`

What state should WireGuard be in? e.g. started/stopped

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
