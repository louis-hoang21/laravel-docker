# laravel-docker
How to setup PHP Laravel into Docker with NGINX and MySQL, REDIS

# Import MySQL database in Docker

```
docker ps
docker exec -i [mysql_container_name] mysql -u[username] -p[password] [DB name] < [path/to/sql/file]
```
