# 06. フロントエンド

---
## 6.1. JavaScript / TypeScript
- [ ] **FE-001:** `var`, `let`, `const`の違いを説明できる。
- [ ] **FE-002:** アロー関数の書き方と、`this`の束縛に関する違いを説明できる。
- [ ] **FE-003:** `map`, `filter`, `reduce`を使った配列操作ができる。
- [ ] **FE-004:** スプレッド構文（`...`）と分割代入の使い方を説明できる。
- [ ] **FE-005:** Promiseと`async/await`を使った非同期処理を記述できる。
- [ ] **FE-006:** モジュール（`import`/`export`）の仕組みを説明できる。
- [ ] **FE-007:** TypeScriptの基本的な型（`string`, `number`, `boolean`, `any`）を使える。
- [ ] **FE-008:** TypeScriptで`interface`と`type`を定義し、使い分けを説明できる。
- [ ] **FE-009:** TypeScriptのジェネリクスの基本的な使い方を説明できる。

---
## 6.2. React基礎
- [ ] **FE-010:** `State`と`Props`の違いを説明できる。
- [ ] **FE-011:** `useState`を使い、カウンターコンポーネントを作成できる。
- [ ] **FE-012:** Propsとコールバック関数を使い、親子コンポーネント間でデータを受け渡しできる。
- [ ] **FE-013:** `useEffect`が実行されるタイミング（依存配列の有無）を説明できる。
- [ ] **FE-014:** `useEffect`を使い、コンポーネントのマウント時にAPIをフェッチする処理を実装できる。
- [ ] **FE-015:** 条件付きレンダリング（`&&`や三項演算子）を記述できる。
- [ ] **FE-016:** `map`メソッドを使い、配列データをリスト形式でレンダリングできる（`key`属性の重要性も理解する）。
- [ ] **FE-017:** イベントハンドリング（`onClick`など）を実装できる。
- [ ] **FE-018:** 制御コンポーネントとして、入力フォームを作成できる。
- [ ] **FE-019:** カスタムフックを作成し、ロジックをコンポーネントから分離できる。
  <details>
  <summary>手を動かす</summary>
  - `useCounter`というカスタムフックを作成し、カウンターのロジック（カウント値、increment関数）をカプセル化する。
  </details>
- [ ] **FE-020:** React.memo, useCallback, useMemoの役割と、パフォーマンス最適化における使い分けを説明できる。

---
## 6.3. 状態管理
- [ ] **FE-021:** 状態管理のスコープ（ローカル vs グローバル）の使い分けを説明できる。
- [ ] **FE-022:** React Context APIを使い、シンプルなグローバル状態管理を実装できる。
- [ ] **FE-023:** Reduxの3つの原則（単一の情報源など）を説明できる。
- [ ] **FE-024:** Redux Toolkitを使い、簡単なカウンターストアを作成できる。
- [ ] **FE-025:** ZustandやJotaiなど、Redux以外の状態管理ライブラリを1つ以上、その特徴を説明できる。
- [ ] **FE-026:** SWRやReact Queryなどのサーバーキャッシュライブラリの役割を説明できる。

---
## 6.4. ルーティング・API通信
- [ ] **FE-027:** React Routerを使い、基本的なページ遷移を実装できる。
- [ ] **FE-028:** React Routerの動的ルーティング（`/users/:id`）を実装できる。
- [ ] **FE-029:** `fetch` APIと`async/await`を使い、APIからデータを取得して表示できる。
- [ ] **FE-030:** API通信における3つの状態（loading, success, error）を管理し、UIを出し分けできる。
- [ ] **FE-031:** AxiosなどのHTTPクライアントライブラリを使うメリットを説明できる。

