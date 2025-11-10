# GitHub Pages セットアップ手順

## 1. GitHubリポジトリの作成

1. [GitHub](https://github.com)にログイン
2. 右上の「+」→「New repository」をクリック
3. リポジトリ名を入力（例: `obake`）
4. 「Public」を選択（GitHub Pagesは無料プランでPublicリポジトリのみ）
5. 「Initialize this repository with a README」は**チェックしない**（既にファイルがあるため）
6. 「Create repository」をクリック

## 2. ローカルでGitリポジトリを初期化してpush

ターミナルで以下のコマンドを実行：

```bash
# プロジェクトディレクトリに移動
cd /Users/kojimakenji/Projects/obake

# Gitリポジトリを初期化（まだの場合）
git init

# すべてのファイルをステージング
git add .

# 初回コミット
git commit -m "Initial commit: AR画像表示アプリ"

# GitHubリポジトリをリモートとして追加
# YOUR_USERNAME と YOUR_REPO_NAME を実際の値に置き換えてください
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git

# メインブランチを設定（GitHubのデフォルトに合わせる）
git branch -M main

# GitHubにpush
git push -u origin main
```

## 3. GitHub Pagesを有効化

1. GitHubリポジトリのページで「Settings」タブをクリック
2. 左サイドバーの「Pages」をクリック
3. 「Source」セクションで：
   - 「Deploy from a branch」を選択
   - 「Branch」で「main」を選択
   - 「/ (root)」を選択
4. 「Save」をクリック

## 4. アクセスURLの確認

数分待つと、以下のURLでアクセスできます：
```
https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/
```

例: `https://kojimakenji.github.io/obake/`

## 5. 確認方法

1. 上記のURLにアクセス
2. カメラのアクセス許可を許可
3. `armarker.png`を別のデバイスや印刷物で表示
4. カメラをマーカーに向けると`obake01.png`が表示される

## 注意事項

- GitHub PagesはHTTPSで提供されるため、カメラアクセスが正常に動作します
- 初回デプロイには数分かかる場合があります
- ファイルを更新した場合は、再度`git push`すると自動的に反映されます

## トラブルシューティング

### 404エラーが出る場合
- 数分待ってから再度アクセス
- GitHubリポジトリのSettings > Pagesでデプロイ状況を確認

### カメラが起動しない場合
- HTTPSでアクセスしているか確認（HTTPではカメラアクセスが制限されます）
- ブラウザの設定でカメラのアクセス許可を確認

