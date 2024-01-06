# Poetry について

## Poetry の主な機能

- 依存関係の管理: Poetry は依存関係をより効果的に管理します。pyproject.toml ファイルを使用してプロジェクトの依存関係を宣言的に記述し、poetry.lock ファイルでこれらの依存関係の正確なバージョンを管理します。
- パッケージの作成と配布: Poetry は、プロジェクトのパッケージ化と PyPI への配布を容易にします。一般的な設定は pyproject.toml ファイルで管理され、コマンド一つでパッケージを作成・公開できます。
- 仮想環境の管理: Poetry は自動的にプロジェクト専用の仮想環境を作成し、プロジェクトごとに隔離された環境を提供します。これにより、異なるプロジェクト間での依存関係の衝突を防ぎます。
- 簡単な依存関係の追加と削除: 新しい依存関係を追加する際、Poetry は自動的に最適なバージョンを解決し、pyproject.toml と poetry.lock を更新します。依存関係の削除も同様に簡単です。
- バージョン解決と互換性の保証: Poetry は依存関係のバージョンを解決し、互換性のあるバージョンを選択するための強力なアルゴリズムを使用します。

## 仮想環境に関する機能

自動的な仮想環境の作成と管理: Poetry はプロジェクトの依存関係をインストールする際、自動的に仮想環境を作成します。これにより、システムの Python 環境に影響を与えずに依存関係を管理できます。

プロジェクトごとの隔離: 各プロジェクトは独自の仮想環境を持つため、異なるプロジェクト間でのライブラリのバージョンの衝突を避けることができます。

簡単なアクティベーション: Poetry で作成された仮想環境は、特定のコマンド（`$ poetry shell`） を使用することで簡単にアクティベートできます。

仮想環境のカスタマイズ: ユーザーは Poetry の設定を通じて仮想環境の場所や動作をカスタマイズすることが可能です。

## パッケージ配布について

Poetryを使用してPythonパッケージを作成し、PyPI（Python Package Index）に配布する手順は以下の通りです：

1. Poetryのインストール
まだPoetryをインストールしていない場合は、公式サイトの指示に従ってインストールします。

2. プロジェクトの設定
既存のプロジェクトにPoetryを使用する場合は、プロジェクトのルートディレクトリで以下のコマンドを実行します：

```
poetry init
```

このコマンドは、プロジェクトの設定を行うためのpyproject.tomlファイルを作成します。対話式のプロンプトが表示され、プロジェクトの詳細（名前、バージョン、説明、作者など）を入力します。

3. 依存関係の追加
必要な依存関係は、以下のコマンドで追加できます：

```
poetry add <パッケージ名>
```

4. ビルド
プロジェクトのパッケージをビルドするには、以下のコマンドを実行します：

```
poetry build
```

このコマンドは、プロジェクトをdistディレクトリに.whl（ホイール）ファイルと.tar.gzファイルとしてビルドします。

5. PyPIへの登録
PyPIにアカウントを作成し、必要に応じてAPIトークンを取得しておきます。

6. パッケージの公開
以下のコマンドでPyPIにパッケージを公開できます：

```
poetry publish --username <ユーザー名> --password <パスワード>
```

API トークンを使用する場合は、 --password の代わりにトークンを指定します。

```
poetry publish --username __token__ --password <APIトークン>

```

注意点：
- パッケージを公開する前に、pyproject.tomlファイルでパッケージの情報（名前、バージョン、説明、ライセンスなど）が正しく設定されていることを確認してください。
- PyPIには既に多くのパッケージが存在するため、独自の名前を選ぶことが重要です。
- ビルドと公開のプロセスは、プロジェクトの規模や複雑さによって異なる場合があります。

これらの手順に従って、Poetryを使用してPythonパッケージを効率的に作成し、PyPIに公開することができます。



このコマンドは、pyproject.toml で定義されたスクリプトを通じてFlaskアプリケーションを起動します。
Flask がデフォルトで使用するポート（通常は5000）で Webサーバが起動し、ブラウザからアクセスできるようになります。

この方法により、Poetry を使って Flask アプリケーションの起動を簡単に管理できます。


