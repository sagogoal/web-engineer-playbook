# 03. データベース

アプリケーションの心臓部であり、データの永続性を担う重要な要素。
パフォーマンス、データの整合性、拡張性を考慮した設計と操作が求められる。

---
## 3.1. データモデリング
- [ ] **DB-001:** サロゲートキーとナチュラルキーの違いを説明できる。
  <details>
  <summary>実務での思考プロセス</summary>
  
  - **サロゲートキー（代理キー）:** `id`など、ビジネス上の意味を持たない一意な識別子。一般的に推奨される。
  - **ナチュラルキー（自然キー）:** `email`など、ビジネス上の意味を持つ一意な識別子。将来変更される可能性があるため、主キーには不向き。
  </details>

- [ ] **DB-002:** 外部キーの参照整合性アクション（`CASCADE`, `RESTRICT`, `SET NULL`）を説明できる。
  <details>
  <summary>実務での思考プロセス</summary>
  
  - 親レコードが削除されたとき、子レコードも一緒に消すべきか（`CASCADE`）、削除を禁止すべきか（`RESTRICT`）、`null`にすべきか（`SET NULL`）を要件に応じて判断する。
  </details>

- [ ] **DB-003:** 第3正規形までの正規化を説明できる。
  <details>
  <summary>実務での思考プロセス</summary>
  
  - **第1:** 繰り返し項目をなくす。
  - **第2:** 主キーの一部にだけ依存する項目を別テーブルに切り出す。
  - **第3:** 主キー以外の項目に依存する項目を別テーブルに切り出す。
  - データの一貫性を保つための原則として理解する。
  </details>

- [ ] **DB-004:** パフォーマンスのために非正規化を検討するケースを説明できる。
  <details>
  <summary>実務での思考プロセス</summary>
  
  - `JOIN`のコストが高い、読み取り頻度が非常に高い、といった場合に、あえて冗長なデータを持たせることを検討する。
  - 更新時の一貫性担保というトレードオフを理解する。
  </details>

- [ ] **DB-005:** `users`と`posts`テーブル（1対多）のCREATE TABLE文をSQLで記述する。
  <details>
  <summary>手を動かす</summary>

  - `sample/DB-005_create_tables.sql`を作成する。
  - `users`テーブル（id, name）と`posts`テーブル（id, user_id, title）を作成する。
  - `posts.user_id`には、`users.id`を参照する外部キー制約を設定する。
  </details>

---
## 3.2. SQL実践
- [ ] **DB-006:** `INNER JOIN`と`LEFT JOIN`の違いを説明できる。
  <details>
  <summary>実務での思考プロセス</summary>
  
  - **INNER JOIN:** 両方のテーブルに存在するデータのみを取得する（例: 投稿のあるユーザー一覧）。
  - **LEFT JOIN:** 左側のテーブルの全データと、それに紐づく右側のテーブルのデータを取得する（例: 全ユーザーと、それぞれの投稿一覧（投稿がなくてもユーザーは表示））。
  </details>

- [ ] **DB-007:** `INNER JOIN`を使って、ユーザーとそのユーザーの投稿を結合して取得するSQLを書ける。
  <details>
  <summary>手を動かす</summary>
  
  - `sample/DB-007_inner_join.sql`を作成する。
  - `users`テーブルと`posts`テーブルを`user_id`で結合し、ユーザー名と投稿タイトルを取得するクエリを記述する。
  </details>

- [ ] **DB-008:** `GROUP BY`と`COUNT`を使い、ユーザーごとの投稿数を集計するSQLを書ける。
  <details>
  <summary>手を動かす</summary>
  
  - `sample/DB-008_group_by.sql`を作成する。
  - `posts`テーブルを`user_id`でグループ化し、各ユーザーの投稿数をカウントするクエリを記述する。
  </details>

- [ ] **DB-009:** `WHERE`と`HAVING`の違いを説明できる。
  <details>
  <summary>実務での思考プロセス</summary>
  
  - **WHERE:** `GROUP BY`で集約される**前**のデータに対して絞り込みを行う。
  - **HAVING:** `GROUP BY`で集約された**後**の結果に対して絞り込みを行う（例: 投稿数が10件以上のユーザー）。
  </details>

- [ ] **DB-010:** N+1問題を検知し、`IN`句を使って解決するSQLを書ける。
  <details>
  <summary>手を動かす</summary>

  - N+1問題が起こるコード（擬似コードでOK）と、その解決策を`sample/DB-010_n_plus_one.md`に記述する。
  - **悪い例:** `for user in users: post = find_post(user.id)`
  - **良い例:** `user_ids = [user.id for user in users]; posts = find_posts_by_user_ids(user_ids)`
  </details>

---
## 3.3. パフォーマンス
- [ ] **DB-011:** インデックスが効かないケース（例: `LIKE`の前方一致以外）を説明できる。
  <details>
  <summary>実務での思考プロセス</summary>
  
  - `LIKE '%word'`（中間一致、後方一致）
  - カラムに関数を適用した場合 (`WHERE a_func(column) = 'value'`)
  - 否定形 (`!=`, `<>`)
  </details>

- [ ] **DB-012:** `EXPLAIN`を使って、SQLの実行計画を読み、フルスキャンが発生していることを確認できる。
  <details>
  <summary>手を動かす</summary>

  - `sample/DB-012_explain.txt`を作成する。
  - インデックスのないテーブルに適当な`SELECT`文を実行し、その`EXPLAIN`結果を貼り付ける。
  - 結果の`type`が`ALL`になっていることを確認する。
  </details>

- [ ] **DB-013:** 複合インデックスにおいて、カラムの順番が重要な理由を説明できる。
  <details>
  <summary>実務での思考プロセス</summary>
  
  - インデックスは左側のカラムから順に効く。
  - `(col_a, col_b)`というインデックスは、`WHERE col_a = '...'`には効くが、`WHERE col_b = '...'`には効かない。
  - 絞り込み条件でよく使われる（カーディナリティが高い）カラムを左に置くのが基本。
  </details>

---
## 3.4. トランザクションとロック
- [ ] **DB-014:** ACID特性（原子性, 一貫性, 独立性, 永続性）をそれぞれ説明できる。
  <details>
  <summary>実務での思考プロセス</summary>
  
  - データベースの信頼性を支える基本原則として理解する。
  - なぜこれらの特性が重要なのか、銀行の振り込み処理などを例に考える。
  </details>

- [ ] **DB-015:** デッドロックがどのような状況で発生するかを説明できる。
  <details>
  <summary>実務での思考プロセス</summary>
  
  - トランザクションAがリソースXをロックし、リソースYを待つ。
  - トランザクションBがリソースYをロックし、リソースXを待つ。
  - このようにお互いが相手のロック解除を待ち、永遠に処理が進まなくなる状態。
  </details>

- [ ] **DB-016:** `BEGIN`, `COMMIT`, `ROLLBACK`を使い、簡単なトランザクション処理をSQLで記述できる。
  <details>
  <summary>手を動かす</summary>
  
  - `sample/DB-016_transaction.sql`を作成する。
  - 2つの`UPDATE`文を`BEGIN`と`COMMIT`で囲んだ一連の処理を記述する。
  </details>
