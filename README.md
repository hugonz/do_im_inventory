Role Name
=========

This role calls up the API for Digital Ocean v2 and brings all the droplets along with their tags. Optionally, the role allows for filtering the returned inventory by tags.

This role came from the lack of a digital_ocean_droplet_facts module in mainline Ansible.

Requirements
------------

Role Variables
--------------
gdoi_token: the DO API token, you should create one for your user n digitalocean.com. If not passed, the DO_TOKEN environment variable will be used.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
