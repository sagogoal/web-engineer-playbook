# 04. API (Application Programming Interface)

システムやサービス間の連携を担うインターフェース。
クライアント（フロントエンドや外部サービス）とサーバー（バックエンド）が円滑に通信するためのルールを定める。

---

## API-001 REST (Representational State Transfer)

### ゴール

RESTの設計原則（アドレス可能性、ステートレス性、接続性、統一インターフェース）を説明できる。

### 完了条件

- [ ] `artifacts` フォルダに成果物を作成する
  - [ ] `README.md`
  - [ ] `anki.csv`
  - [ ] `sample/`

### 実務での思考プロセス

- **リソース**ベースで設計されているか？
- URIでリソースを**一意**に示せているか？
- **HTTPメソッド**（GET, POST, PUT, DELETEなど）を正しく使い分けているか？
- サーバーはクライアントの**状態を保持しない**か？（ステートレス）
- やり取りされる情報に、次に行うべき操作への**リンク**を含められるか？ (HATEOAS)

---

## API-002 URI設計

### ゴール

RESTの原則に基づき、リソース指向で直感的かつ一貫性のあるURIを設計できる。

### 完了条件

- [ ] `artifacts` フォルダに成果物を作成する
  - [ ] `README.md`
  - [ ] `anki.csv`
  - [ ] `sample/`

### 実務での思考プロセス

- URIは**名詞の複数形**になっているか？ (`/users`, `/products`)
- URIに**動詞**を含んでいないか？ (`/getUsers` はNG）
- **階層構造**は直感的か？ (`/users/123/posts`)
- 適切な**HTTPメソッド**を選択できているか？ (GET, POST, PUT, DELETE)
- パラメータの渡し方は適切か？（Path Parameter, Query Parameter, Request Body）
- **命名規則**はプロジェクト内で統一されているか？（kebab-case, snake_caseなど）

### 関連項目

- DGN-001 (APIエンドポイント設計)

---

## API-003 HTTPステータスコード

### ゴール

レスポンスの種類に応じて、適切なHTTPステータスコードを返すことができる。

### 完了条件

- [ ] `artifacts` フォルダに成果物を作成する
  - [ ] `README.md`
  - [ ] `anki.csv`
  - [ ] `sample/`

### 実務での思考プロセス

- **成功時**:
  - `200 OK`: GET, PUT, DELETEの成功
  - `201 Created`: POSTによるリソース作成の成功
  - `204 No Content`: レスポンスボディがない成功（例: DELETE）
- **クライアントエラー時**:
  - `400 Bad Request`: リクエストの形式が不正（バリデーションエラーなど）
  - `401 Unauthorized`: 認証が必要
  - `403 Forbidden`: 認可されていない（権限がない）
  - `404 Not Found`: リソースが存在しない
- **サーバーエラー時**:
  - `500 Internal Server Error`: 予期せぬサーバー側のエラー
  - `503 Service Unavailable`: メンテナンス中や過負荷
