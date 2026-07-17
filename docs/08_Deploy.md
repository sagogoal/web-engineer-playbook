# 08. デプロイとCI/CD

---
## 8.1. Dockerとコンテナ
- [ ] **DPL-001:** Dockerが解決する「自分の環境では動いたのに」問題を説明できる。
- [ ] **DPL-002:** DockerイメージとDockerコンテナの違いを説明できる。
- [ ] **DPL-003:** `Dockerfile`の基本的な命令（`FROM`, `RUN`, `COPY`, `CMD`）を説明できる。
- [ ] **DPL-004:** Node.jsアプリケーションをDocker化する`Dockerfile`を記述する。
  <details>
  <summary>手を動かす</summary>
  - 簡単なExpressサーバーの`Dockerfile`を記述し、`docker build`でイメージをビルドし、`docker run`でコンテナを起動して`localhost`でアクセスできることを確認する。
  </details>
- [ ] **DPL-005:** `.dockerignore`ファイルの役割を説明できる。
- [ ] **DPL-006:** マルチステージビルドを使い、最終的なイメージサイズを削減するメリットを説明できる。
- [ ] **DPL-007:** `docker-compose.yml`を使い、複数のコンテナ（例: WebサーバーとDB）を連携して起動できる。
- [ ] **DPL-008:** Docker HubやECRなどのコンテナレジストリの役割を説明できる。

---
## 8.2. CI/CDの概念
- [ ] **DPL-009:** CI（継続的インテグレーション）の目的を説明できる。
- [ ] **DPL-010:** CD（継続的デリバリー/デプロイメント）の目的を説明できる。
- [ ] **DPL-011:** 継続的デリバリーと継続的デプロイメントの違いを説明できる。
- [ ] **DPL-012:** CI/CDパイプラインの典型的なステージ（lint, test, build, deploy）を説明できる。
- [ ] **DPL-013:** GitHub Actionsの基本的な概念（workflow, job, step, action）を説明できる。
- [ ] **DPL-014:** GitHub Actionsを使い、`main`ブランチへのpushをトリガーにテストを実行するワークフローを作成する。
  <details>
  <summary>手を動かす</summary>
  - `.github/workflows/ci.yml`を作成する。
  - `on: push`でトリガーを設定し、`npm install`と`npm test`を実行するステップを記述する。
  </details>

---
## 8.3. デプロイ戦略
- [ ] **DPL-015:** Blue/Greenデプロイメントの仕組みとメリット・デメリットを説明できる。
- [ ] **DPL-016:** カナリアリリースの仕組みとメリット・デメリットを説明できる。
- [ ] **DPL-017:** ローリングアップデートの仕組みを説明できる。
- [ ] **DPL-018:** デプロイとリリースの違いを説明できる。
- [ ] **DPL-019:** Feature Flagが「デプロイとリリースの分離」をどう実現するのか説明できる。
- [ ] **DPL-020:** ゼロダウンタイムデプロイの重要性を説明できる。
- [ ] **DPL-021:** アプリケーションのヘルスチェックエンドポイントの役割を説明できる。
- [ ] **DPL-022:** ロールバックの手順を説明できる。

---
## 8.4. クラウドとIaaS/PaaS/SaaS
- [ ] **DPL-023:** IaaS, PaaS, SaaSの違いを、管理責任の範囲を元に説明できる。
- [ ] **DPL-024:** 代表的なクラウドプロバイダー（AWS, GCP, Azure）を3つ挙げられる。
- [ ] **DPL-025:** EC2やGCEのようなIaaSコンピュートサービスの基本的な役割を説明できる。
- [ ] **DPL-026:** HerokuやVercelのようなPaaSのメリット・デメリットを説明できる。
- [ ] **DPL-027:** AWS S3やGCSなどのオブジェクトストレージのユースケースを説明できる。
- [ ] **DPL-028:** AWS RDSやCloud SQLなどのマネージドデータベースサービスのメリットを説明できる。
- [ ] **DPL-029:** VPC（Virtual Private Cloud）の基本的な役割を説明できる。
- [ ] **DPL-030:** セキュリティグループ（ファイアウォール）の役割を説明できる。
- [ ] **DPL-031:** IaC（Infrastructure as Code）のメリットを説明できる。
- [ ] **DPL-032:** Terraformの基本的な役割を説明できる。
- [ ] **DPL-033:** コンテナオーケストレーションツール（Kubernetes, ECSなど）の必要性を説明できる。

---
## 8.5. 環境と設定
- [ ] **DPL-034:** 開発、ステージング、本番環境の役割の違いを説明できる。
- [ ] **DPL-035:** Git-flowやGitHub Flowなどのブランチ戦略を説明できる。
- [ ] **DPL-036:** 環境変数で設定を管理する重要性を説明できる。
- [ ] **DPL-037:** Secret Manager（AWS KMS, GCP Secret Managerなど）の役割を説明できる。
- [ ] **DPL-038:** Gitのタグを使ったバージョン管理の方法を説明できる。
- [ ] **DPL-039:** CHANGELOGの重要性を説明できる。
- [ ] **DPL-040:** `ssh`を使ってサーバーにログインできる。
- [ ] **DPL-041:** `scp`を使ってサーバーにファイルを転送できる。
- [ ] **DPL-042:** CI/CDパイプラインの実行時間を計測し、ボトルネックを特定する。
- [ ] **DPL-043:** パイプラインのキャッシュを活用して、ビルド時間を短縮する。
- [ ] **DPL-044:** モノレポとマルチレポのメリット・デメリットを説明できる。
- [ ] **DPL-045:** Kubernetesの基本的なコンポーネント（Pod, Deployment, Service）を説明できる。
- [ ] **DPL-046:** HelmやKustomizeなどのKubernetesパッケージ管理ツールの役割を説明できる。
- [ ] **DPL-047:** GitOpsの基本的な考え方を説明できる。
- [ ] **DPL-048:** Argo CDやFluxなどのGitOpsツールの名前を挙げられる。
- [ ] **DPL-049:** サーバープロビジョニングツール（Ansible, Chef, Puppet）の役割を説明できる。
- [ ] **DPL-050:** AWS CDKを使い、S3バケットを1つ作成するTypeScriptコードを記述する（ローカル完結）。
  <details>
  <summary>手を動かす</summary>
  - `cdk init app --language typescript` でプロジェクトを初期化する。
  - `lib/xxx-stack.ts` に、`new s3.Bucket(...)` のようにS3バケットを定義するコードを記述する。
  - `cdk synth` を実行し、生成されるCloudFormationテンプレートを確認する。
  </details>
