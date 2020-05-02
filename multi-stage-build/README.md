マルチステージビルドと Docker Compose を使う方法
========================================================================

## 使い方

### 設定

- GitHub の [Personal Access Token](https://help.github.com/ja/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line) を取得する
- [`.env.example`](./.env.example) ファイルをファイル名 `.env` としてコピーする
- `.env` ファイルに Personal Access Token の値を書き込む
- [`Dockerfile`](./Dockerfile) ファイルの中の `username/pkgname` をインストールしたいRパッケージのGitHubリポジトリ名に書き換える（例: [`tidyverse/tidyr`](https://github.com/tidyverse/tidyr) など）
- [`docker-compose.yml`](./docker-compose.yml) ファイルの中の `imagename:tag` をビルドしたイメージに付けたいイメージ名・タグに書き換える（例: `myrstudio:latest` など）

### ビルドの実行

次のコマンドでビルドを実行する:

```sh
docker-compose build --no-cache
```

### コンテナの起動

ビルドされたイメージからコンテナを起動するには、次のコマンドを実行する:

```sh
docker-compose up
```
