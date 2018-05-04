# PostgreSQL Cheat Sheet


### Commands

| Command                                                                               | Description                           |
| ---                                                                                   | ---                                   |
| `pg_ctl -D /usr/local/var/postgres -l server.log start`                               | Start server and save log             | 
| `pg_ctl -D /usr/local/var/postgres | tee /usr/local/var/postgres/server.log`          | Start server and watch log            |
| `pg_ctl -D /usr/local/var/postgres stop -s -m fast`                                   | Stop server           |
| `pg_ctl reload`                                                                       | Reload server           |
| ---                                                                                   | ---           |
| `createdb <database_name>`                                                            | Create database           |
| `dropdb <database_name>`                                                              | Drop database           |
| `createuser -U <user> --interactive`                                                  | Create PSQL user           |
| ---                                                                                   | ---           |
| `\conninfo`                                                                           | Display connection info (ie. port)           |
| `\l`                                                                                  | List all databases           |
| `\c`                                                                                  | Connect to specific database          |
| `\dt`                                                                                 | Describe all tables          |
| `\d <table_name>`                                                                     | Describe a specific table          |
| `\q` or `Ctrl + D`                                                                    | Quit console          |