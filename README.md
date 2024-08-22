## Docker for Laravel 11.+

### Add domain to /etc/hosts (host)

```bash
sudo nano /etc/hosts
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
docker exec -it php-container bash
```

### Install laravel (php-container)

```bash
composer create-project laravel/laravel .
```

### npm install / watch / install package (host)

```bash
docker-compose run --rm node-service npm install
docker-compose run --rm node-service npm run watch
```
