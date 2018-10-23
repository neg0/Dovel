# Dovel
Dovel is a Laravel and Docker Development Stack _(Tested with Laravel 5.x)_
> * PHP 7.2
> * NGINX 1.15
> * MySQL 8.0.13
> * Redis 5.0.0

I should have added some shell scripts to automate build via docker compose and entering containers but since I don't value Laravel, this is it :D Enjoy!

## Build via Docker Compose
__For Windows and Linux:__
```bash
$: docker-compose -f docker/docker-compose.yml up --build
```

__For Mac only:__
```bash
$: docker-compose -f docker/docker-compose.mac.yml up --build
```

### Access tty for each container

_Enter PHP container:_
```bash
$: docker-compose -f docker/docker-compose.yml exec php bash
```

_Enter MySql container:_
```bash
$: docker-compose -f docker/docker-compose.yml exec mysql bash
```
_Enter Redis container:_
```bash
$: docker-compose -f docker/docker-compose.yml exec redis bash
```

_Enter NGINX container:_
```bash
$: docker-compose -f docker/docker-compose.yml exec nginx bash
```
