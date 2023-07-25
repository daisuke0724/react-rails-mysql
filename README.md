# React Rails MySQL Environment

## 開発環境の起動

開発環境は Dev Container または GitHub Codespaces を利用してください。  
快適に開発できる方をご利用ください。  
Dev Container を使って PC が重たくなる方は GitHub Codespaces をお勧めします。

> GitHub Codespaces は月 60 時間までは無料で使用可能です。  
> 無料枠を超えて使用する場合は従量課金する必要があります。  
> 無料枠を超えて 60 時間利用しても１ドル 140 円のレートだと 1500 円程度の費用です。

### Dev Container を利用した開発

#### セットアップ

##### Visual Studio Code インストール

1. [Download Visual Studio Code](https://code.visualstudio.com/download) ページにアクセス
2. OS に応じたインストーラーをダウンロード
3. インストールを行う

##### Docker Desktop インストール

1. [Download Docker Desktop](https://www.docker.com/products/docker-desktop) ページにアクセス
2. OS に応じたインストーラーをダウンロード
3. インストールを行う
  > Windows機のみWSL2の有効化を促される場合がある  
  > その際はインストーラーの案内に従って設定すること

#### 実行手順

1. Visual Studio Code を起動する
2. ソース管理タブを選択
3. リポジトリのクローンを選択
4. GitHub からの複製を選択
5. GitHub の認証を実施
6. 本リポジトリを選択
7. 右下のポップアップで「コンテナーで再度開く」ボタンを選択する

### GitHub Codespaces を利用した開発

#### 実行手順

1. 本リポジトリの Code タブを選択
2. Code ボタンを選択
3. Codespaces タブを選択
4. Create Codespace on main ボタンを選択

## サーバ起動方法

### 初回のみ

#### 実行手順

```bash
# イメージビルド
docker compose build --no-cache

# DB作成
docker compose run backend rails db:create
```

### 必要に応じて

#### 実行手順
```bash
# サーバ起動
docker compose up -d

# サーバ停止
docker compose down
```
