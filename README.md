# Kolla-PreDeployment

The purpose of this repository is to provide a simple Ansible Playbook which helps to streamline the OpenStack Kolla installation process. While deploying Kolla, I ran into the need to deploy the following dependencies across all Kolla deploy targets in my infrastructure (Ubuntu 16.04):

  - Installing base packages such as Ansible, Kolla, and python
  - Creating alternative user accounts (if not using the default `kolla` user)
  - Cloning the kolla repository across all hosts in infrastructure into specific deploy directories (Helps to make kolla cleanup easier)
  - Testing simple things such as Internet connectivity and apt-repositories and reachability prior to running the `kolla-ansible deploy`

_NOTE:_ This does not attempt to replace the `kolla-ansible bootstrap` function, but intended to run prior to the bootstrap process.  This is simply some helpful hacks I ran across while deploying OpenStack Kolla.  Enjoy!

## How to Use:

Simply run this playbook against your infrastructure like you would any other playbook.  Be sure to supply `user` parameters in the playbook itself if you plan on creating user accounts prior to the kolla-deployment

`ansible-playbook kolla-predeployment.yml -i yourinventory.ini`
