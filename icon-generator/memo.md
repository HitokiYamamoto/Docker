# メモ

## ビルド

タイムアウトのエラーが出たり出なかったりする

`docker compose build --no-cache` で、cacheなしで実行した後に
`docker compose up --detach`すると成功する
