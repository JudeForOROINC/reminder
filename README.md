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

