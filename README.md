# REST APIのテスト

## nodeのインストール
```zsh
$ brew install node
```

## json-serverのインストール

```zsh
$ npm install -g json-server
```

**jsonデータ**

```json
{
  "movies": [
    {"id": 1, "name": "The Godfather", "director":"Francis Ford Coppola", "rating": 9.1},
    {"id": 2, "name": "Casablanca", "director": "Michael Curtiz", "rating": 8.8}
  ]
}
```

## JSONサーバーを起動する

```zsh
$ json-server --watch db.json
```

[http://localhost:3000/movies](http://localhost:3000/movies)をみる
結果
```json
[
  {
    "id": 1,
    "name": "The Godfather",
    "director": "Francis Ford Coppola",
    "rating": 9.1
  },
  {
    "id": 2,
    "name": "Casablanca",
    "director": "Michael Curtiz",
    "rating": 8.8
  }
]
```

## POSTで追加する

```zsh
$ curl -X POST -H "Content-Type: application/json" -d '{
  "id": 3,
  "name": "Inception",
  "director": "Christopher Nolan",
  "rating": 9.0
}' "http://localhost:3000/movies"
```

## GETで取得する

```
$ curl -X GET "http://localhost:3000/movies/3"
```

結果

```json
{
  "id": 3,
  "name": "Inception",
  "director": "Christopher Nolan",
  "rating": 9
}
```

# 参考サイト

**リンク**

[0からREST APIについて調べてみた - Qiita](https://qiita.com/masato44gm/items/dffb8281536ad321fb08#:~:text=RESTful%20API(REST%20API)%E3%81%A8,%E3%81%AB%E5%BE%93%E3%81%A3%E3%81%A6%E7%AD%96%E5%AE%9A%E3%81%95%E3%82%8C%E3%81%9F%E3%82%82%E3%81%AE%E3%80%82)


