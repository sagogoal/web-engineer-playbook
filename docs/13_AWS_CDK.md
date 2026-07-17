# 13. AWS CDK (Cloud Development Kit)

---
## 13.1. 基礎とセットアップ
- [ ] **CDK-001:** AWS CDKが解決する課題（IaCのプログラマビリティ向上）を説明できる。
- [ ] **CDK-002:** AWS CLIとNode.jsをインストールし、CDK Toolkitをセットアップする (`npm install -g aws-cdk`)。
- [ ] **CDK-003:** `cdk bootstrap`コマンドの役割と、実行時に作成されるリソースを説明できる。
- [ ] **CDK-004:** `cdk init app --language typescript` を実行し、新しいCDKプロジェクトを作成する。
- [ ] **CDK-005:** `cdk synth`コマンドを実行し、生成されるCloudFormationテンプレートを確認する。
- [ ] **CDK-006:** `cdk deploy`コマンドを実行し、リソースをデプロイする。
- [ ] **CDK-007:** `cdk diff`コマンドを使い、変更差分を確認する。
- [ ] **CDK-008:** `cdk destroy`コマンドを実行し、作成したスタックを削除する。
- [ ] **CDK-009:** CDKのApp, Stack, Constructの基本的な関係性を説明できる。

---
## 13.2. Constructの理解と利用
- [ ] **CDK-010:** L1, L2, L3 Constructの違いを説明できる。
- [ ] **CDK-011:** S3バケットを作成するL2 Construct (`s3.Bucket`) を使う。
  <details>
  <summary>手を動かす</summary>
  - `lib/xxx-stack.ts` に、`new s3.Bucket(...)` のようにS3バケットを定義するコードを記述し、デプロイする。
  </details>
- [ ] **CDK-012:** Constructのプロパティを使い、S3バケットのバージョニングを有効にする。
- [ ] **CDK-013:** `RemovalPolicy`の役割を説明し、`DESTROY`と`RETAIN`の違いを示す。
- [ ] **CDK-014:** `cdk-nag`を導入し、セキュリティやベストプラクティスに関する警告を検知する。
- [ ] **CDK-015:** Construct ID, 論理ID, 物理IDの違いを説明できる。
- [ ] **CDK-016:** `CfnOutput`を使い、デプロイしたリソースの情報（S3バケット名など）をCloudFormationの出力として表示する。

---
## 13.3. 実践的なリソース構築
- [ ] **CDK-017:** IAMロールとポリシー (`iam.Role`, `iam.PolicyStatement`) を作成し、特定のS3バケットへの読み取りアクセスを許可する。
- [ ] **CDK-018:** VPC (`ec2.Vpc`) を作成し、パブリックサブネットとプライベートサブネットを定義する。
- [ ] **CDK-019:** Lambda関数 (`lambda.Function`) を作成し、簡単な"Hello World"を返すコードをデプロイする。
- [ ] **CDK-020:** Lambda関数に、先ほど作成したIAMロールをアタッチする。
- [ ] **CDK-021:** API Gateway (`apigateway.RestApi`) とLambdaを連携させ、単一のエンドポイントを持つAPIを作成する。
- [ ] **CDK-022:** DynamoDBテーブル (`dynamodb.Table`) を作成し、パーティションキーとソートキーを定義する。
- [ ] **CDK-023:** Lambda関数からDynamoDBテーブルを読み書きするためのIAM権限を付与し、実際にデータを操作するコードを記述する。
  <details>
  <summary>手を動かす</summary>
  - API Gateway経由でPOSTされたデータをLambdaが受け取りDynamoDBに保存する、という一連の流れを実装する。
  </details>
- [ ] **CDK-024:** S3イベント通知を使い、ファイルがアップロードされたらLambda関数が起動する仕組みを実装する。
- [ ] **CDK-025:** EventBridge (CloudWatch Events) を使い、定期的（例: 5分ごと）にLambda関数を実行するルールを作成する。
- [ ] **CDK-026:** SQSキュー (`sqs.Queue`) を作成し、非同期処理のキューとして利用する。

