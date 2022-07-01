almaops.s3cmd
==========

This ansible role installs [s3cmd](https://s3tools.org/s3cmd) with [pyhton pip](https://s3tools.org/s3cmd) and allow you to configure several accounts.

Requirements
------------

- role [almaops.pip_install](https://galaxy.ansible.com/almaops/pip_install)

Role Variables
--------------

Look into [./defaults/main.yml](./defaults/main.yml)

Example Playbook
----------------

```
- hosts:
    - servers
  become: true
  roles:
    - role: almaops.s3cmd
      vars:
        s3cmd_configs:
          - name: yandex
            access_key: "<...>"
            secret_key: "<...>"
            bucket_location: "ru-central1"
            host_base: "storage.yandexcloud.net"
            host_bucket: "%(bucket)s.storage.yandexcloud.net"
          - name: vkcs-hot
            access_key: "<...>"
            secret_key: "<...>"
            bucket_location: "ru-msk"
            host_base: "hb.bizmrg.com"
            host_bucket: "%(bucket).hb.bizmrg.com"
            website_endpoint: "http://hb.bizmrg.com"
```

License
-------

[MIT License](./LICENSE)


Author Information
------------------
Dmitrii Kashin, <freehck@freehck.com>
