Systemd Customizer
=========

This role is to help to create a unit file to customize a service already installed

Installing
------------
```
ansible-galaxy install farchanjo.systemd_customizer
```

Role Variables
--------------

systemd_directory: '/etc/systemd/system'


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
- name: Testing Systemd Customizer
  hosts: all
  roles:
    - role: farchanjo.systemd.customizer
      service_name: mongod
      service_files:
         - name: Limits
           priority: 50
           params:
            - name: LimitFSIZE
              value: infinity
            - name: LimitCPU
              value: infinity
            - name: LimitAS
              value: infinity
            - name: LimitNOFILE
              value: infinity
         - name: Nice
           priority: 50
           params:
            - name: Nice
              value: 5
```

License
-------

MIT
