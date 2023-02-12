# wordpress backup to s3

## There are some dependencies to use this script:

1- [s3cmd](https://s3tools.org/s3cmd) must be installed.

2- s3cmd must be configured with its configuration file: config sample file name is `.s3cfg`.

3- If you want to use mysqldump without providing password input, consider configuring `.my.conf` file in the `$HOME/.my.cnf` location, otherwise you have to change the mysqldump command. consider reading this [thread](https://stackoverflow.com/questions/9293042/how-to-perform-a-mysqldump-without-a-password-prompt). You need to set `-m` flag as first argument.  Example: `./backup-sql.sh -m`

4- [ccrypt](https://ccrypt.sourceforge.net) must be installed.

5- `config.sh` must be filled like `config.sample.sh`.

## How to run:

Simple run, in this mode the backup file will also be located on your machine: `/root/db_backups`

Run with `-r` flag. This option will remove the local copy of the backup.

Run with `-e` flag. This option will encrypt the backup dump using provided `SECRET` in the config file.

Run with `-a` flag. This option will alert you and call the endpoint you provided in config file.

Examples:

`./wordpress-backup -rame`

`./wordpress-backup -ame`

`./wordpress-backup -ae`