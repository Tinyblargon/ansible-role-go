# Ansible Role: go

Ansible role to install the [Go](https://golang.org) programming language.

## Requirements

n/a

## Role Variables

| Variable Name| Type  | Default Value| Description|
| :------------|:-----:| :-----------:| :----------|
| go_version:  | string| "1.24.1"     | Go version to download and install, when the version changes the old install will be removed and a new one will be created.|
| go_state:    | string| "present"    | When `"present"` Go will be installed, when `"absent"` Go will be removed. With `"present-reinstall"` the version check is ignored and go will be reinstalled on every run.|
| go_checksum: | string| ""           | Checksum of the downloaded archive, syntax `"sha256:cb2396..."`.|

## Dependencies

n/a

## Example Playbook

```yaml
- hosts: all
  roles:
    - role: tinyblargon.go
      vars:
        go_version: "1.24.1"
        go_checksum: sha256:cb2396bae64183cdccf81a9a6df0aea3bce9511fc21469fb89a0c00470088073
        go_state: present-reinstall
```

## License

MIT
