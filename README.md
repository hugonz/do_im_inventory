do_im_inventory
=========

This role calls the v2 API for Digital Ocean and build an in-memory inventory for the user who owns the provided API key. I wrote this role to fix the lack of a digital_ocean_droplet_facts module in mainline Ansible.

Requirements
------------
This role uses the json_query Ansible filter, so the [jmespath](http://jmespath.org/) Python module must be installed in the controlling node.

Role Variables
--------------
`doim_token`: the DO API token, you should create one for your user in digitalocean.com. If not passed, the DO_API_TOKEN environment variable will be used.

Dependencies
------------
None.

Example Playbook
----------------

```yaml
- hosts: localhost
  environment:
    DO_API_TOKEN: <Digital Ocean API token string>

  roles:
    - role: do_im_inventory

  post_tasks:
    - name: Print the hosts added in the default group 
      debug: 
        msg: "{{ groups['digitalocean_droplets'] }}"

- hosts: digitalocean_droplets
  gather_facts: no

  tasks:
    - name: Print the facts from Digital Ocean present in the inventory
      debug: 
        msg: "{{ digitalocean_facts | }}"
```

License
-------

MIT

Author Information
------------------

Hugo F. Gonzalez  https://github.com/hugonz
