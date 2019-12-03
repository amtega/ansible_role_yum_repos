# Ansible check_mk_agent role

This is an [Ansible](http://www.ansible.com) role to configue yum repositories whit priority plugin suport.

## Role Variables

A list of all the default variables for this role is available in `defaults/main.yml`.

## Usage

This is an example playbook:

```yaml
---

- hosts: all
  roles:
    - role: amtega.yum_repos
      vars:
        yum_repos_repofiles:
          - filename: my.repo
            repos:
              - name: my-rpms
                description: My rpms
                base_url: http://acme.com/myrepo                  
                enabled: yes
                gpgcheck: no
                priority: 10
              - name: my-rpms-optional
                description: My optional rpms
                base_url: http://acme.com/myrepo-optional
                enabled: yes
                gpgcheck: no
                priority: 10    
```

## Testing

Tests are based on docker containers. You can setup docker engine quickly using the playbook `files/setup.yml` available in the role [amtega.docker_engine](https://galaxy.ansible.com/amtega/docker_engine).

Once you have docker, you can run the tests with the following commands:

```shell
$ cd amtega.yum_repos/tests
$ ansible-playbook main.yml
```

## License

Copyright (C) 2019 AMTEGA - Xunta de Galicia

This role is free software: you can redistribute it and/or modify it under the terms of:

GNU General Public License version 3, or (at your option) any later version; or the European Union Public License, either Version 1.2 or – as soon they will be approved by the European Commission ­subsequent versions of the EUPL.

This role is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details or European Union Public License for more details.

## Author Information

- José Enrique Mourón Regueira
