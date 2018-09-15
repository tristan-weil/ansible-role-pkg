# Ansible Role: pkg

An Ansible Role that installs a list of packages on Debian or OpenBSD.

**NOTE**: packages already installed won't be upgraded if the version is not provided.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    pkg_list: []                                    # the list of packages
    
The list of packages to install.
    
    pkg_Debian_apt_allow_downgrades: False          # True|False
    
For Debian, by default, downgrades are disallowed but it can be allowed with this variable set to `True`.

## Dependencies

None.

## Example Playbook

    - hosts: webservers
      roles:
        - role: Common/pkg
          pkg_list:
            - name: gimp

## Todo

None.

## License

```
Copyright (c) 2018 Tristan Weil <titou@lab.t18s.fr>

Permission to use, copy, modify, and distribute this software for any
purpose with or without fee is hereby granted, provided that the above
copyright notice and this permission notice appear in all copies.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES
WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF
MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR
ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN
ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF
OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
```
