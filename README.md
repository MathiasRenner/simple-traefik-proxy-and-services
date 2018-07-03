# Traefik proxy with backend services
Simple example of **docker and traefik as SSL proxy** with auto-redirect from http to https **in front of a flexible infrastructure of backend services**, like this one:

![Architecture](https://raw.githubusercontent.com/containous/traefik/master/docs/img/architecture.png)

## How to use

### Prerequisites
- Docker and Docker-Compose must be installed

### Start up frontend proxy
- Clone this repo: `git clone https://github.com/bitleaf/simple-traefik-proxy-and-services.git`
- Go into folder `frontend-traefik`: `cd frontend-traefik`
- Create `acme.json` to persist SSL certificate data and set correct permissions: `touch traefik-conf/acme.json && chmod 600 traefik-conf/acme.json`
- Customize config file `traefik-conf/traefik.toml` to your environment. Change `domain` and `email`.
- Create docker network for the proxy: `docker network create proxy`
- Start traefik: `docker-compose up -d`
- Now continue startup up at least one backend service. Then, traefik can automatically setup SSL.

### Start up backend services
- Go into a folder of the backend services and follow the specific README. Use the `backend-whoami` as a simple first service.

## Kudos
Thanks to [firecyberice](https://github.com/firecyberice) for the basic architectural idea of this deployment and [baez90](https://github.com/baez90) for remembering me about this architecture and providing a working example!

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

