# traefik playgroung

a traefik demo playground

## dynamic configuration with 2 services

use docker-compose.yml to expose 2 internal service, 

```bash
docker-compose -f docker-compose.yml
```

## static configuration to expose external service

use static-conf.docker-compose.yml to expose 
    . 1 internal service, configured on docker
    . 1 external service, deployed outside docker cluster

to manage these services the static configuration was required
    . traefik.yml exposes the docker and file provider
    . to expose internal services use docker
    . to expose external services use file provider
    . config.yml defines the external services 


```bash
# to deploy the external service
docker run -d --rm -p 81:80 containous/whoami
# to deploy traefik
docker-compose -f docker-compose.yml
```