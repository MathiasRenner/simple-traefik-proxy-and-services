# Mediawiki

- Project URL: https://www.mediawiki.org/wiki

## How to run
1. Change your domain in the config file `.env`. Changing the DB password (`MYSQL_PASSWORD`) is optional.
1. Within this folder, run `docker-compose up -d`.

# After initial setup, download LocalSettings.php to the same directory as
# this yaml and uncomment the following line and use compose to restart
# the mediawiki service
# - ./LocalSettings.php:/var/www/html/LocalSettings.php


1. Within seconds, you should be able to see the mediawiki in your browser at `cloud.your-domain.com`
1. Run `docker-compose cp app:LocalSettings.php ./data/config/LocalSettings.php`


### Install PHP extenstions
https://github.com/docker-library/docs/blob/31280550a3c7104fef824450753844d2f3d917be/php/README.md#how-to-install-more-php-extensions
