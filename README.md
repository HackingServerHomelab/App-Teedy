# App-Teedy

## First Time Prerequisites

1. `rm ./Data/postgres/.gitkeep`
2. Run [Traefik](https://github.com/mattlombana/App-Traefik)

## Running the Containers

1. Update the following volumes in [docker-compose.yml](./Docker/docker-compose.yml)
    * `../Data/teedy:/docs`
    * `../Data/postgres:/var/lib/postgresql/data`
1. Update the following lines in [docker-compose.yml](./Docker/docker-compose.yml)
    * `DOCS_BASE_URL=https://localhost`
    * `DATABSASE_URL=postgresql://postgres:5432/teedy`
    * `DATABASE_USER=teedy`
    * `DATABASE_PASSWORD=changeme`
    * `POSTGRES_PASSWORD=changeme`
2. Update the Traefik host label in [docker-compose.yml](./Docker/docker-compose.yml)
    * ``"traefik.http.routers.teedy.rule=Host(`localhost`)"``
3. Run `docker-compose -f ./Docker/docker-compose.yml up -d`

## First Time Setup

1. Visit <https://your-ip>
