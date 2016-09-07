# docker-elasticsearch-kopf

[elasticsearch-kopf](https://github.com/lmenezes/elasticsearch-kopf) のバージョン 1.5.8 をカスタマイズしたものです。

- KOPF_ES_ROOT_PATH をバックポート。
- KOPF_WITH_CREDENTIALS をバックポート。
- KOPF_THEME をバックポート。
- KOPF_REFRESH_RATE をバックポート。
- /_site ではなく / で動作するように変更。
- アクセスログ、エラーログを標準出力に出力するように変更。

## 例

    $ docker run -p 8080:80 -e KOPF_SERVER_NAME=10.10.10.10:8080 -e KOPF_ES_SERVERS=10.10.10.10:9200 --rm --name kopf cosmicvelocity/docker-elasticsearch-kopf:1.5.8

## ドキュメント

### コンテナのビルド

    mkdir docker-elasticsearch-kopf
    cd docker-elasticsearch-kopf
    curl -L https://raw.githubusercontent.com/cosmicvelocity/docker-elasticsearch-kopf/1.5.8/1.5.8/Dockerfile > Dockerfile
    docker build -t cosmicvelocity/elasticsearch-kopf:1.5.8 .

### 実行

    $ docker run -p 8080:80 -e KOPF_SERVER_NAME=10.10.10.10:8080 -e KOPF_ES_SERVERS=10.10.10.10:9200 --rm --name kopf cosmicvelocity/docker-elasticsearch-kopf:1.5.8
