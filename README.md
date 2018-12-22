## Docker-Nginx-Freessl

![docker-nginx-freessl logo](https://raw.githubusercontent.com/arttberg/docker-nginx-freessl/master/logo.jpg)

Based on official [nginx](https://hub.docker.com/_/nginx/) image from docker hub.

For build and activate ssl follow steps below:

- Config nginx.conf for your needs

- From the directory of the repo run command:

`Docker build -t mynginx .`

- When it's finished run:

`docker-compose up -d`

And then get the running container id by command: `docker stats`

You need container bash:

`docker exec -ti <paste id or name here> /bin/bash`

When you in the container run the command below:

`certbot --nginx`  and follow certbot instructions

You will see congratilations message and can quit the container with `exit`.
Private key and chain files you can find in volume folder /configs/nginx/ssl/

Cron job will be renew certificat when it's expire automaticly.

Enjoy

![docker-nginx-freessl result](https://raw.githubusercontent.com/arttberg/docker-nginx-freessl/master/ssl-report.png)