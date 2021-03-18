# laravel-docker
How to setup PHP Laravel into Docker with NGINX and MySQL, REDIS

# Run docker-compose
```
docker-compose up -d
```

# Start/Stop docker-compose
```
docker-compose start/stop
```

# Check container docker
```
docker ps
```

# Docker exec container
```
docker exec -i [Container ID] sh/bash
```

# Import MySQL database in Docker

```
docker ps
docker exec -i [mysql_container_name] mysql -u[username] -p[password] [DB name] < [path/to/sql/file]
```

# [Show more docker](https://docs.docker.com/get-started/)
# [Form docker hub](https://hub.docker.com/)
