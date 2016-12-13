# GIMP dependencies role

In Debian, this ansible role will:

1. Convert Debian Jessie to Debian Testing by modifying `/etc/apt/sources.list`
2. Perform an `apt-get dist-upgrade` to upgrade the OS to Debian Testing.
3. Install prerequisite packages for building GIMP.

# Requirements

Debian Jessie or Debian Stretch/Testing

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

### License

* [Apache License 2.0](LICENSE)

# Author Information

Created by Sam Gleske.
