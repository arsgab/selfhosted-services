# Self-hosted services setup
 
## Nextcloud check

```bash
docker compose exec --user www-data app php occ status
```


## Outline server (shadowbox) installation on arm64

```bash
 SB_IMAGE="kugaevsky/outline-server-arm64" bash -c "$(wget -qO- https://raw.githubusercontent.com/kugaevsky/outline-server-arm64/master/src/server_manager/install_scripts/install_server.sh)"
 ```
