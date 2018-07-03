# Bluespice wiki

- Project URL: https://de.bluespice.com/
- Base Docker image: https://github.com/kns-it/Docker-BlueSpice-Wiki

## How to run
- Customize the config in file `.env` to your environment. Changing variable `WIKI_URL` to your domain is mandatory, changing others are optional.
- Within this folder, run `docker-compose up -d`.
- Within ~5 minutes, you should be able to see the wiki in your browser. Check the logs for more info `docker-compose logs -f`. In the logs, you should see the message `Correct permissions to ensure that web server is able to access the web directory...` for several minutes, until the web server apache starts (automatically) and the project is up and running.
