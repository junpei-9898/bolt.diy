# bolt.diy (旧 oTToDev)
[![bolt.diy: ブラウザ上でAI駆動のフルスタックWeb開発](./public/social_preview_index.jpg)](https://bolt.diy)

bolt.diyへようこそ。これはBolt.new（以前はoTToDevやbolt.new ANY LLMとして知られていた）の公式オープンソースバージョンで、各プロンプトで使用するLLMを選択できます！現在、OpenAI、Anthropic、Ollama、OpenRouter、Gemini、LMStudio、Mistral、xAI、HuggingFace、DeepSeek、Groqのモデルを使用でき、Vercel AI SDKでサポートされている他のモデルにも簡単に拡張できます！ローカルでの実行方法や、より多くのモデルを追加する方法については、以下の説明をご覧ください。

詳細については[bolt.diy ドキュメント](https://stackblitz-labs.github.io/bolt.diy/)をご確認ください。

また、bolt.diyに関する一般的な質問に答えることができる実験的なエージェント「bolt.diy Expert」を[oTTomator Live Agent Studio](https://studio.ottomator.ai/)で公開しています。

bolt.diyは元々[Cole Medin](https://www.youtube.com/@ColeMedin)によって開始されましたが、最高のオープンソースAIコーディングアシスタントを構築するための大規模なコミュニティの取り組みへと急速に成長しました！

## 目次

- [コミュニティに参加](#コミュニティに参加)
- [要望された追加機能](#要望された追加機能)
- [機能](#機能)
- [セットアップ](#セットアップ)
- [アプリケーションの実行](#アプリケーションの実行)
- [利用可能なスクリプト](#利用可能なスクリプト)
- [貢献方法](#貢献方法)
- [ロードマップ](#ロードマップ)
- [FAQ](#faq)

## コミュニティに参加

[ottomator.aiのthinktankでbolt.diyコミュニティに参加しましょう！](https://thinktank.ottomator.ai)

## 要望された追加機能

- ✅ OpenRouter統合 (@coleam00)
- ✅ Gemini統合 (@jonathands)
- ✅ ダウンロード済みOllamaモデルの自動生成 (@yunatamos)
- ✅ プロバイダーによるモデルのフィルタリング (@jasonm23)
- ✅ プロジェクトをZIPとしてダウンロード (@fabwaseem)
- ✅ `app\lib\.server\llm\prompts.ts`のbolt.newプロンプトの改善 (@kofi-bhr)
- ✅ DeepSeek API統合 (@zenith110)
- ✅ Mistral API統合 (@ArulGandhi)
- ✅ "Open AI Like" API統合 (@ZerxZ)
- ✅ ローカルフォルダへのファイル同期（一方向同期） (@muzafferkadir)
- ✅ 簡単なインストールのためのDockerコンテナ化 (@aaronbolton)
- ✅ GitHubへの直接プロジェクト公開 (@goncaloalves)
- ✅ UI上でのAPIキー入力機能 (@ali00209)
- ✅ xAI Grok Beta統合 (@milutinke)
- ✅ LM Studio統合 (@karrot0)
- ✅ HuggingFace統合 (@ahsan3219)
- ✅ LLMコマンド出力を表示するBoltターミナル (@thecodacus)
- ✅ コード出力のストリーミング (@thecodacus)
- ✅ 以前のバージョンへのコード復元機能 (@wonderwhy-er)
- ✅ Cohere統合 (@hasanraiyan)
- ✅ 動的なモデル最大トークン長 (@hasanraiyan)
- ✅ プロンプト強化の改善 (@SujalXplores)
- ✅ プロンプトのキャッシング (@SujalXplores)
- ✅ ローカルプロジェクトのアプリへの読み込み (@wonderwhy-er)
- ✅ Together統合 (@mouimet-infinisoft)
- ✅ モバイル対応 (@qwikode)
- ✅ プロンプト強化の改善 (@SujalXplores)
- ✅ プロンプトへの画像添付 (@atrokhym)
- ✅ Gitクローンボタンの追加 (@thecodacus)
- ✅ URLからのGitインポート (@thecodacus)
- ✅ 様々なユースケース用のプロンプトバリエーション (@thecodacus)
- ✅ フォルダーとGitインポート用のpackage.jsonとコマンドの自動検出 (@wonderwhy-er)
- ✅ 変更を視覚的にターゲットにする選択ツール (@emcconnell)
- ✅ ターミナルエラーの検出とboltによる修正 (@thecodacus)
- ✅ プレビューエラーの検出とboltによる修正 (@wonderwhy-er)
- ✅ スターターテンプレートオプションの追加 (@thecodacus)
- ⬜ **高優先度** - ファイルの頻繁な書き換えを防止（ファイルロックと差分）
- ⬜ **高優先度** - 小規模LLM向けのより良いプロンプト（コードウィンドウが時々開始しない）
- ⬜ **高優先度** - 単一のモデル呼び出しではなくバックエンドでのエージェント実行
- ⬜ Vercel/Netlify/その他類似プラットフォームへの直接デプロイ
- ⬜ より良い結果/透明性のためのMDファイルでのLLMプロジェクト計画
- ⬜ git風の確認を伴うVSCode統合
- ⬜ 知識のためのドキュメントアップロード - UIデザインテンプレート、コーディングスタイル参照用のコードベースなど
- ⬜ 音声プロンプト
- ⬜ Azure Open AI API統合
- ✅ Perplexity統合 (@meetpateltech)
- ⬜ Vertex AI統合

## 機能

- ブラウザ上で直接**AI駆動のフルスタックWeb開発**
- 追加モデルを統合できる拡張可能なアーキテクチャによる**複数のLLMのサポート**
- より良い文脈理解のための**プロンプトへの画像添付**
- LLM実行コマンドの出力を表示する**統合ターミナル**
- デバッグと迅速な変更のための**以前のバージョンへのコード復元**
- 簡単な移植性のための**プロジェクトのZIPダウンロード**
- 手間のないセットアップのための**統合準備済みのDockerサポート**

## セットアップ

GitHubからソフトウェアをインストールするのが初めての方でも心配いりません！問題が発生した場合は、提供されているリンクを使用して「issue」を提出するか、リポジトリをフォークし、説明を編集してプルリクエストを提出することで、このドキュメントを改善できます。以下の手順で、安定版のBolt.DIYをローカルマシンで迅速に実行できます。

## クイックダウンロード

[![最新リリースをダウンロード](https://img.shields.io/github/v/release/stackblitz-labs/bolt.diy?label=Download%20Bolt&sort=semver)](https://github.com/stackblitz-labs/bolt.diy/releases/latest) ← クリックして最新リリースバージョンに移動！

- 次に**source.zip**をクリックしてください


## 前提条件

開始する前に、2つの重要なソフトウェアをインストールする必要があります：

### Node.jsのインストール

アプリケーションの実行にはNode.jsが必要です。

1. [Node.jsダウンロードページ](https://nodejs.org/en/download/)にアクセス
2. お使いのOSに合わせて「LTS」（Long Term Support）バージョンをダウンロード
3. インストーラーを実行し、デフォルト設定を受け入れる
4. Node.jsが正しくインストールされたことを確認：
   - **Windowsユーザーの場合**：
     1. `Windows + R`キーを押す
     2. "sysdm.cpl"と入力してEnterを押す
     3. 「詳細設定」タブ→「環境変数」に移動
     4. 「Path」変数に`Node.js`が表示されているか確認
   - **Mac/Linuxユーザーの場合**：
     1. ターミナルを開く
     2. 以下のコマンドを入力：
        ```bash
        echo $PATH
        ```
     3. 出力に`/usr/local/bin`が含まれているか確認

## アプリケーションの実行

Bolt.DIYの実行には2つの選択肢があります：直接マシン上で実行するか、Dockerを使用するか。

### オプション1：直接インストール（初心者向け推奨）

1. **パッケージマネージャー（pnpm）のインストール**：
   ```bash
   npm install -g pnpm
   ```

2. **プロジェクトの依存関係をインストール**：
   ```bash
   pnpm install
   ```

3. **アプリケーションの起動**：
   ```bash
   pnpm run dev
   ```

   **重要な注意**: Google Chromeを使用している場合、ローカル開発にはChrome Canaryが必要です。[ここからダウンロード](https://www.google.com/chrome/canary/)

### オプション2：Dockerの使用

このオプションにはDockerの基本的な知識が必要ですが、より分離された環境を提供します。

#### 追加の前提条件
- Dockerのインストール：[Dockerのダウンロード](https://www.docker.com/)

#### 手順：

1. **Dockerイメージのビルド**：
   ```bash
   # npmスクリプトを使用：
   npm run dockerbuild

   # または直接Dockerコマンドを使用：
   docker build . --target bolt-ai-development
   ```

2. **コンテナの実行**：
   ```bash
   docker-compose --profile development up
   ```




## APIキーとプロバイダーの設定

### APIキーの追加

Bolt.DIYでのAPIキーの設定は簡単です：

1. ホームページ（メインインターフェース）を開く
2. ドロップダウンメニューから希望のプロバイダーを選択
3. 鉛筆（編集）アイコンをクリック
4. セキュアな入力フィールドにAPIキーを入力

![APIキー設定インターフェース](./docs/images/api-key-ui-section.png)

### カスタムベースURLの設定

カスタムベースURLをサポートするプロバイダー（OllamaやLM Studioなど）の場合、以下の手順に従ってください：

1. サイドバーの設定アイコンをクリックして設定メニューを開く
   ![設定ボタンの場所](./docs/images/bolt-settings-button.png)

2. 「プロバイダー」タブに移動
3. 検索バーを使用してプロバイダーを検索
4. 指定されたフィールドにカスタムベースURLを入力
   ![プロバイダーベースURL設定](./docs/images/provider-base-url.png)

> **注意**: カスタムベースURLは、ローカルでAIモデルを実行する場合やカスタムAPIエンドポイントを使用する場合に特に便利です。

### サポートされているプロバイダー
- Ollama
- LM Studio
- OpenAILike

## Gitを使用したセットアップ（開発者向け）

この方法は以下を目的とする開発者向けに推奨されます：
- プロジェクトへの貢献
- 最新の変更への追従
- 異なるバージョン間の切り替え
- カスタム修正の作成

#### 前提条件
1. Gitのインストール：[Gitのダウンロード](https://git-scm.com/downloads)

#### 初期セットアップ

1. **リポジトリのクローン**：
   ```bash
   # HTTPSを使用
   git clone https://github.com/stackblitz-labs/bolt.diy.git
   ```

2. **プロジェクトディレクトリへ移動**：
   ```bash
   cd bolt.diy
   ```

3. **メインブランチへ切り替え**：
   ```bash
   git checkout main
   ```

4. **依存関係のインストール**：
   ```bash
   pnpm install
   ```

5. **開発サーバーの起動**：
   ```bash
   pnpm run dev
   ```

#### 最新状態の維持

リポジトリから最新の変更を取得するには：

1. **ローカルの変更を保存**（ある場合）：
   ```bash
   git stash
   ```

2. **最新の更新を取得**：
   ```bash
   git pull origin main
   ```

3. **依存関係の更新**：
   ```bash
   pnpm install
   ```

4. **ローカルの変更を復元**（ある場合）：
   ```bash
   git stash pop
   ```

#### Gitセットアップのトラブルシューティング

問題が発生した場合：

1. **クリーンインストール**：
   ```bash
   # node_modulesとロックファイルの削除
   rm -rf node_modules pnpm-lock.yaml

   # pnpmキャッシュのクリア
   pnpm store prune

   # 依存関係の再インストール
   pnpm install
   ```

2. **ローカルの変更をリセット**：
   ```bash
   # すべてのローカル変更を破棄
   git reset --hard origin/main
   ```

コンフリクトを避けるため、更新を取得する前に必ずローカルの変更をコミットするかスタッシュしてください。

## 利用可能なスクリプト

- **`pnpm run dev`**: 開発サーバーを起動
- **`pnpm run build`**: プロジェクトをビルド
- **`pnpm run start`**: Wrangler Pagesを使用してビルドしたアプリケーションをローカルで実行
- **`pnpm run preview`**: プロダクションビルドをローカルでビルドして実行
- **`pnpm test`**: Vitestを使用してテストスイートを実行
- **`pnpm run typecheck`**: TypeScriptの型チェックを実行
- **`pnpm run typegen`**: Wranglerを使用してTypeScript型を生成
- **`pnpm run deploy`**: プロジェクトをCloudflare Pagesにデプロイ
- **`pnpm run lint:fix`**: リンティングの問題を自動修正

## 貢献方法

貢献を歓迎します！始めるには[貢献ガイド](CONTRIBUTING.md)をご確認ください。

## ロードマップ

今後の機能と優先事項については[ロードマップ](https://roadmap.sh/r/ottodev-roadmap-2ovzo)をご覧ください。

## FAQ

一般的な質問、問題、推奨モデルのリストについては[FAQページ](FAQ.md)をご覧ください。
