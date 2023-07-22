# React Rails MySQL Environment

## 実行手順

### 初回のみ

```bash
# イメージビルド
docker compose build --no-cache

# DB作成
docker compose run backend rails db:create
```

### 必要に応じて

```bash
# サーバ起動
docker compose up -d

# サーバ停止
docker compose down
```
