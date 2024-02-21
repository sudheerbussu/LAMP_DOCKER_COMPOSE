# LAMP_DOCKER_COMPOSE


Create a docker compose file for setting up LAMP architecture 



# vim docker-compose.yml

---
version: '3'

services:
 mydb:
  image: mysql:5
  environment:
   MYSQL_ROOT_PASSWORD: sunilsunil

 apache:
  image: tomcat
  ports:
   - 6060:8080
  links:
   - mydb:mysql


 php:
  image: php
  links:
   - mydb:mysql
   - apache:tomcat
...


:wq

# docker-compose up -d

To see the list of the containers
# docker container ls
( Observation - we are unable to see the php container)

# docker ps -a
