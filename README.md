# Multiple Wordpress instance with NGINX on Docker Compose
Deploy a multiple Wordpress instance architecture that handles HTTPS support e multi domain reverse proxy.
## Server requirements
Both Docker and Docker Compose must be installed on the host machine.

Install Docker Engine: https://docs.docker.com/engine/install/
Install Docker Compose: https://docs.docker.com/compose/install/

## Wordpress PHP Setup
You can modify the `wp-config/uploads.ini` file to manage your own PHP configuration.

A base configuration is already set.

## Nginx Setup
You can modify the `nginx-config/my_proxy.conf` file to manage your own Nginx configuration.

A base configuration is already set.

## Run everything
Inside the main folder run:
`docker-compose up -d`

## Local testing
For local development set the values of `VIRTUAL_HOST` and `LETSENCRYPT_HOST` environment variables to custom domain. (e.g. wordpressone.com). 

Make sure to use a valid domain ending and to add the domain to your hosts file.

E.g. add this line `127.0.0.1 wordpressone.com` to /etc/hosts and restart the browser.

## Take care!
The docker volumes in this configuration will persist.

Run the command `docker compose down` with the `--volumes` option only in case you need to clean the data storage.