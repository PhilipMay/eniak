# Optuna

## Connection String for PostgeSQL Database
- basic: `postgresql://<user>:<password>@<url>/<database>`
- turn on ssl: `postgresql://<user>:<password>@<url>/<database>?sslmode=require`
- connection string with SSL verification: `postgresql://<user>:<password>@<url>/<database>?sslmode=verify-full`

For SSL verification the root-cart must be placed in `.postgresql/root.crt` (also see: <https://www.postgresql.org/docs/10/libpq-ssl.html#LIBPQ-SSL-PROTECTION>). On Microsoft Windows the file is named `%APPDATA%\postgresql\root.crt.` 

The location of the root certificate file and the CRL can be changed by setting the connection parameters `sslrootcert` and `sslcrl` or the environment variables `PGSSLROOTCERT` and `PGSSLCRL`. Example for connection string with SSL verification and root cert location: `postgresql://<user>:<password>@<url>/<database>?sslmode=verify-full&sslrootcert=/home/<user>/<some_dir>/<cert_name>.crt'`

## Command-Line Interface
- Show all studies in database: `optuna studies --storage <storage>`
- Delete a study: `optuna delete-study --study-name <study-name> --storage <storage>`
- Start dashboard that is updated in realtime: `optuna dashboard --study <study_name> --storage <storage>`
- also see: <https://optuna.readthedocs.io/en/latest/tutorial/cli.html>
