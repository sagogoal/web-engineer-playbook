# 02. 基本設計

要件定義で固まった「何を作るか」を、エンジニアリングの観点から「どう作るか」に変換するフェーズ。
この段階での設計の質が、将来の拡張性、メンテナンス性、パフォーマンスに大きく影響する。

---
## 2.1. アーキテクチャ設計
- [ ] **DGN-001:** モノリスとマイクロサービスのメリット・デメリットを説明できる。
  <details>
  <summary>実務での思考プロセス</summary>
  
  - 開発初期の速度、チーム規模、将来の拡張性といった観点で、どちらが適しているか判断する。
  - トレードオフ（例: マイクロサービスの運用複雑性）を理解する。
  </details>

- [ ] **DGN-002:** BFF (Backend For Frontend) パターンが必要なケースを説明できる。
  <details>
  <summary>実務での思考プロセス</summary>
  
  - クライアント（Web, iOS, Android）ごとにAPIの要求が大きく異なる場合に検討する。
  - BFFの導入による開発・運用コスト増を考慮する。
  </details>

- [ ] **DGN-003:** レイヤードアーキテクチャの各層の責務を説明できる。
  <details>
  <summary>実務での思考プロセス</summary>
  
  - プレゼンテーション層、アプリケーション層、ドメイン層、インフラストラクチャ層の依存関係の方向を意識する。
  - 各層の責務が混ざらないように設計する（例: ドメイン層が特定のフレームワークに依存しない）。
  </details>

- [ ] **DGN-004:** 簡単なアプリケーションのディレクトリ構成をレイヤードアーキテクチャに基づいて設計する。
  <details>
  <summary>手を動かす</summary>
  
  - 「ユーザー情報を取得するAPI」を想定する。
  - `sample/DGN-004_directory_structure.txt` に、`controller`, `service`, `repository`, `domain` といったディレクトリ構造を作成・記述する。
  </details>

---
## 2.2. API設計
- [ ] **DGN-005:** RESTの原則（リソース、URI、HTTPメソッド）に基づき、APIエンドポイントを設計できる。
  <details>
  <summary>手を動かす</summary>
  
  - 「ブログ記事」リソースに対するCRUD操作を想定する。
  - `sample/DGN-005_rest_api.md` に、一覧取得, 詳細取得, 新規作成, 更新, 削除 の5つの操作に対応するHTTPメソッドとURIのペアを記述する。
  </details>

- [ ] **DGN-006:** APIの成功時レスポンス（JSON）の命名規則とデータフォーマットを定義できる。
  <details>
  <summary>手を動かす</summary>
  
  - `sample/DGN-006_response_format.json` を作成する。
  - ユーザー情報の取得APIを想定し、命名規則（例: camelCase）、日付フォーマット（例: ISO 8601）、ネスト構造を含むサンプルJSONを記述する。
  </details>

- [ ] **DGN-007:** APIのエラーレスポンスの共通フォーマットを定義できる。
  <details>
  <summary>手を動かす</summary>
  
  - `sample/DGN-007_error_response.json` を作成する。
  - バリデーションエラー（400 Bad Request）を想定し、エラーコード、エラーメッセージ、どの項目がエラーか、といった情報を含む共通のエラーレスポンス形式を定義する。
  </details>

- [ ] **DGN-008:** JWT (JSON Web Token) を使った認証方式のフローを説明できる。
  <details>
  <summary>実務での思考プロセス</summary>
  
  - ログイン時にサーバーが署名付きJWTを生成し、クライアントに返す。
  - クライアントは以降のリクエストで、そのJWTをAuthorizationヘッダーに含める。
  - サーバーはリクエストのたびにJWTの署名を検証する。
  - サーバーがステートレスになるメリットを理解する。
  </details>

- [ ] **DGN-009:** OpenAPI (Swagger) を使って、API仕様をYAML形式で記述できる。
  <details>
  <summary>手を動かす</summary>
  
  - `sample/DGN-009_openapi.yaml` を作成する。
  - 「GET /users/{id}」というユーザー取得APIの仕様（パス、パラメータ、成功レスポンス、失敗レスポンス）をOpenAPI 3.0形式で記述する。
  </details>

---
## 2.3. 図による表現
- [ ] **DGN-010:** Mermaid記法を使い、シーケンス図を作成できる。
  <details>
  <summary>手を動かす</summary>
  
  - 「ユーザーがログインボタンを押し、APIサーバーがDBを検証して、トークンを返す」という流れを想定する。
  - `sample/DGN-010_sequence_diagram.md` に、上記の流れをMermaidのシーケンス図として記述する。
  </details>

- [ ] **DGN-011:** Mermaid記法を使い、ER図を作成できる。
  <details>
  <summary>手を動かす</summary>
  
  - 「1人のユーザーは複数の投稿を持つ（1対多）」という関係を想定する。
  - `sample/DGN-011_er_diagram.md` に、`users`テーブルと`posts`テーブルの関係性をMermaidのER図として記述する。
  </details>

- [ ] **DGN-012:** C4モデルのコンテキスト図とコンテナ図の違いを説明できる。
  <details>
  <summary>実務での思考プロセス</summary>
  
  - **コンテキスト図:** システムと外部環境（ユーザー、外部システム）との関係に焦点を当てる（最もズームアウトした視点）。
  - **コンテナ図:** システムを構成する要素（Webアプリ、API、DBなど）に焦点を当てる（少しズームインした視点）。
  </details>

---
## 2.4. フロントエンド設計
- [ ] **DGN-013:** Atomic Designの各要素（Atoms, Molecules, Organisms）を説明できる。
  <details>
  <summary>実務での思考プロセス</summary>
  
  - **Atoms:** それ以上分解できない最小単位（例: ボタン、インプット）。
  - **Molecules:** Atomsを組み合わせた小さな部品（例: 検索フォーム）。
  - **Organisms:** Moleculesを組み合わせた大きな部品（例: ヘッダー）。
  - なぜこの考え方が再利用性を高めるのかを理解する。
  </details>

- [ ] **DGN-014:** 状態管理のスコープ（ローカル/グローバル）の使い分けを判断できる。
  <details>
  <summary>実務での思考プロセス</summary>
  
  - **ローカルステート:** 特定のコンポーネント内でのみ使う状態（例: `useState`）。
  - **グローバルステート:** 複数のコンポーネントで共有する状態（例: `Context API`, `Redux`）。
  - 「Prop Drilling（バケツリレー）」を避けるためにグローバルな状態管理を検討するタイミングを理解する。
  </details>
