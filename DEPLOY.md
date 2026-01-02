# DRESS CODEs - デプロイ手順

## 必要なもの

1. GitHubアカウント
2. Vercelアカウント  
3. Anthropic APIキー

## デプロイ手順

### 1. GitHubリポジトリ作成

1. https://github.com/new にアクセス
2. Repository name: `dress-codes`
3. Public を選択
4. 「Create repository」をクリック

### 2. ファイルをアップロード

以下のファイルをGitHubリポジトリにアップロード:

```
dress-codes/
├── dress-codes.html      # メインHTML
├── butler.png            # 執事画像
├── api/
│   └── claude.js         # Serverless Function
└── vercel.json           # Vercel設定
```

**アップロード方法:**
1. GitHubリポジトリページで「uploading an existing file」をクリック
2. 上記4ファイルをドラッグ&ドロップ
3. 「Commit changes」をクリック

### 3. Vercelにデプロイ

1. https://vercel.com/signup にアクセス
2. 「Continue with GitHub」でログイン
3. 「New Project」をクリック
4. `dress-codes` リポジトリを選択
5. 「Import」をクリック

### 4. 環境変数を設定

**重要:** デプロイ前に環境変数を設定してください。

1. Vercelプロジェクト設定で「Settings」→「Environment Variables」
2. 以下を追加:

```
Name: ANTHROPIC_API_KEY
Value: (あなたのAnthropic APIキー)
```

3. 「Save」をクリック

### 5. デプロイ

1. 「Deploy」をクリック
2. デプロイ完了を待つ（1-2分）
3. 表示されるURLにアクセス

例: `https://dress-codes.vercel.app`

## Firebase設定（既に完了）

✅ Firebaseプロジェクト: `dress-codes-party`
✅ Firestore Database: 有効
✅ セキュリティルール: 設定済み

## トラブルシューティング

### API呼び出しが失敗する場合

1. Vercelの環境変数が設定されているか確認
2. `ANTHROPIC_API_KEY` が正しいか確認
3. Vercel Logs で詳細エラーを確認

### Firestoreエラーが出る場合

1. Firebaseプロジェクトが有効か確認
2. セキュリティルールが正しいか確認
3. ブラウザのコンソールでエラー詳細を確認

## 費用

- **Vercel**: 無料（Hobby tier）
- **Firebase**: 無料（Spark plan）
- **Anthropic API**: 使用量に応じて課金
- **Pexels API**: 完全無料

## サポート

問題が発生した場合は、Vercel Logsとブラウザのコンソールを確認してください。
