# Dockerized Strapi

A dockerized installation of Strapi for local development.

## What this Contains

* Run Strapi with PostgreSQL 12 via docker-compose
* Named volumes for Strapi and PostgreSQL
* Makefile for invoking docker-compose commands useful to this project,
  including the ability to SSH into the Strapi container.

## Misc Observations

### Strapi can't connect to DB at Startup

Possibly due to a bug in the MariaDB container and the MySQL container, Strapi
doesn't wait for the database to be fully initialized (even though Strapi's
container internally depends on the DB container) and thus it errors out while
starting. I switched to PostgreSQL and that problem has stopped.

### Admin UI doesn't load

Refer https://github.com/strapi/strapi/issues/3284 for solution

