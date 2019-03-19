# Mediawiki

- Project URL: https://www.mediawiki.org/wiki

## How to run
1. Change your domain in the config file `.env`. Changing the DB password (`MYSQL_PASSWORD`) is optional.
1. Within this folder, run `docker-compose up -d`.
1. Within seconds, you should be able to see the mediawiki in your browser at `cloud.your-domain.com`. Follow the instructions in the setup. The database is not `localhost`, but `db`. See the `.env` file for further credentials.
1. At the end of the setup accept downloading the `LocalSettings.php` (will automatically be offered from the setup). Upload this file to the server in directory `simple-traefik-proxy-and-services/backend-mediawiki/data/wiki-config/`. *Before* that, delete the existing empty directory `LocalSettings.php`.
1. In the docker-compose file, delete the comment in front of this line: `- ./data/wiki-config/LocalSettings.php:/var/www/html/LocalSettings.php`
1. Run `docker-compose up -d` in folder `simple-traefik-proxy-and-services/backend-mediawiki` and you should have your mediawiki up and running.

### Install PHP extenstions
https://github.com/docker-library/docs/blob/31280550a3c7104fef824450753844d2f3d917be/php/README.md#how-to-install-more-php-extensions
