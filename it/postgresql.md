# PostgreSQL

## Config Files
- general config: `/etc/postgresql/10/main/postgresql.conf`
  - to allow access from everywhere: `listen_addresses = '*'`
- who can access what from where and how: `/etc/postgresql/10/main/pg_hba.conf`
  - example: `host    <database>        <user>        0.0.0.0/0               md5`

## Commands (prompt)
- enter db tool psql: `psql`
- create user: `createuser --interactive`
- create database
  - `createdb <db_name>`
  - create and set owner: `createdb <db_name> -o <role_name>`
- restart the db: `systemctl restart postgresql.service`

## Commands (psql)
- set pssword: `\password <role_name>`
- list user (roles): `\du`
- list user (roles) with passwords to check if they are set: `select * from pg_shadow;`
- list databases: `\l`
- detele db: `DROP DATABASE <db_name>;`
- delete role: `DROP ROLE <role_name>;`

## Links
- alter databases: https://www.postgresql.org/docs/10/sql-alterdatabase.html
