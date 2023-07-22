# React Rails MySQL Environment

## 実行方法

```bash
# イメージビルド 初回のみ
docker compose build --no-cache

# DB作成 初回のみ
docker compose run backend rails db:create

# サーバ起動
docker compose up -d
```
