# CI: Get free tcp port

This role is useful for getting free tcp port on remote host.

## Role Variables

- `ci_get_free_port__var` (default: ci_get_free_port): This variable contains name of variable to which the free port will be written.
- `ci_get_free_port__pool` (default: 1024-32767): Range of ports between which a free port will be found.
- `ci_get_free_port__host` (default: 127.0.0.1): IP address where free port will be checked.
- `ci_get_free_port__default` (default: ""): Value that will be written to variable if no free port is found among range.

## Requirements

`nmap` (`nc`) utility must be installed on the remote host.

## Example Playbook

```yaml
- hosts: all
  become: yes
  become_method: sudo
  vars:
    ci_get_free_port__var: project_port
  roles:
  - role: levonet.ci-get-free-port
  tasks:
  - debug:
      msg: "Port: {{ project_port }}"
```

## License

[MIT](https://opensource.org/licenses/MIT)

## Author Information

This role was created by [Pavlo Bashynskyi](https://github.com/levonet)
