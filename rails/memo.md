# メモ

## 実行例

ビルド

```shell
docker build --tag rails ./rails
```

実行

```shell
docker run --rm -it \
    --mount type=bind,source="$(pwd)"/rails,target=/app \
    rails \
    rails new blog --database=postgresql
```
