# docker-mariaDB
Set up a quick mariaDB database using docker

## Configuration

You need to modify `run.sh`, pointing it to your local storage - e.g. Mac OSX local machine
```
docker run -e MYSQL_ROOT_PASSWORD=1234 -d -p 3333:3306 -v /Users/db/mariadb:/var/lib/mysql mariadb
```
If you are on MacOS, this config is ready to go!

## Running Docker
```
git clone https://github.com/AlberErre/docker-mariaDB.git
sudo mkdir /Users/mariadb
cd docker-mariaDB
sudo bash run.sh
```

If everything was ok, you should have a docker container running in the background.
To ensure it's running just use:
```
docker ps
```

## Interacting with your database

You can use [SQLElectron](https://sqlectron.github.io/) to interact with your database, run queries, etc. 

### Config SQLElectron exmaple
![SQLElectron config example (Mac OS)](https://github.com/AlberErre/docker-mariaDB/blob/master/mariaDB-example.png)

## Kill your docker container (MariaDB)

```
docker kill DOCKER_UUID
```

Happy shipping!
