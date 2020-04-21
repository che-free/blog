---
title:  "MySQL(MariaDB) UTF-8 설정"
tags: curl
---

MySQL(MariaDB) UTF-8 설정 방법 정리.

## my.cnf 수정
```
[client]
default-character-set=utf8

[mysqld]
character-set-client-handshake = FALSE
init_connect="SET collation_connection = utf8_general_ci"
init_connect="SET NAMES utf8"
character-set-server = utf8

[mysql]
default-character-set=utf8

[mysqldump]
default-character-set = utf8
```

## 설정 정보 확인
```sql
-- character set 확인
show variables like 'char%';

-- collation 확인
show variables like '%collation%';
```


### UTF-8 설정 변경 전
```
MariaDB [(none)]> show variables like 'char%';
+--------------------------+----------------------------------------+
| Variable_name            | Value                                  |
+--------------------------+----------------------------------------+
| character_set_client     | euckr                                  |
| character_set_connection | euckr                                  |
| character_set_database   | latin1                                 |
| character_set_filesystem | binary                                 |
| character_set_results    | euckr                                  |
| character_set_server     | latin1                                 |
| character_set_system     | utf8                                   |
| character_sets_dir       | C:\mariadb\share\charsets\             |
+--------------------------+----------------------------------------+
8 rows in set (0.003 sec)

MariaDB [(none)]> show variables like '%collation%';
+----------------------+-------------------+
| Variable_name        | Value             |
+----------------------+-------------------+
| collation_connection | euckr_korean_ci   |
| collation_database   | latin1_swedish_ci |
| collation_server     | latin1_swedish_ci |
+----------------------+-------------------+
3 rows in set (0.002 sec)
```

### UTF-8 설정 변경 후
```
MariaDB [(none)]> show variables like 'char%';
+--------------------------+------------------------------------+
| Variable_name            | Value                              |
+--------------------------+------------------------------------+
| character_set_client     | utf8                               |
| character_set_connection | utf8                               |
| character_set_database   | utf8                               |
| character_set_filesystem | binary                             |
| character_set_results    | utf8                               |
| character_set_server     | utf8                               |
| character_set_system     | utf8                               |
| character_sets_dir       | C:\mariadb\share\charsets\         |
+--------------------------+------------------------------------+
8 rows in set (0.003 sec)

MariaDB [(none)]> show variables like '%collation%';
+----------------------+-----------------+
| Variable_name        | Value           |
+----------------------+-----------------+
| collation_connection | utf8_general_ci |
| collation_database   | utf8_general_ci |
| collation_server     | utf8_general_ci |
+----------------------+-----------------+
3 rows in set (0.002 sec)
```
