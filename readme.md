# Docker MongoDB Server
A simple docker setup to run a mongodb server accessible via localhost.

The docker-compose file is not setup to create a database. Creating a database needs to be done manually once the container is running using the command line, or Mongodb Compass .

If using this in a new project, be sure to update the following configuration settings in the docker-compose.yml file:
- container_name
- volumes

## commands

### start docker
```sh
docker-compose up -d
```

### stop docker
```sh
docker-compose down
```

### stop docker and delete volumes (databases)
```sh
docker-compose down -v
```

### log into the container
```sh
docker exec -it docker_mongodb_server /bin/bash
```

### export the database (run outside of mysql shell)
```sh
mongodump --db DATABASE_NAME --authenticationDatabase=admin -u root -p root -o databases
```

### import a database (run outside of mysql shell)
```sh
mongorestore  --db DATABASE_NAME --authenticationDatabase=admin -u root -p root ./databases/DATABASE_NAME
```

### log into the mysql shell
```sh
mongo admin -u root -p root
```

## mongodb connection settings
These setttings can be used in your project settings or database management application (MongoDB Compass)

Database Connection String:
```sh
mongodb://root:root@localhost:27017
```

| KEY | VALUE |
| ------ | ------ |
| HOST | mongodb://localhost |
| USER | root |
| PASSWORD | root |
| PORT | 27017 |


## extra resources
https://dev.to/sonyarianto/how-to-spin-mongodb-server-with-docker-and-docker-compose-2lef