# メモ

## 初期設定

```shell
docker compose up --detach

docker compose exec web bin/rails db:create
```

## scaffoldを使ってみる

```shell
docker compose exec web rails g scaffold Post title:string body:text

docker compose exec web rails db:migrate
```