---
## 6.5. UI・スタイリング
- [ ] **FE-032:** CSS in JS（Styled Components, Emotionなど）のメリットを説明できる。
- [ ] **FE-033:** CSS Modulesの仕組みとメリットを説明できる。
- [ ] **FE-034:** Tailwind CSSのようなユーティリティファーストCSSフレームワークの特徴を説明できる。
- [ ] **FE-035:** レスポンシブデザインの基本的な考え方（モバイルファースト）を説明できる。
- [ ] **FE-036:** メディアクエリ（`@media`）を使って、画面幅に応じたスタイルを記述できる。
- [ ] **FE-037:** Flexboxレイアウトの基本的なプロパティ（`display: flex`, `justify-content`など）を説明できる。
- [ ] **FE-038:** Gridレイアウトの基本的なプロパティ（`display: grid`, `grid-template-columns`など）を説明できる。
- [ ] **FE-039:** UIコンポーネントライブラリ（MUI, Chakra UIなど）を使うメリット・デメリットを説明できる。
- [ ] **FE-040:** StorybookやLadleを使い、コンポーネントをカタログ化する。
  <details>
  <summary>手を動かす</summary>
  - `Button`コンポーネントを作成し、`primary`と`secondary`の2つのバリエーションをStorybookで表示する。
  </details>

---
## 6.6. パフォーマンス・ビルド
- [ ] **FE-041:** ViteやWebpackなどのモジュールバンドラの役割を説明できる。
- [ ] **FE-042:** Lighthouseを使い、Webサイトのパフォーマンスを計測できる。
- [ ] **FE-043:** Core Web Vitals（LCP, FID, CLS）の各指標が何を表しているか説明できる。
- [ ] **FE-044:** 画像最適化（サイズ、フォーマット）の重要性を説明できる。
- [ ] **FE-045:** コード分割（Code Splitting）と遅延読み込み（Lazy Loading）の目的を説明できる。
- [ ] **FE-046:** `React.lazy`と`Suspense`を使ったコンポーネントの遅延読み込みを実装できる。

---
## 6.7. その他
- [ ] **FE-047:** パッケージマネージャ（npm, yarn, pnpm）のロックファイルの役割を説明できる。
- [ ] **FE-048:** ESLintとPrettierを使い、コードの静的解析とフォーマットを自動化する。
- [ ] **FE-049:** ブラウザのDevTools（Elements, Console, Networkパネル）の基本的な使い方を説明できる。
- [ ] **FE-050:** Webアクセシビリティ（a11y）の重要性と、`alt`属性などの基本的な実践方法を説明できる。
---
## 6.8. ブラウザとWeb API
- [ ] **FE-051:** DOMと仮想DOM（Virtual DOM）の違いを説明できる。
- [ ] **FE-052:** ブラウザのレンダリングプロセス（クリティカルレンダリングパス）の概要を説明できる。
- [ ] **FE-053:** Local Storage, Session Storage, Cookieの使い分けを説明できる。
- [ ] **FE-054:** Web Storage APIを使い、ブラウザにデータを保存・取得する。
- [ ] **FE-055:** Intersection Observer APIのユースケース（画像の遅延読み込みなど）を説明できる。
- [ ] **FE-056:** Web Workersを使い、重い処理をメインスレッドから分離する方法を説明できる。
- [ ] **FE-057:** Service Workerの役割（オフライン対応、プッシュ通知）を説明できる。
- [ ] **FE-058:** PWA（Progressive Web Apps）の基本的な概念を説明できる。

---
## 6.9. フレームワーク発展
- [ ] **FE-059:** Next.jsのレンダリング戦略（SSR, SSG, ISR）の違いを説明できる。
- [ ] **FE-060:** エラーバウンダリーの役割と実装方法を説明できる。
- [ ] **FE-061:** ReactのPortalsのユースケース（モーダルダイアログなど）を説明できる。
- [ ] **FE-062:** `useReducer`フックが`useState`と比べて適しているケースを説明できる。
- [ ] **FE-063:** debounceとthrottleの違いを説明できる。
- [ ] **FE-064:** 再レンダリングのパフォーマンスをReact DevToolsを使ってプロファイリングする。
- [ ] **FE-065:** TypeScriptでReactコンポーネントのPropsに型を付ける。
- [ ] **FE-066:** zodなどのライブラリを使い、フォームやAPIレスポンスのスキーマバリデーションを行う。
- [ ] **FE-067:** マイクロフロントエンドの基本的な考え方を説明できる。
- [ ] **FE-068:** WebAssembly（Wasm）がどのような課題を解決するか説明できる。

