
# Docker Container + MongoDB

## Configuration - MongoDB

You need to modify `MongoDB/run.sh`, pointing it to your local storage - e.g. Mac OSX local machine `/Users/mongodb`
```
docker run -p 27017:27017 -d -v /Users/mongodb:/data/db mongo
```
If you are on MacOS, this config is ready to go!

## Check if MongoDB is running correctly on its port
```
netstat ao | grep 27017
```

## Running Docker
```
git clone https://github.com/AlberErre/docker-databases.git
mkdir /Users/mongodb
cd docker-databases/MongoDB
bash run.sh
```
Note: use `sudo` if needed.

If everything was ok, you should have a docker container running in the background.
To ensure it's running just use:
```
docker ps
```


# Docker Container + MariaDB ![Docker_MariaDB](https://github.com/AlberErre/docker-mariaDB/blob/master/docker_mariadb.png)
Set up a quick mariaDB database using docker

## Configuration - MariaDB

You need to modify `MariaDB/run.sh`, pointing it to your local storage - e.g. Mac OSX local machine `/Users/mariadb`
```
docker run -e MYSQL_ROOT_PASSWORD=1234 -d -p 3333:3306 -v /Users/mariadb:/var/lib/mysql mariadb
```
If you are on MacOS, this config is ready to go!

## Running Docker
```
git clone https://github.com/AlberErre/docker-databases.git
mkdir /Users/mariadb
cd docker-databases/MariaDB
bash run.sh
```
Note: use `sudo` if needed.

If everything was ok, you should have a docker container running in the background.
To ensure it's running just use:
```
docker ps
```

## Interacting with your database

You can use [SQLElectron](https://sqlectron.github.io/) to interact with your database, run queries, etc. 

### Config SQLElectron example
![SQLElectron config example (Mac OS)](https://github.com/AlberErre/docker-mariaDB/blob/master/mariaDB-example.png)

## Kill your docker container (MariaDB)

```
docker kill DOCKER_UUID
```

## Happy shipping!