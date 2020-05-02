Buildkit の `RUN --mount=type=secret` を使う方法
========================================================

## 使い方

### 設定

- GitHub の [Personal Access Token](https://help.github.com/ja/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line) を取得する
- [`.env.example`](./.env.example) ファイルをファイル名 `.env` としてコピーする
- `.env` ファイルに Personal Access Token の値を書き込む
- [`Dockerfile`](./Dockerfile) ファイルの中の `username/pkgname` をインストールしたいRパッケージのGitHubリポジトリ名に書き換える（例: [`tidyverse/tidyr`](https://github.com/tidyverse/tidyr) など）

### ビルドの実行

イメージをビルドするには、次のコマンドを実行する
（`imagename:tag` はビルドしたイメージに付けたいイメージ名・タグに置き換える）:

```sh
DOCKER_BUILDKIT=1 \
  docker build -t imagename:tag \
  --secret id=dotenv,src=.env \
  .
```

### コンテナの起動

ビルドされたイメージからコンテナを起動するには、次のコマンドを実行する:

```sh
docker run --rm -d -p 8787:8787 -e PASSWORD=password imagename:tag
```
