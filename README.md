redis
=====

Install and manage Redis server. Currently the role installs Redis from source.

Tested on:
 - Ubuntu Server 14.04 LTS x64


Role Variables
--------------

By default you don't need to define any variables, the role will use defaults/main.yml


defaults/main.yml

`redis_install` (OPTIONAL)

```
redis_install:
 method: src
 directory: /opt
 download_url: http://download.redis.io/releases/redis-3.0.4.tar.gz
 src_file_sha256: a35e90ad581925134aa0fc92e969cc825f5cdee8e13c36a87d4d6995316112cf
```

Note: The role will use the URL to grab the version. The URL must end with redis-X.Y.Z.tar.gz


`redis_cfg` (OPTIONAL)

This is the full path to the configuration template file. If not provided the role will use
the default from the templates directory

Example (Recommended to define in group_vars or host_vars):

```
redis_cfg: /etc/ansible/group_files/my-group/redis/redis.conf.j2
```


License
-------

MIT


Author Information
------------------

Tal Lannder

tallannder@gmail.com
