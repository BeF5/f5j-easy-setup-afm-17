# F５ Advanced AFM かんたんセットアップガイド v17.5
https://f5j-easy-setup-afm-17.readthedocs.io/ja/latest/

日々更新中

## 構成
Readthedocs というOSSを利用。
https://docs.readthedocs.com/platform/stable/index.html

- Read the Docs は、Git（GitHub や GitLab など）に push されたタイミングで自動的にドキュメントをビルド・ホストしてくれるサービスです。
- 複数バージョンのドキュメント（v1, v2 など）をまとめて公開できます。
- コミュニティ版はオープンソースプロジェクト向けに無料でホスティングしていて、サービス自体もオープンソースとして公開されています。
- 企業向けには「Read the Docs for Business」という有償版もあります。
- main ブランチに Commit すると自動でデプロイされます。

## ローカル環境でのドキュメント確認

### 前提条件

- macOS
- Homebrew
- pyenv

### 初回セットアップ
```bash
# pyenv で Python 3.11 をインストール（未インストールの場合）
brew install pyenv
echo 'eval "$(pyenv init -)"' >> ~/.zshrc
source ~/.zshrc
pyenv install 3.11

# プロジェクトディレクトリで Python 3.11 を指定
pyenv local 3.11

# 仮想環境を作成
## venv は Python 専用の隔離ツール。他の言語やシステムパッケージは対象外です。
python -m venv .venv
source .venv/bin/activate

# 依存パッケージをインストール
## pip はPython 専用のパッケージ管理ツール
pip install -r docs/requirements.txt
pip install sphinx-autobuild
```

### ドキュメントのプレビュー
```bash
source .venv/bin/activate
cd docs
sphinx-autobuild . _build/html
```

http://127.0.0.1:8000 でプレビューできます。
ファイルを保存すると自動でリビルド・リロードされます。

### 終了
```bash
# Ctrl+C でサーバー停止
deactivate
```

### （オプション）direnv で自動 activate
```bash
brew install direnv
echo 'eval "$(direnv hook zsh)"' >> ~/.zshrc
source ~/.zshrc

# プロジェクトルートで
echo "source .venv/bin/activate" > .envrc
direnv allow
```

以降はディレクトリに入ると自動で仮想環境が有効になります。