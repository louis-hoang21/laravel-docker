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

# Depends_on Express dependency between services => [Detail](https://docs.docker.com/compose/compose-file/compose-file-v3/)
```
#Nginx Service

depends_on:
  - mysql
```

# Aliases when using multiple services PHP => [Detail](https://docs.docker.com/compose/compose-file/compose-file-v3/)
```
#Nginx Service

networks:
  blog-network:
    aliases:
      - api.xyz
```

# Import MySQL database in Docker

```
docker ps
docker exec -i [mysql_container_name] mysql -u[username] -p[password] [DB name] < [path/to/sql/file]
```

# Edit file hosts

```
vim /etc/hosts
```

# [Show more docker](https://docs.docker.com/get-started/)
# [Docker hub](https://hub.docker.com/)
