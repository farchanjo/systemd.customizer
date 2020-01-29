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

This a example how to use this role. You should have one service_files and at least one pair of params. Follow below:

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
