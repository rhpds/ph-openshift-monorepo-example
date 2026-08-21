# create_namespace

Creates an OpenShift namespace for the monorepo lab

## Requirements

None.

## Role Variables

| Variable | Default | Description |
|----------|---------|-------------|
| ph_mono_create_namespace_name | ansible_test_monorepo | Name of the namespace to create |

## Dependencies

None.

## Example Playbook

```yaml
- hosts: all
  roles:
    - role: ph_openshift_monorepo_example.ansible.create_namespace
```

## License

GPL-2.0-or-later
