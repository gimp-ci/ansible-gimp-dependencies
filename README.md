# DEPRECATED

This project has been migrated to [GNOME GitLab under World/gimp-ci](https://gitlab.gnome.org/World/gimp-ci).  Refer to [the documentation repository for better information](https://gitlab.gnome.org/World/gimp-ci/documentation).  If you just want to build GIMP, then [check out the GIMP development environment based on Docker](https://gitlab.gnome.org/World/gimp-ci/docker-gimp).  The Docker environment also allows you to run GIMP if you have Xorg display; instructions therein.

# GIMP dependencies role

In Debian, this ansible role will:

1. Convert Debian Jessie to Debian Testing by modifying `/etc/apt/sources.list`
2. Perform an `apt-get dist-upgrade` to upgrade the OS to Debian Testing.
3. Install prerequisite packages for building GIMP.

# Requirements

* Debian Jessie or Debian Stretch/Testing (WARNING: this will convert Debian
  Jessie to Debian Testing)
* Python 2.7 - https://www.python.org/ - scripting language used by Ansible and
  Molecule.
* Vagrant - https://www.vagrantup.com/ - VirtualBox provisioning layer.
* VirtualBox - https://www.virtualbox.org/ - Virtualization software.
* Virtualenv - https://virtualenv.pypa.io/ - user-managed python environment
  which simplifies development.

This role was last tested on Ubuntu 16.04.1 LTS with the following versions:

    Python 2.7.12
    Vagrant 1.8.6
    VirtualBox 5.0.24_Ubuntur108355
    Virtualenv 15.0.1

# Role Variables

No configurable role variables.  See [`vars/main.yml`](vars/main.yml) for a list
of static variables.

# Dependencies

No additional Ansible dependencies.

# Example Playbook

Usage in a playbook includes:

    - hosts: servers
      roles:
         - ansible-gimp-dependencies

# Getting Started

To start testing out this role:

```
git clone https://github.com/gimp-ci/ansible-gimp-dependencies.git
cd ansible-gimp-dependencies
virtualenv --python=$(type -p python2.7) .venv
source .venv/bin/activate
pip install -U pip
pip install -r test-reqs.txt
#now ready for development or running
molecule create
molecule converge
```

`molecule create` will create a VM based on Debian Jessie.  `molecule converge`
will execute this ansible role to perform all of the tasks defined in
[`tasks/main.yml`](tasks/main.yml).

### License

* [Apache License 2.0](LICENSE)

# Author Information

Created by Sam Gleske.
