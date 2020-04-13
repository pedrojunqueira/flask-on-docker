
### Flask on Docker with Nginx and PostgreSQL

This is from tutorial taken from testdriven.io and made few changes that worked for me.

Still to sort out some errors I had while executing the Dockerfile of the web container

### Project structure

``` bash
.
├── docker-compose.prod.yml
├── docker-compose.yml
└── services
    ├── nginx
    │   ├── Dockerfile
    │   └── nginx.conf
    └── web
        ├── Dockerfile
        ├── Dockerfile.prod
        ├── Dockerfile.prod_failed
        ├── entrypoint.prod.sh
        ├── entrypoint.sh
        ├── manage.py
        ├── project
        │   ├── __init__.py
        │   ├── config.py
        │   ├── media
        │   └── static
        │       └── hello.txt
        └── requirements.txt
```
Usage

``` bash

$ docker-compose -f docker-compose.prod.yml up -d --build
$ docker-compose -f docker-compose.prod.yml exec web python manage.py create_db
```

for a detail tutorial visit [post](https://testdriven.io/blog/dockerizing-flask-with-postgres-gunicorn-and-nginx/)
