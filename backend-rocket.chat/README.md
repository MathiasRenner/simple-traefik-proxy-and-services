# Rocket.chat

- Project URL: https://rocket.chat

## How to run
1. Provide your environment-specific data in the config file `.env`. Changing the DB password is optional, but recommended.
1. Within this folder, run `docker-compose up -d db && sleep 20 && docker-compose up -d db-init && sleep 20 && docker-compose up -d`.
1. After about 1-2 Minutes, you should be able to see the website of your new Rocket.chat instance in your browser at `chat.your-domain.com`
