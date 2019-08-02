# 简要说明

1. 创建 php 容器

```bash
    docker run -d --name php7 -v $PWD/www:/var/www/html -p 9000:9000 php:7.2-fpm
```

2. 创建 nginx 容器

```bash
docker run -d --name web -p 80:80 -v $PWD/www:/var/www/html -v $PWD/conf:/etc/nginx/conf.d --link php7:php7 nginx:1.16
```

