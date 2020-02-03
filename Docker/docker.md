# Docker
## Dockerfile
Docker for Windows ダウンロード
Docker for windowsダウンロード

Dockerfileの作成
```text:Dockerfile
FROM ubuntu:16.04

COPY helloworld /usr/local/bin
RUN chmod +x /usr/local/bin/helloworld

CMD ["helloworld"]
```
|要素 |説明 |
|:----|:----|
|FROM|ベース（コンテナの雛形）となるDockerイメージ（OS）を定義|
|COPY|ホストOSからDockerコンテナへファイルをコピー|
|RUN|Dockerコンテナ内で任意のコマンドを実行できる仕組み|
|CMD|Dockerイメージをコンテナととして実行する前に行われるコマンドを定義|

Dockerイメージのビルド
```shell script
$ docker image build -t helloworld:latest .
```

Dockerコンテナの実行
```shell script
$ docker container run helloworld:latest
```