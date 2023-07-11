# Ansible Role: lodestar

### Description
Ansible role that will install, configure and runs [Lodestar](https://chainsafe.github.io/lodestar/install/docker/):

### Table of Contents
  - [Supported Platforms](#supported-platforms)
  - [Dependencies](#dependencies)
  - [Role Variables](#role-variables)
  - [Example Playbook](#example-playbook)
  - [License](#license)
  - [Author Information](#author-information)

### Supported Platforms
```
* MacOS
* Debian
* Ubuntu
* Redhat(CentOS/Fedora)
* Amazon
```

### Dependencies

* Docker 

### Role Variables:

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file. By and large these variables are configuration options. Please refer to the Lodestar [docs](https://chainsafe.github.io/lodestar/usage/beacon-management/) for more information

| Name                           | Default Value                      |  Description                                                                                                        |
|--------------------------------|------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| `lodestar_version`             | ___unset___                        | __REQUIRED__ Version of lodestar to install and run.                                                                |
| `lodestar_user`                | lodestar                           | lodestar user                                                                                                       |
| `lodestar_group`               | lodestar                           | lodestar group                                                                                                      |
| `lodestar_base_dir`            | /opt/lodestar                      | Path to install to                                                                                                  |
| `lodestar_config_dir`          | /etc/lodestar                      | Path for default configuration                                                                                      |
| `lodestar_data_dir`            | /opt/lodestar/data                 | Path for data directory                                                                                             |
| `lodestar_log_dir`             | /var/log/lodestar                  | Path for logs directory                                                                                             |
| `lodestar_network`             | mainnet                            | Predefined network configuration                                                                                    |
| `lodestar_host_ip`             | ""                                 |                                                                                                                     |

### Keys/Secrets
Please note that you must put your own secrets and keys in the config directory that you are using ie `lodestar_config_dir`

### Example Playbook

1. Default setup:
Install the role from galaxy
```
ansible-galaxy install consensys.lodestar
```

Create a requirements.yml with the following:
Replace `x.y.z` below with the version you would like to use 
```
---
- hosts: localhost
  connection: local
  force_handlers: True

  roles:
  - role: consensys.lodestar
    vars:
      lodestar_version: x.y.z

```

Run with ansible-playbook:
```
ansible-playbook -v /path/to/requirements.yml
```


2. Install via github

```
ansible-galaxy install git+https://github.com/consensys/ansible-role-lodestar.git
```

Create a requirements.yml with the following:
Replace `x.y.z` below with the version you would like to use 
```
---
- hosts: localhost
  connection: local
  force_handlers: True

  roles:
  - role: ansible-role-lodestar
    vars:
      lodestar_version: x.y.z

```

Run with ansible-playbook:
```
ansible-playbook -v /path/to/requirements.yml
```


### License

Apache


### Author Information

Consensys, 2023
