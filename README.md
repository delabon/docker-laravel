## Docker for Laravel 10.+

### Add domain to /etc/hosts (host)

```bash
sudo vi /etc/hosts
127.0.0.111  laravel.test
```

### Install mkcert (host)

```bash
sudo apt install libnss3-tools
curl -JLO "https://dl.filippo.io/mkcert/latest?for=linux/amd64"
chmod +x mkcert-v*-linux-amd64
sudo mv mkcert-v*-linux-amd64 /usr/local/bin/mkcert
cd config/ssls/
mkcert -install laravel.test
```

### Up containers (host)

```bash
docker-compose up --build -d
```

### Connect to container bash (host)

```bash
docker exec -it container_id bash
```

### Install laravel (php-container)

```bash
git config --global user.email "example@example.com"
git config --global user.name "John Doe"

composer create-project laravel/laravel example-app
```

### npm install / watch / install package (host)

```bash
docker-compose run node-service npm install
docker-compose run node-service npm i bootstrap --save-dev
docker-compose run node-service npm run watch
```
