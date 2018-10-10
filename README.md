# Ansible Role: Netrc

Configures encrypted `.netrc` file, encryption is via [gnupg2][gnupg2].

## Requirements

[gnupg2][gnupg2] must be installed on the system prior to running this role
(suggested role: `geerlingguy.homebrew`). A gpg key must exist (suggested role:
`lwalley.gpg`).

## Role Variables

Available variables with example values are listed below, for default values see
[`defaults/main.yml`](defaults/main.yml)):

    netrc_path: ~/.netrc
    netrc_gpg_recipient: "marvin@depressed-androids.io"
    netrc_config:
      - machine: "api.depressed-androids.io"
        config:
          - [ "login", "marvin" ]
          - [ "password", "muchsmarterthanamattress" ]

## Dependencies

None.

## Example Playbook

    - hosts: localhost
      roles:
         - { role: lwalley.netrc }

## License

MIT

[gnupg2]: https://gnupg.org