---
## 6.10. TypeScript/React 実践
- [ ] **FE-069:** zodを使い、APIレスポンスの型をランタイムで検証する型ガードを実装する。
- [ ] **FE-070:** `React.FC`を使わずにコンポーネントの型を定義するメリットを説明できる。
- [ ] **FE-071:** React Hook FormとZodを組み合わせて、型安全なフォームを作成する。
- [ ] **FE-072:** Storybookで、コンポーネントの様々な状態（`isLoading`, `error`など）を可視化する。
- [ ] **FE-073:** JestとReact Testing Libraryを使い、カスタムフックのテストを記述する。
- [ ] **FE-074:** MSW (Mock Service Worker) を導入し、ブラウザレベルでAPIをモックして開発する。
- [ ] **FE-075:** Next.jsのApp RouterとServer Componentsの基本的な概念を説明できる。
- [ ] **FE-076:** `server-only`と`client-only`パッケージの役割を説明できる。
- [ ] **FE-077:** Next.jsのRoute Handlersを使って、簡単なAPIエンドポイントを作成する。
- [ ] **FE-078:** VercelにNext.jsアプリケーションをデプロイする。
- [ ] **FE-079:** `useSWR`や`useQuery`のキャッシュキーの管理戦略を説明できる。
- [ ] **FE-080:** TanStack Table (React Table) を使って、ソート・フィルタ・ページネーション機能を持つテーブルを実装する。
- [ ] **FE-081:** dnd-kitやReact DnDを使って、ドラッグ&ドロップ機能を実装する。
- [ ] **FE-082:** RechartsやChart.jsを使い、簡単なグラフを描画する。
- [ ] **FE-083:** LighthouseのスコアをCI/CDプロセスに組み込む方法を調べる。
- [ ] **FE-084:** playwrightを使い、E2EテストをTypeScriptで記述する。
- [ ] **FE-085:** `React.Suspense`と非同期コンポーネントを組み合わせて、データ取得中のローディングUIを宣言的に実装する。
- [ ] **FE-086:** ValtioやJotaiのようなProxyベースの状態管理ライブラリの基本的な使い方を学ぶ。
- [ ] **FE-087:** TurborepoやNxを使ってモノレポを構築し、複数のアプリケーションやパッケージを管理する。
- [ ] **FE-088:** Chromaticを使い、UIコンポーネントのVisual Regression Testを自動化する。
- [ ] **FE-089:** shadcn/ui や Headless UI のような、より低レベルなUIコンポーネントライブラリの利点を説明できる。
- [ ] **FE-090:** `as`キーワードによる型キャストの代わりに、型ガード関数を実装する。
  <details>
  <summary>手を動かす</summary>
  - `animal.swim()` のようなコードを書くために、`isFish(animal): animal is Fish` のような、`is`キーワードを使ったユーザー定義型ガード関数を実装する。
  </details>
- [ ] **FE-091:** `satisfies`演算子のユースケースを説明できる。
- [ ] **FE-092:** TypeScriptの`tsconfig.json`における`strict: true`の重要性を説明できる。
- [ ] **FE-093:** tRPCの基本的な考え方と、REST/GraphQLとの違いを説明できる。
- [ ] **FE-094:** App Routerでの`fetch`のキャッシュと再検証（revalidate）の仕組みを説明できる。
- [ ] **FE-095:** Server Actionsの基本的な使い方を学ぶ。
- [ ] **FE-096:** `useOptimistic`フックを使って、楽観的UIを実装する。
- [ ] **FE-097:** Reactの`forwardRef`と`useImperativeHandle`のユースケースを説明できる。
- [ ] **FE-098:** Framer MotionやReact Springを使って、簡単なアニメーションを実装する。
- [ ] **FE-099:** Million.jsやBlock Virtual DOMのコンセプトを説明できる。
- [ ] **FE-100:** Vitestと`@testing-library/react`を使い、コンポーネントのスナップショットテストを記述する。
