# Traefik reverse proxy with backend services

Get your own services running - within just a few minutes and with automatic SSL.

This project uses **[Docker](https://www.docker.com/) and [traefik](https://traefik.io/) as automatic SSL proxy** with auto-redirect from http to https **in front of a flexible infrastructure of backend services**, like this one:

![Architecture](https://raw.githubusercontent.com/containous/traefik/master/docs/img/architecture.png)

## How to use

### Prerequisites
- **Hardware:** a computer (localhost) or a server with a public domain pointing to that server, i.e. in the DNS zone file of the Domain, the A record must contain the IP address of the server.
- **Software:** `docker`, `docker-Compose` and `git` (all latest) must be installed.

### Step 1/2: Start up frontend proxy
- Clone this repo by running:

  ```git clone https://github.com/bitleaf/simple-traefik-proxy-and-services.git```

- Go into folder `frontend-traefik`, create empty file `acme.json` as store for SSL certificate data, and set correct permissions by running:  

  ```cd frontend-traefik && touch traefik-conf/acme.json && chmod 600 traefik-conf/acme.json```

- Customize the config file `traefik-conf/traefik.toml` to your environment. Change `domain` and `email`. Use `localhost` as domain if you use a local machine.

- Create docker network for the proxy:

  ```docker network create proxy```

- Start traefik:

  ```docker-compose up -d```

- Now continue with starting up at least one backend service in next section "Step 2/2". Don't worry about SSL. Traefik will automatically issue a valid SSL certificate from [Let's encrypt](https://letsencrypt.org/). If you run on localhost, traefik will issue a self-signed cert. In that case, some browsers will ask you to accept this self-signed cert before you can access the services.


### Step 2/2: Start up backend services
- Go into a folder of the backend services and follow the specific README. The service [backend-whoami](https://github.com/bitleaf/simple-traefik-proxy-and-services/tree/master/backend-whoami) is a simple first service to start with.

## Kudos
Thanks to [firecyberice](https://github.com/firecyberice) for the basic architectural idea of this deployment and [baez90](https://github.com/baez90) for providing a working example!

## Support this project

If you want this project to get better, support me with a few cents:

<a href="https://liberapay.com/Bitleaf/donate"><img alt="Donate using Liberapay" src="https://liberapay.com/assets/widgets/donate.svg"></a>

## License

![](https://www.gnu.org/graphics/gplv3-127x51.png)

The project is licensed unter the GPLv3.

Copyright (C) Mathias Renner

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

See <http://www.gnu.org/licenses/> fore more information.
