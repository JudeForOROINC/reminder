# reminder

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

