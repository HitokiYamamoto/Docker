# メモ

## sinatra

sinatraは4567ポートで起動するので4567ポートを公開する

### サンプルコマンド

ビルド

```shell

docker build --tag sample_ruby_app ./ruby

```

実行

```shell
docker run --rm --publish 4567:4567 sample_ruby_app
```
