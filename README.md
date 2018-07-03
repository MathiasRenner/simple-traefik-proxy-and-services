# Traefik proxy with backend services
Simple example of **docker and traefik as (SSL) proxy** or load balancer **in front of a flexible infrastructure of backend services**, like this one

![Architecture](https://raw.githubusercontent.com/containous/traefik/master/docs/img/architecture.png)

## How to use

### Prerequisites
- Docker and Docker-Compose must be installed

### Start up frontend proxy
- Clone this repo: `TODO`
- Go into folder `frontend-traefik`: `cd frontend-traefik`
- Create `acme.json` to persist SSL certificate data and set correct permissions: `touch traefik-conf/acme.json && chmod 600 traefik-conf/acme.json`
- Customize config file `traefik-conf/traefik.toml` to your environment. Change `domain` and `email`.
- Create docker network for the proxy: `docker network create proxy`
- Start traefik: `docker-compose up -d`

### Start up backend services
- Go into a folder of the backend services and follow the specific README.

## Kudos
Thanks to [firecyberice](@https://github.com/firecyberice) for the basic idea and [baez90](https://github.com/baez90) for remembering me about this architecture and providing a working example!


