redis
=====

Install and manage Redis server. Currently the role installs Redis from source.

Tested on:
 - Ubuntu Server 14.04 LTS x64


Role Variables
--------------

By default you don't need to define any variables, the role will use defaults/main.yml


defaults/main.yml

```
---
redis_install:
 method: src
 directory: /opt
 download_url: http://download.redis.io/releases/redis-3.0.6.tar.gz
 src_file_sha256: 6f1e1523194558480c3782d84d88c2decf08a8e4b930c56d4df038e565b75624


redis:
 conf: Debian/redis.conf.j2

 OPTIONAL: redis.conf can define the location of the main configuration file can be relative or full path.
```

Note: The role will use the redis_install.download_url to extract the version.
      ( URL must end with a filename redis-X.Y.Z.tar.gz where X.Y.Z is the version )


Example (Recommended to define in group_vars or host_vars):

```
redis:
 conf: group_files/my-group/redis/redis.conf.j2
```

FORMAT: group_files/<group>/<role>/redis.conf.j2


License
-------

MIT


Author Information
------------------

Tal Lannder

tal@pjili.com
