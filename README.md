# docker_example
Dockerの勉強用で使うこととする

# よく使うDockerコマンド

## Dockerfileをビルドする
```
docker build -t [作成するイメージ名] .
```

## イメージを作成・起動してbashに入る
exitしたら止まる
```
docker run -it --name [作成するコンテナ名] [Dockerイメージ名]
```

## イメージを作成・起動(バックグラウンド)
exitしても止まらない
```
docker run -d -it --name [作成するコンテナ名] [Dockerイメージ名]
```

## 起動したコンテナに入る
```
docker exec -it [コンテナ名] bash
```

