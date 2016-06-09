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
 download_url: http://download.redis.io/releases/redis-3.2.0.tar.gz
 src_file_sha256: 989f1af3dc0ac1828fdac48cd6c608f5a32a235046dddf823226f760c0fd8762

redis_conf: Debian/redis.conf.j2


 OPTIONAL: redis.conf can define the location of the main configuration file can be relative or full path.
```

Note: The role will use the redis_install.download_url to extract the version.
      ( URL must end with a filename redis-X.Y.Z.tar.gz where X.Y.Z is the version )


Example (Recommended to define in group_vars or host_vars):

```
redis_conf: group_files/my-group/redis/redis.conf.j2
```

Recommended path structure: group_files/<group>/<role>/redis.conf.j2


License
-------

MIT


Author Information
------------------

Tal Lannder

tal@pjili.com
