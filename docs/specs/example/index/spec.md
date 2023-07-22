# example 機能設計書

## UI イメージ

### 初期表示後

```
モック完成後にスクリーンショットを貼り付け
Figma のリンクでもOK
```

### 検索後

```
モック完成後にスクリーンショットを貼り付け
Figma のリンクでもOK
```

## 画面項目定義

### ヘッダ表示部

| #   | 項目名 | DB 項目 | 旧 DB 項目 |
| --- | ------ | ------- | ---------- |
| 1   | aaa    | bbb     |            |

### 一覧表示部

| #   | 項目名 | DB 項目 | 旧 DB 項目 |
| --- | ------ | ------- | ---------- |
| 1   | aaa    | bbb     |            |

## イベント定義

| #   | イベント名                    | ルーティング |
| --- | ----------------------------- | ------------ |
| 1   | [初期表示](#初期表示検索処理) | index        |
| 2   | [検索](#初期表示検索処理)     | index        |

## バリデーション定義

| #   | イベント | 項目 | バリデーション種別 |
| --- | -------- | ---- | ------------------ |
| 1   | 登録     | Foo  | Required           |

## メッセージ定義

| #   | イベント | 表示条件           | メッセージ内容     |
| --- | -------- | ------------------ | ------------------ |
| 1   | 検索     | 検索結果が０件の時 | データがありません |

## イベント詳細仕様

### 初期表示/検索処理

#### 仕様

初期表示時および検索ボタン選択時にデータベースからデータ取得・表示する

#### ER 図

```mermaid
erDiagram

    foo ||--|| foo_bar : "1:1"
    foo_bar ||--|| bar : "1:1"

    foo {
        bigint id PK
        bigint name "名称"
        timestamp created_at "登録日"
        timestamp updated_at "更新日"
    }

    bar {
        bigint id PK
        bigint name "名称"
        timestamp created_at "登録日"
        timestamp updated_at "更新日"
    }

    foo_bar {
        bigint id PK
        bigint foo_id FK
        bigint bar_id FK
        timestamp created_at "登録日"
        timestamp updated_at "更新日"
    }
```

#### 処理フロー

```mermaid
sequenceDiagram
    autonumber

    box whitesmoke Real
        actor User as 担当者
    end

    box ghostwhite Application
        participant Example as サンプル一覧
        participant Database as データベース
    end

    User->>+Example: 画面呼出 GET: /example
    Example-->>-User: 初期表示
    User->>+Example: 検索ボタン選択 GET: /example
    Example->>+Database: クエリ発行
    Database-->>-Example: 検索結果取得
    Example-->>-User: 検索結果表示
```
