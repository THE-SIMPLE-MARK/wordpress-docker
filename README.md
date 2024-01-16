# wordpress-docker
Boilerplates for managing multiple wordpress sites under 1 machine & 1 IP using docker-compose and NGINX.

## How it works

The idea behind the whole thing is that you have your sites in docker-compose instances, where each instance has
it's own wordpress, DB, and an NGINX instance. You can easily fire up new wordpress sites when needed using
docker-compose, and then simply modify the main NGINX instance to route to that new webserver.

## How to use
This is quick tutorial is primarly for Ubuntu-based systems. You can substitute the OS-specific commands to your own easily though.

1. Install nginx
   
   ```bash
   sudo apt install nginx
   ```
2. Clone this repository
  
  ```bash
  git clone https://github.com/THE-SIMPLE-MARK/wordpress-docker.git
  
  # enter the freshly cloned directory
  cd wordpress-docker
  ```
3. Modify your main NGINX config
   You can either modify `nginx_http.conf` or `nginx_https.conf` depending on if you intend to use https or not.
   
   Both files provide a basic example of the multi-domain routing. You need to replace `{DOMAIN1}` and `{DOMAIN2}` as with your actual domain(s).
   You can remove the instances of the second domain with a pretty basic knowledge of NGINX's config syntax if you only intend to use one or add more if you need more instances.
   ```bash
   sudo nano /main_nginx/nginx_http.conf
   # or
   sudo nano /main_nginx/nginx_https.conf
   ```
4. Override the default NGINX config with your own
   ```
   sudo cp /main_nginx/nginx_http.conf /etc/nginx/nginx.conf
   # or
   sudo cp /main_nginx/nginx_https.conf /etc/nginx/nginx.conf
   ```
5. Create site directory
   TODO
6. Edit docker compose config
   TODO
7. Create env variable
   TODO
9. Execute docker-compose
    TODO
