# task1

### Run

Docker compose

```bash
docker compose up -d
```

Just docker:

```bash
# build
docker build -t mynginx .
docker run -d -p 127.0.0.1:8080:80/tcp --rm mynginx:latest
# clean
docker ps -a | grep mynginx | awk '{ print $1 }' | xargs docker rm -f
docker rmi task1-nginx-mynginx:latest
# run inside
docker exec -it mynginx /bin/sh

docker run --mount type=volume,src=<volume-name>,dst=<mount-path>
```

Creating of less layers decreases image size:

- <https://habr.com/ru/companies/ruvds/articles/485650/>
- <https://ru.hexlet.io/courses/docker-basics/lessons/image-layers/theory_unit>

Utility

```bash
# launch on boot
sudo systemctl enable nginx
# not launch on boot
sudo systemctl disable nginx

sudo systemctl status nginx
sudo systemctl start nginx
sudo systemctl stop nginx
sudo systemctl restart nginx

### Using nginx commands
sudo /etc/init.d/nginx start # or sudo nginx -s start
sudo nginx -s start
sudo nginx -s stop
sudo nginx -s quit # graceful stop

sudo nginx -t # test configuration
sudo nginx -s reload # reload config

### Help
sudo nginx -h # print help and basic commands
sudo nginx -V # shows all configuration options
```

- [Beginner guide](https://nginx.org/en/docs/beginners_guide.html) on nginx.
- [Structure](https://docs.nginx.com/nginx/admin-guide/basic-functionality/managing-configuration-files/) of nginx config file.

