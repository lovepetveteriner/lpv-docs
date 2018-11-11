# Up and Running with Lovepetveteriner

## Production

```shell
chmod 600 acme.json
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d ui rp

docker-compose -f docker-compose.yml -f docker-compose.prod.yml ps
```
