# メモ

## Create App

```shell
docker run --rm -it \
    --mount type=bind,source="$(pwd)",target=/app \
    --workdir /app \
    node:22 \
    sh -c "npx create-next-app"
```
