# 2023年6月18日

Dockerの基本的な使い方を学ぶ

<br><br>

# とりあえずサンプルをビルド・起動・実行・終了・削除
## ビルド
```
docker build -t docker_ubuntu .
```
## コンテナ実行・bash
```
docker run -it docker_ubuntu bash 
```
## コンテナから抜ける（Bashから抜ける）
バックグラウンド(-d)で実行していないため、コンテナも停止する
```
$ exit
```
## コンテナに名前をつけてバックグラウンドで実行
```
docker run -d -it --name docker_test docker_ubuntu
```
## 起動中のコンテナに入る
```
docker exec -it docker_test bash
```
## コンテナから抜ける（Bashから抜ける）
バックグラウンド(-d)で実行しているため、exitしても起動したまま
```
$ exit
```
## コンテナを停止する
```
docker stop docker_test
```
## コンテナを削除する
```
docker rm docker_test
```
## Dockerイメージを削除する
```
docker rmi docker_ubuntu
```

<br><br>

# Dockerの使い方
## Dockerfileのビルド方法
### 基本コマンド
```
docker image build -t イメージ名[:タグ名] [Dockerfileが配置されているディレクトリパス]
```

## Dockerイメージからコンテナを作成
### 基本コマンド
```
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
docker run --name {コンテナ名} -it {image名} /bin/bash
```
### オプション
 - --name : コンテナ名を指定
 - -d : バックグラウンドで実行
 - -p : ポートフォワーディング
 - -it ： コンテナ内で操作
 - -v ： ボリュームのマウント
 - --restart always ： 自動再起動
 - --env DISPLAY=$DISPLAY： コンテナ上にいるTerminalから画像表示用のウィンドウを表示
 - --device /dev/video0 ： Webカメラにアクセス

### 実行中コンテナ内部に入る（コマンド）
```
docker exec -it [コンテナID・name] bash
```

### サンプル実行方法
```
docker run -it docker_test_ubuntu bash 
```