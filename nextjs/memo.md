# メモ

## Create App

```shell
docker run --rm -it \
    --mount type=bind,source="$(pwd)",target=/app \
    --workdir /app \
    node:22 \
    sh -c "npx create-next-app"
```

## マルチステージビルド

### ビルド

```shell
docker build --tag nextjs:production --file Dockerfile.production . 
```

### 確認

```shell
docker run --rm --publish 3000:3000 nextjs:production
```