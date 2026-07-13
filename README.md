# 教育OS 副担任mirAI NEXT

![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)
![Vite](https://img.shields.io/badge/build-Vite%205-646CFF)
![React](https://img.shields.io/badge/React-18-61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6)
![Single File](https://img.shields.io/badge/build-single%20HTML-success)

NOLTYプランナーズの既存サービス「副担任mirAI／未来」のUIを土台に、**mirAI Curriculum** / **Dify RAG** / **Supabase** / **n8n** / **副担任mirAI API** を統合した完成形デモアプリ。

> ⚠️ 本アプリは**プロトタイプ**であり、本番サービスではありません。Dify / Supabase / n8n / 副担任mirAI API は **mock 接続**で動作します。個人情報は**保持しないデモ**（生徒は匿名IDで管理）。

---

## ✨ NEXT 2.0 強化ポイント(このリリースの新機能)

体感価値・直感操作・安心のすべてを底上げした **教育OS強化版** です。

### 🎓 直感で使える(体感価値)

- **ロール別オンボーディングツアー**: 初回ログイン時に、生徒・教員・企業・管理者・制作委員それぞれに最適化された使い方ツアーを自動表示。各ステップから該当画面へワンクリック遷移。ヘッダーの「使い方ツアー」からいつでも再表示できます。
- **クイックヘルプ(画面右下の「?」)**: ツアー再表示・データ取扱い確認・デモ初期化・ロール別ワンポイントTIPS・満足度フィードバックをワンストップで。

### 🛡 安心が見える(トラストセンター)

- **トラストセンター(全ロール共通・生徒版は「あんしんガイド」)**: 「個人情報を持たない設計」「人が最終承認」「すべての操作が追跡可能」の3つの約束を可視化。
- **データ取扱いフロー図**: 記録→AI分析→人による確認→進路指導活用の各ステップと安全装置を明示。
- **監査ログビューア(デモ)**: AI生成・レビュー・公開・データ連携・アクセスの操作記録を種別フィルタ+CSVエクスポート付きで公開。不適切処理の自動ブロックも記録。
- **保護者・生徒・教員・企業それぞれの不安に答えるFAQ**。
- **ログイン画面に安心バッジ**: 「個人情報を保持しない / 人による二重レビュー / 外部送信ゼロ」を体験前に明示。

### 📊 現場で役立つ(AIインサイト)

- **教員向け AI週次サマリー**: クラスごとに「良い変化」「気になるサイン」「AIからの提案」を要約。クラス切替対応。
- **要ケア生徒アラート**: 進捗停滞・関心低下などのシグナルを匿名IDベースで検知し、評価ではなく「声かけのきっかけ」として推奨アクションを提示。
- **今週のおすすめアクション**: 効果測定・進路指導・ライブラリーへの実行導線付き。
- **企業向け 効果レポート**: 導入校数・受講者数・完了率・受講前後の関心変化グラフ・現場の声を可視化。CSVダウンロードで社内報告にそのまま使えます。
- **生徒向け 学習ハイライト**: 連続学習ストリーク・週間学習時間・関心の伸び・バッジコレクション・次のおすすめ教材。

---

## 🎬 デモを見る（4つの方法）

このプロジェクトは **`docs/index.html` と `mirai-next-demo-standalone.html` が同一内容の単一HTMLファイル** です（約5MB）。JS / CSS / 画像はインライン化済みで、サーバー不要で動作します。

### 🅐 方法A: ダブルクリックで即体験（最も簡単）

`docs/index.html` / `docs/mirai-next-demo-standalone.html` / `mirai-next-demo-standalone.html` を **ブラウザで直接開くだけ** でデモが起動します。

```
docs/index.html  ←ダブルクリック
docs/mirai-next-demo-standalone.html  ←配布向け別名
mirai-next-demo-standalone.html  ←単体配布向け
```

追加ソフト・サーバー・ネット接続、すべて不要。ローカルで完全動作します。

### 🅑 方法B: GitHub Pages で公開する

GitHub にプッシュして、以下の 3 ステップで公開します。

#### ステップ1. リポジトリ作成 & push

```bash
git init
git add .
git commit -m "chore: initial commit"
git branch -M main
git remote add origin https://github.com/<username>/<repo>.git
git push -u origin main
```

> 💡 リポジトリ名はなんでも OK です（大文字・小文字混じり `mirAI_NEXT` 等でも動作）。

#### ステップ2. GitHub Pages を有効化

GitHub のリポジトリ画面で:

```
Settings  →  Pages  →  Build and deployment

  Source :  Deploy from a branch    ← ★ 必ずこちら ★
  Branch :  main  ▼   /   /docs  ▼
                                    [Save]
```

**重要**: **Source は「GitHub Actions」ではなく必ず「Deploy from a branch」を選択** してください。ブランチは `main`、フォルダは `/docs` です。

> 💡 GitHub Pages の入口は `index.html` です。添付HTMLを単体で置くだけではトップページにならないため、本パッケージでは **公開用の `docs/index.html` を同梱** しています。

#### ステップ3. アクセス

1〜3分待つと、以下のURLで公開されます:

```
https://<username>.github.io/<repo>/
```

### 🅒 方法C: 開発モードで起動（コード修正する場合）

```bash
npm install
npm run dev
```

http://localhost:5173/ が起動します。ソース修正のホットリロード付き。

### 🅓 方法D: GitHub公開用zipを一括生成する

```bash
npm install
npm run release:github
```

生成物:

```
docs/mirai-next-demo-standalone.html
release/mirai-next-github-release/mirai-next-source-package.zip
release/mirai-next-github-release/
release/mirai-next-github-release.zip
```

`release/mirai-next-github-release/` は **GitHubの100ファイル制限を超えない公開用構成** です。

- `docs/` : GitHub Pages 公開に必要なファイルのみ
- `mirai-next-demo-standalone.html` : 単体配布用
- `mirai-next-source-package.zip` : `src/` や `public/` など開発用ソース一式を1ファイルに圧縮
- `README.md` / `LICENSE` : 公開に必要な説明ファイル

このため、GitHubへブラウザアップロードする場合も **100ファイル未満** で扱えます。

---

## 🎯 デモの体験フロー

ログイン画面で、認証情報なしでボタンをクリックするだけでログインできます。

### 👨‍🎓 生徒モード
1. **ホーム**: 17軸の関心レーダー、受講中カリキュラム、AI進路ナビへの導線
2. **AI進路ナビ**: Dify(mock) との対話で興味関心を整理
3. **カリキュラムライブラリー**: フィルタで気になる授業を探す
4. **キャリアデザイン**: 業種/教科/やってみたい仕事の登録
5. **受講進捗**: 完了率・関心変化・ルーブリック評価の可視化
6. **学習ハイライト** 🆕: ストリーク・バッジ・次のおすすめ
7. **あんしんガイド** 🆕: 自分のデータがどう守られるかを確認

### 👨‍🏫 教員モード
1. **ホーム**: 担当クラスの進捗・興味関心・適性の可視化
2. **mirAI Curriculum生成**: 企業素材から Dify Workflow で授業自動生成
3. **教員チューニング**: セクション単位の編集、差分表示、クイック変換
4. **制作委員会レビュー**: 生成不可条件チェック → 承認 → ライブラリー公開
5. **受講・効果測定**: クラス別完了率、関心変化、ルーブリック平均
6. **進路指導反映**: 受講後データを副担任mirAI API(mock)へ同期
7. **他校トレンド・事例**: 全国の導入事例
8. **データ連携 / API Hub**: システム図、n8n フロー、API イベントログ
9. **AIインサイト** 🆕: AI週次サマリー・要ケア生徒アラート・おすすめアクション
10. **トラストセンター** 🆕: データ取扱い・監査ログ・FAQ

### 🏢 企業モード
1. **ホーム**: 自社素材 → AI 教材化パイプライン、自社公開カリキュラム
2. **自社コンテンツ素材**: 素材アップロード・管理
3. **カリキュラム自動生成**: 自社素材 → 指導要領適合カリキュラム化
4. **公開ライブラリー**: 他社事例参照
5. **他社事例・トレンド**: 全国トレンド・人気カリキュラム
6. **効果レポート** 🆕: 導入校数・関心変化・現場の声・CSV出力

### 🎛 管理者モード / 制作委員会モード
- 教員機能全部 + 制作委員会レビュー機能

---

## ⚠️ よくある失敗パターン

### 公開URLにアクセスしたら真っ白

**Settings → Pages → Source が `Deploy from a branch`** になっていて、**Branch が `main` / `/docs`** に設定されているか確認してください。

`Source: GitHub Actions` を選ぶと、事前ビルド済みの `docs/` は使われず、リポジトリの生ソース `index.html` が配信されて真っ白になります。

### `index.html`（ルート直下）をダブルクリックしても動かない

**ルート直下の `index.html`** は Vite 開発サーバー専用です。**`docs/index.html`** を代わりに開いてください。

---

## サービス概要

```
企業コンテンツ
   ↓ (Dify Workflow + 学習指導要領 RAG)
mirAI Curriculum
   ↓ (教員チューニング: セクション単位編集)
カリキュラム制作委員会レビュー (生成不可条件チェック)
   ↓ (n8n 自動連携)
カリキュラムライブラリーへ公開
   ↓
教員が授業に活用 / 生徒が受講
   ↓ (Supabase に受講ログ保存)
効果測定 / ルーブリック評価
   ↓ (副担任mirAI API 同期)
進路指導 / キャリアデザインに反映
   ↺ (Data Loop)
```

---

## 技術スタック

| カテゴリ | 採用技術 |
| --- | --- |
| ビルドツール | Vite 5 + vite-plugin-singlefile（単一HTML化） |
| フレームワーク | React 18 + TypeScript |
| ルーティング | React Router (HashRouter) |
| スタイル | Tailwind CSS |
| アイコン | lucide-react |
| グラフ | recharts (Radar / Bar / Line) |
| 状態保存 | localStorage (Supabase代替) |
| 配布形式 | 単一HTMLファイル（画像もbase64インライン化）|

---

## npm スクリプト一覧

| コマンド | 用途 |
| --- | --- |
| `npm install` | 依存パッケージのインストール |
| `npm run dev` | 開発サーバー起動（ホットリロード付き） |
| `npm run build` | 本番ビルド → `docs/index.html`（単一HTML）に出力 |
| `npm run package:github` | GitHub公開用の軽量構成を生成し、100ファイル未満かを検証 |
| `npm run release:github` | build + GitHub 公開用 zip 生成を一括実行 |
| `npm run demo` | `docs/` をローカルサーバーで配信 |
| `npm run preview` | Vite の preview サーバー |
| `npm run lint` | TypeScript 型チェック |

---

## 環境変数（オプション）

`.env.example` を `.env.local` にコピーして編集してください。すべて未設定でも mock adapter で動作します。

| 変数 | 用途 | 未設定時の挙動 |
| --- | --- | --- |
| `VITE_BASE_PATH` | ビルド時の base URL | `./`（相対パス、どこでも動く） |
| `VITE_OUT_DIR` | ビルド出力先 | `docs` |
| `VITE_DIFY_ENDPOINT` | Dify Workflow エンドポイント | mock 生成 |
| `VITE_DIFY_API_KEY` | Dify API キー | mock |
| `VITE_SUPABASE_URL` | Supabase プロジェクトURL | localStorage |
| `VITE_SUPABASE_ANON_KEY` | Supabase 匿名キー | localStorage |
| `VITE_N8N_WEBHOOK_URL` | n8n Webhook URL | mock |
| `VITE_MIRAI_API_BASE` | 副担任mirAI API ベースURL | mock |
| `VITE_MIRAI_API_KEY` | 副担任mirAI API キー | mock |

**APIキーやトークンは絶対にコードへ直書きしないでください。**

---

## 外部サービス連携の将来設計

### Dify

`src/services/difyAdapter.ts` を Dify Workflow Run API に置き換え。

**役割**: カリキュラム生成 Workflow / RAG 知識ベース参照 / 生成不可条件チェック / 進路指導コメント生成

### Supabase

`src/services/supabaseAdapter.ts` を `@supabase/supabase-js` ベースに置き換え。

**保存するテーブル（RLS推奨）**: `schools` / `users` / `classes` / `students` / `career_profiles` / `curriculum_items` / `curriculum_versions` / `assignments` / `learning_records` / `rubric_scores` / `api_events` / `approvals`

### n8n

`src/services/n8nAdapter.ts` を n8n Webhook 呼び出しに置き換え。

### 副担任mirAI API

`src/services/miraiApiAdapter.ts` を本番APIに置き換え。

**役割**: 生徒キャリア情報の取得 / 反映、受講後データの返却、進路指導コメントの反映、面談準備情報の更新

---

## ディレクトリ構成

```
mirai-next/
├── .github/
│   └── workflows/deploy.yml   # GitHub Actions（オプション）
├── index.html                 # ルート用の軽量リダイレクト（docs/ へ誘導）
├── favicon.svg                # ルート直下HTML向け favicon
├── docs/                      # ★ GitHub Pages 公開用（同梱・コミット対象）
│   ├── index.html             # GitHub Pages の入口
│   ├── mirai-next-demo-standalone.html
│   ├── .nojekyll              # Jekyll 無効化
│   └── favicon.svg
├── public/
│   ├── images/                # 開発時のみ利用（本番はsrc/assets/使用）
│   └── favicon.svg
├── src/
│   ├── assets/images/         # ★ 本番ビルドはここから base64 インライン化
│   ├── components/            # Layout, Sidebar, TopBar, Badges, PageHeader,
│   │                          #   OnboardingTour 🆕, QuickHelp 🆕
│   ├── context/               # AuthContext, AppContext
│   ├── data/                  # mockData, careerAxes, insightsData 🆕, trustData 🆕
│   ├── pages/                 # 全画面コンポーネント（TrustPage 🆕, InsightsPage 🆕 含む）
│   ├── services/              # adapter層 (Dify/Supabase/n8n/mirAI mock)
│   ├── types/
│   ├── utils/assetUrl.ts      # 画像 import → base64 変換辞書
│   ├── App.tsx
│   ├── main.tsx
│   └── index.css
├── serve-docs.mjs             # ローカルサーバー (npm run demo)
├── .env.example
├── .gitignore
├── LICENSE
├── vite.config.ts             # vite-plugin-singlefile 設定
├── tailwind.config.js
├── tsconfig.json
└── package.json
```

---

## セキュリティ方針

- **APIキー・トークンの直書き禁止**：すべて `.env.local` で管理
- **`.env.local` は `.gitignore` 対象**：誤コミット防止
- **個人情報を持たないデモ**：生徒は匿名IDで管理
- **生成不可条件チェック**：Dify RAG + 制作委員会レビューの二重防御
- **トラストセンター搭載** 🆕：データ取扱いフロー・監査ログ(デモ)・FAQをアプリ内で常時公開

---

## ライセンス・クレジット

- 本プロトタイプは NOLTYプランナーズ「副担任mirAI」の世界観をデモンストレーションする目的で作成されました
- 画像・イラストは AI 生成（プロトタイプ用）
- アイコン: lucide-react (ISC)
- 本コードは MIT License

---

**©︎ NOLTYプランナーズ / 副担任mirAI NEXT プロトタイプ**
