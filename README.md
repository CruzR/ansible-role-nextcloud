# ansible-role-nextcloud #

An ansible role to install nextcloud on a Debian stretch machine.

## Features ##

- Supports SQLite, MariaDB or ~~PostgreSQL~~__\*__. If you want to use MariaDB or
  PostgreSQL, make sure the DBMS is installed before using this role.
  You could use [my role for MariaDB](https://github.com/CruzR/ansible-role-mariadb)
  or [my role for PostgreSQL](https://github.com/CruzR/ansible-role-postgres),
  if you want to.

  __\* PostgreSQL support is currently broken. Contributions are welcome! :)__
- Supports TLS
- Installs APCu and Redis and sets up caching
- Supports installing additional nextcloud apps

## Variables ##

| Variable                              | Type            | Description                                      |
|---------------------------------------|-----------------|--------------------------------------------------|
| `nextcloud_admin_user` __\*__         | string          | Name of the nextcloud admin user to create.      |
| `nextcloud_admin_pass` __\*__         | string          | Password for the nextcloud admin user to create. |
| `nextcloud_data_directory` __\*__     | string          | Path of the nextcloud data directory.            |
| `nextcloud_database`                  | string          | One of `sqlite` (default), `mysql` and `pgsql`.  |
| `nextcloud_apps`                      | list of strings | Names of nextcloud apps that will be installed.  |
| `nextcloud_ssl`                       | bool            | Enable using TLS.                                |
| `nextcloud_ssl_certificate` __†__     | string          | Path of the TLS certificate chain file.          |
| `nextcloud_ssl_certificate_key` __†__ | string          | Path of the TLS private key file.                |

__\*__ Required variables
__†__ Required if `nextcloud_ssl` is true
