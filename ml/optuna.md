# Optuna

## Connect to PostgeSQL Database
- connection string: `postgresql://<user>:<password>@<url>/<database>`
- connection string with SSL verification: `postgresql://<user>:<password>@<url>/<database>?sslmode=verify-full`

For SSL verification the root-cart must be placed in `.postgresql/root.crt` (also see: <https://www.postgresql.org/docs/10/libpq-ssl.html#LIBPQ-SSL-PROTECTION>).

## Command-Line Interface
- Show all studies in database: `optuna studies --storage <storage>`
- Delete a study: `optuna delete-study --study-name <study-name> --storage <storage>`
- Start dashboard that is updated in realtime: `optuna dashboard --study <study_name> --storage <storage>`
- also see: https://optuna.readthedocs.io/en/latest/tutorial/cli.html
