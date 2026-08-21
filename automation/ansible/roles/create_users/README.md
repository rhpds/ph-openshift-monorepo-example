# create_users

Creates 4 OpenShift users (dev1–dev4) with a shared password

## Requirements

None.

## Role Variables

| Variable | Default | Description |
|----------|---------|-------------|
| create_users_users | [dev1, dev2, dev3, dev4] | List of usernames to create |
| create_users_password | rhdp@3456 | Shared password for all users |

## Dependencies

None.

## Example Playbook

```yaml
- hosts: all
  roles:
    - role: ph_openshift_monorepo_example.ansible.create_users
```

## License

GPL-2.0-or-later
