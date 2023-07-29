# Self-hosted services setup
 
### Nextcloud check

```bash
docker compose exec --user www-data app php occ status
```


### Outline server (shadowbox) installation on arm64

```bash
 SB_IMAGE="kugaevsky/outline-server-arm64" bash -c "$(wget -qO- https://raw.githubusercontent.com/kugaevsky/outline-server-arm64/master/src/server_manager/install_scripts/install_server.sh)"
 ```


### Get wildcard certificate with CloudFlare DNS

Install `certbot`:

```bash
apt update
apt install software-properties-common
add-apt-repository universe ppa:certbot/certbot
apt update
apt install certbot python3-certbot-dns-cloudflare
```

Set up `cloudflare.ini`:

```
dns_cloudflare_email = "me@example.com"
dns_cloudflare_api_key = "***"
```

Obtain certificate:

```bash
certbot certonly --dns-cloudflare --dns-cloudflare-credentials /root/cloudflare.ini -d example.com,*.example.com --preferred-challenges dns-01
```
