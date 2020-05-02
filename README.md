rockerをベースにGitHub上のRパッケージをインストールしたイメージの安全なビルド方法
================================================================================

Dockerイメージ
[rocker/tidyverse](https://hub.docker.com/r/rocker/tidyverse)
をベースに、GitHub上のRパッケージをインストールしたイメージをビルドするためのサンプルコード。

認証に使用する Personal Access Token を安全に取り扱うための方法として

- [Buildkit の `RUN --mount=type=secret` を使う方法](./buildkit-secret/)
- [マルチステージビルドと Docker Compose を使う方法](./multi-stage-build/)

の２つの例を示す。
