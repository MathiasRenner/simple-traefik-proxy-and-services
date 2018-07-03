# Bluespice wiki

Project URL: https://de.bluespice.com/

## How to run
- Customize the config in file `.env` to your environment. Changing variable `WIKI_URL` to your domain is mandatory, changing others are optional.
- Within this folder, run `docker-compose up -d`.
- Within ~5 minutes, you should be able to see the wiki in your browser. Check the logs for more info `docker-compose logs -f`
