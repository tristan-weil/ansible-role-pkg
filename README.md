# Ansible Role: pkg

An Ansible Role that installs a list of packages.

**NOTE**: packages already installed won't be upgraded if the version is not provided.

## Role Variables

Available variables are listed below, (see also `defaults/main.yml`).

Mandatory variables:

| Variable      | Description |
| :------------ | :---------- |

Optional variables:

| Variable      | Default | Description |
| :------------ | :------ | :---------- |
| pkg_list      | []      | a list of <*pkg*> or a list of packages names |

### <*pkg*> (Debian)

A *pkg* represents a package.

Mandatory variables:

| Variable      | Description |
| :------------ | :---------- |
| name          | the name of the package |

Optional variables:

| Variable      | Default | Description |
| :------------ | :------ | :---------- |
| allow_downgrades | False | *True / False * : allow the downgrade of packages |
| allow_upgrade | False | *True / False * : allow the upgrade of packages |
| default_release |       | the default release name |
| state         | present | *present / absent* : the installation state of the package |
| version       |         | the version of the package (upgrade forced) |

### <*pkg*> (OpenBSD)

A *pkg* represents a package.

Mandatory variables:

| Variable      | Description |
| :------------ | :---------- |
| name          | the name of the package |

Optional variables:

| Variable      | Default | Description |
| :------------ | :------ | :---------- |
| state         | present | *present / absent: the installation state of the package |

## Example Playbook

    - hosts: 'webservers'
      roles:
        - role: 'ansible-role-pkg'
          pkg_list:
            - lynx
            - alpine

## Todo

On OpenBSD, add a check on the lock and some retries.
