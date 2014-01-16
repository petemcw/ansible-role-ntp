# Network Time Protocol (NTP) Role for Ansible

This role installs the NTP package which is a protocol designed to synchronize the clocks of computers over a network.

## Requirements

This role requires [Ansible](http://www.ansibleworks.com/) version 1.4 or higher and the Debian/Ubuntu platform.

## Role Variables

The variables that can be passed to this role and a brief description about
them are as follows (additional variables are available in the source):

```yaml
# The list of default NTP time servers used for synchronization
ntp_servers:
  - '0.ubuntu.pool.ntp.org'
  - '1.ubuntu.pool.ntp.org'
  - '2.ubuntu.pool.ntp.org'
  - '3.ubuntu.pool.ntp.org'
```

## Examples

1. Install NTP with the defaults

    ```yaml
    ---
    # This playbook installs NTP

    - name: Apply NTP to all nodes
      hosts: all
      roles:
        - ntp
    ```

2. Install NTP with custom time servers

    ```yaml
    ---
    # This playbook installs NTP

    - name: Apply NTP to all nodes
      hosts: all
      roles:
        - { role: ntp,
            ntp_servers: [0.pool.ntp.org, 1.pool.ntp.org]
          }
    ```

## Dependencies

None.

## License

MIT.
