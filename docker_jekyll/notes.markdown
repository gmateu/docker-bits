docker container run -p 80:80 -d --name webhost nginx

docker container run -d -p 3306:3306 --name db -e MYSQL_RANDOM_ROOT_PASSWORD=yes mariadb

docker container logs db  > logs.txt

docker container logs db  | grep pass

docker container exec -it db mysql -p

#eliminam contenidor
docker container stop db 
docker container rm db

#cream volum
docker volume create mysql-db-data

#up mysql with volumne for presisten data
docker run -d -p 33060:3306 --name db  -e MYSQL_ROOT_PASSWORD=secret --mount src=mysql-db-data,dst=/var/lib/mysql mariadb

#enter shell


#apache
docker container run -d --name webserver -p 8080:80 httpd

#proxy
docker container run -d --name proxy -p 80:80 nginx
docker container top nginx
docker container inspect nginx
docker container stats nginx

#stop
docker stop  proxy webserver db

#delete
docker rm  proxy webserver db

