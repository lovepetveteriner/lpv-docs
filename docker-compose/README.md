# Up and Running with Lovepetveteriner

## Production

```shell
chmod 600 acme.json
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d ui rp

docker-compose -f docker-compose.yml -f docker-compose.prod.yml ps
```

#### environment variables

```shell
vim ~/.bashrc
export LPV_DB_PASS=<password>
export LPV_MAIL_PASSWORD=<password>
export LPV_DB_ROOT_PASS=<mysql-root-password>
```

#### troubleshooting

```shell
newly created data directory /var/lib/mysql/ is unusable. You can safely remove it.
```

- above problem was a result of this:
  - previously i used the "db-data" volume for postgresql container
  - then i used the same volume for mysql without clearing it up or anything
  - probably mysql did not want to work with an non-empty/initialized-by-mysql directory

- change volume name to something else, it fixes the problem
