# Docker database with GUI

## Customize Composition
Copy .env.sample to .env and edit it at your convenience

## Run Container Database
### 1 - First time
docker-compose up -d

docker-compose -p projectname up -d // donner  le nom projectname en plus , -d pour le mode daemon

docker-compose --env-file .env.test -d // pour avoir un nom d'environnement différent de ".env"

docker-compose -p projectname --env-file .env.test -d
### 2 - Start/Stop
docker-compose start

docker-compose start db

docker-compose start gui

### 3 - Logs
docker-compose logs db
docker-compose logs gui

### 4 - Run Postgresql Command Line Tool
- interactive mode

docker-compose -p dbpoe exec -it db psql -U poe -d dbpoe

- for one query

docker-compose -p dbpoe exec -it db psql -U poe -d dbpoe -c "select * from poes"

