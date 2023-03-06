# reminder

mysql
-----

to upload dump under container: `sudo docker exec -i mysql_container_name mysql -uUserName -pPassword DBName < MyDump.sql` where mysql_container_name = name of container from `docker ps` , UserName - name of user, for example root,  Password - password of user for db , for example root, DBName - schema name where dump must be uploaded. MyDump.sql - file path and file name with dump from . root


ubuntu cli

docker container
----------------

`sudo docker-compose up -d` = set up container(s) run from project root folder with docker-compose.yaml

`sudo docker-compose exec php bash` = log in the conpainer php to cli

postgress
---------

`psql -h myhost -d mydb -U myuser` = login with host myhost database mydb and user myuser;

`\dn` = schemas list;

`\c my_schema` = connect to schema myshema;

`\dt` = list of tables of current schema;

curl 
----

`sudo apt install curl` istall curl

`curl lockalhost/my/url -XPOST -H"

to start new project
--------------------

- create with ```git clone my/github/url my_project```
new project
- ``` cd my_project ```
- ```git submodule add https://github.com/Laradock/laradock.git laradock_my_project```
- enter into sub folder with laradock ``` cd laradock_my_project ```
- do copy envitoment ```cp env-example .env```

project architecture
-----------

Main part is how to choose architecture type.  Classically famous frameworks propose MVC moniolith . it mean that you have all code in one repo sorted by folders that stored in frameworke. other case SOA Service oriented architecture. its alse can be monolith but with small classes like Service prefics or suffics. and of cource it can be separated service from aech other that logicaly or fisicaly ( DB, instance, or even container separated, redy to scale.) and last known type is micro services. it mean a lot of small or very small services that can be done with totally separation and that very simple. main idea - you can change or rebuild it without rebuilding all rest services. and if you have some problem with communication between this serwices you never know when it start :P  . So :
 - Monolith
 - SOA
 - Micro services.

How to build microservices
--------------------------

First rule it must be agnostic. service must know nothin about other world. it must know that it know only. for example if service store users, if must know nothing about previleges or favorite items or last login date or categories that recommended, ect. it must know about user. may be connect info or name and login end all thar related to this, email, register. servise with privilagies can have information about first level - permissions - but know nothing about rest.  service security can join info of two services - users and permissions.  and call them when check rights but do not store external info. Goal :  protection from dead lock.  user can not wait security message cause it never know that security exists.  so all requests with security (where, probably can generated dead lock) may be done from security side ( but it under one repo conrtol so its easy to find and fix this bug)
other profit is that we can have smal services with clear logic. and it is not hard to change it .  in monolish case logic separated between many classes so some time its imposible change somethin without braking all rest :)
