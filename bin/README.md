# zabbix-server

## Setup

1. Build command を実行

```sh
docker compose down -v; docker compose build --no-cache; git diff; docker compose up -d; docker compose ps; docker compose logs
```

2. zabbix sql を読み込ませてテーブル作成

```sh
zcat server.sql.gz | docker compose exec -T zabbix-database psql -U zabbix -d zabbix
```
