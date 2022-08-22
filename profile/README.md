## Elephantbox: Production Grade PHP / Nginx / Node Docker Image

- built on the excellent https://github.com/phusion/baseimage-docker (minimal Dockerized Ubuntu)
- PHP + Nginx as a **logical service**
- PHP delivered via Ondřej Surý's PHP
- latest Node for building frontend assets
- suitable for all environments from development to production
- can be used as a parent or a baseimage

### Quickstart

In your PHP project, create a `docker-compose.yml` file:

```yml
version: '3.7'

services:

  web:
    image: elephantbox/elephantbox:latest
    command: run-services nginx,php-fpm
    environment:
      APP_NAME: my-project-name
      APP_ENV: local
    ports:
      - 8000:80
    volumes:
      - .:/app
```

Then on the console run:

```
$ docker-compose up -d
```

Your application will be available on port 8000 (http://localhost:8000)

### Versions

|   | Release / Tag Name | Ubuntu Version | PHP Version | Node Version |
| - | ------------------ | -------------- | ----------- | ------------ |
| latest| `focal-p81n18` | 20.04 (Focal) | 8.1 | 18 |
|   | `jammy-p81n18` | 22.04 (Jammy) | 8.1 | 18 |

