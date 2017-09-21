user@6adead0ee21e:/projects$ sudo -u postgres createuser user
user@6adead0ee21e:/projects$ sudo -u postgres psql
psql (9.5.9, server 9.5.2)
Type "help" for help.

postgres=# create database dspace
postgres-# ;
CREATE DATABASE
postgres=# grant all on database dspace to "user"
postgres-# ;
GRANT
postgres=# \q
user@6adead0ee21e:/projects$ psql
psql: FATAL:  database "user" does not exist
user@6adead0ee21e:/projects$ psql -d dspace


user@6adead0ee21e:/projects$ sudo -u postgres psql
psql (9.5.9, server 9.5.2)
Type "help" for help.

postgres=# alter user "user" with password 'dspace;
postgres'# ^C
postgres=# alter user "user" with password 'dspace';

install pgcrypto

-----

cp dspace/config/local.cfg.EXAMPLE local.cfg
  - set install path
  - set db password
  - create symlinks in ~/tomcat8/webapps

run install
run migrate

---

link