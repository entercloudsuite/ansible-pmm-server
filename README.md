Ansible Role: pmm-server 
======================================

[![Build Status](https://travis-ci.org/entercloudsuite/ansible-pmm-server.svg?branch=master)](https://travis-ci.org/entercloudsuite/ansible-pmm-server)
[![Galaxy](https://img.shields.io/badge/galaxy-entercloudsuite.pmm_server-blue.svg?style=flat-square)](https://galaxy.ansible.com/entercloudsuite/pmm_server)  

Installs pmm-server on Ubuntu 16.04 (Xenial)

## Requirements
This role requires Ansible 2.4 or higher.
### Pakage
 - pip
 - docker

## Role just testo for
chrissam.pmm-server

## Example Playbook

```yaml
- name: run the main role
  hosts: all
  roles:
  - role: entercloudsuite.pmm_server
    pmm_server_ENABLE_SSL: false
    pmm_client_PROTECTED: true
    pmm_server_version: 1.11.0
    pmm_server_username: pmm-administrator
    pmm_server_password: verys3cre3t
    pmm_client_http_port: 80
    pmm_client_https_port: 443
```
## Testing

## You nead pmm client


Tests are performed using [Molecule](http://molecule.readthedocs.org/en/latest/).

Install Molecule or use `docker-compose run --rm molecule` to run a local Docker container, based on the [enterclousuite/molecule](https://hub.docker.com/r/fminzoni/molecule/) project, from where you can use `molecule`.

1. Run `molecule create` to start the target Docker container on your local engine.  
2. Use `molecule login` to log in to the running container.  
3. Edit the role files.  
4. Add other required roles (external) in the molecule/default/requirements.yml file.  
5. Edit the molecule/default/playbook.yml.  
6. Define infra tests under the molecule/default/tests folder using the goos verifier.  
7. When ready, use `molecule converge` to run the Ansible Playbook and `molecule verify` to execute the test suite.  
Note that the converge process starts performing a syntax check of the role.  
Destroy the Docker container with the command `molecule destroy`.   

To run all the steps with just one command, run `molecule test`. 

In order to run the role targeting a VM, use the playbook_deploy.yml file for example with the following command: `ansible-playbook ansible-pmm-server/molecule/default/playbook_deploy.yml -i VM_IP_OR_FQDN, -u ubuntu --private-key private.pem`.  

## License

MIT
