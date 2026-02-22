# GitHub Pages デプロイ手順

## 1. リポジトリ作成
1. https://github.com/new にアクセス
2. Repository name: `hearing`（任意）
3. **Private** を選択（社内ツールのため）
4. 「Create repository」

## 2. ファイルをアップロード
リポジトリ画面で「Add file」→「Upload files」で以下をドラッグ＆ドロップ：

```
index.html   ← メインファイル
README.md    ← リポジトリ説明
```

「Add file」→「Create new file」で以下を作成（中身は空でOK）：
```
.nojekyll    ← GitHub Pagesビルドスキップ用
```

## 3. GitHub Pages を有効化
1. リポジトリの **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` / `/ (root)` を選択 →「Save」
4. 数分後に公開：`https://[ユーザー名].github.io/hearing/`

## 4. 注意事項
- **Private リポジトリ** で GitHub Pages を使うには **GitHub Pro / Team / Enterprise** プランが必要
- 無料プランの場合は Public にするか、Cloudflare Pages 等を検討
- 将来の会員制化を見据えるなら Cloudflare Pages + Workers が拡張しやすい

## 運用フロー
```
社員がURLにアクセス
  ↓
ヒアリング記入（ブラウザ上で自動保存）
  ↓
「HTML保存」→ データ入りファイルをローカル保存
  ↓
「御見積書を印刷」→ PDF化してクライアントに提出
  ↓
案件フォルダ（Googleドライブ等）に保存
```

## 更新時
index.html を差し替えて push → 全社員に即反映

## 将来の拡張メモ
- コーポレートサイトからリンク → iframe または直リンク
- 会員制 → Cloudflare Access / Firebase Auth 等
- データ共有 → Supabase / Firebase でクラウド保存化
