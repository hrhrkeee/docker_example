# 起動方法

## ビルド
```
docker build -t docker_test .
```

## コンテナ作成・起動
オプション -v のホスト側ディレクトリは絶対パスを指定する。
```
# docker run -i -t --name [コンテナ名] -v $(pwd)/[マウントしたいディレクトリ]:[マウント先のパス] [イメージ] /bin/bash

```

サンプルコマンド
```
docker run -d -it --name mount_test -v $(pwd)/sample_code:/home/sample_code docker_test


docker run -d -it --name mount_test -v "C:\Users\hirahara\Documents\Python Scripts\docker_example\202306202_volume_mount\sample_code":/home/sample_code docker_test
```

## bashに入る
```
docker exec -it mount_test bash
```