---
## 13.4. 複数スタックとパラメータ管理
- [ ] **CDK-027:** 1つのCDKアプリ内に、本番用(Prod)と開発用(Dev)の2つのスタックを定義する。
- [ ] **CDK-028:** スタック間でリソースを参照（クロススタック参照）する方法を説明できる。
- [ ] **CDK-029:** `cdk.context.json`の役割を説明し、環境ごとの設定値（VPC IDなど）を管理する。
- [ ] **CDK-030:** 環境変数や`--context`オプションを使って、CDKコードに外部から値を渡す。
- [ ] **CDK-031:** SSM パラメータストアやSecrets Managerから設定値を取得し、CDKコード内で利用する。

---
## 13.5. カスタムConstructとテスト
- [ ] **CDK-032:** 複数のリソースをまとめた、独自のL3 Construct（例: `WebsiteHostingConstruct`）を作成する。
- [ ] **CDK-033:** Jestを使い、CDKスタックのスナップショットテストを記述する。
- [ ] **CDK-034:** `aws-cdk-lib/assertions`モジュールの`Template.fromStack`と`hasResourceProperties`を使い、特定のリソースが意図したプロパティで作成されているかをテストする。
  <details>
  <summary>手を動かす</summary>
  - S3バケットが暗号化されているか、バージョニングが有効になっているかをアサーションでテストする。
  </details>
- [ ] **CDK-035:** Fine-grained assertionsを使い、より詳細なテストを記述する。

---
## 13.6. CI/CDとパイプライン
- [ ] **CDK-036:** `aws-cdk-lib/pipelines`モジュール (CDK Pipelines) の役割を説明できる。
- [ ] **CDK-037:** GitHub ActionsからCDKのデプロイを行うためのIAMロール（OIDCプロバイダー利用）を設定する。
- [ ] **CDK-038:** GitHubリポジトリへのpushをトリガーに、`cdk diff`と`cdk deploy`を自動実行するGitHub Actionsのワークフローを記述する。
- [ ] **CDK-039:** CDK Pipelinesを使い、自己更新機能を持つCI/CDパイプライン（CodePipeline）をCDKで定義する。
- [ ] **CDK-040:** パイプラインに手動承認ステージを追加する。

---
## 13.7. 発展・応用課題
- [ ] **CDK-041:** CloudFrontディストリビューション (`cloudfront.Distribution`) を作成し、S3バケットをオリジンとして静的サイトをホスティングする。
- [ ] **CDK-042:** ACM (`certificatemanager.Certificate`) を使い、CloudFrontにカスタムドメインとSSL/TLS証明書を設定する。
- [ ] **CDK-043:** ECS Fargateサービス (`ecs.FargateService`) とALB (`elbv2.ApplicationLoadBalancer`) を使い、Dockerコンテナをデプロイする。
- [ ] **CDK-044:** ECR (`ecr.Repository`) にDockerイメージをプッシュし、そのイメージをFargateサービスで利用する。
- [ ] **CDK-045:** Cognito User Pool (`cognito.UserPool`) を作成し、API Gatewayのオーソライザーと連携させる。
- [ ] **CDK-046:** Aspectsの機能を使って、スタック内のすべてのS3バケットに特定のタグを自動的に付与する。
- [ ] **CDK-047:** AWS SDKをCDKコード内で使い、外部リソースの情報（最新のAMI IDなど）を取得して利用する。
- [ ] **CDK-048:** Lambdaのコンテナイメージサポートを使い、コンテナとしてビルドした関数をデプロイする。
- [ ] **CDK-049:** `CfnResource` (L1 Construct) を直接使い、L2 Constructがまだ提供されていない新しいAWSリソースを定義する。
- [ ] **CDK-050:** CDK for Terraform (CDKTF) や CDK for Kubernetes (CDK8s) とAWS CDKとの違いを説明できる。
