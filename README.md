# FastAPI Practice
PythonのフレームワークであるFastAPIの練習用リポジトリ。  
以下のサイトを参考に勉強をする。  
https://nmomos.com/tips/2021/04/11/fastapi-docker-10/

## Section1
FastAPI + DockerでHelloWorldを行った。  
FastAPIのAPIRouterを使うことで、エントリーポイントを持つ関数を複数のファイルに分割ができる。  
Dockerは、Vimでモジュールの補完が表示されるように多少手を加えている。

## Section2
SQLAlchemyでPostgreSQLに接続をする。  
マイグレーションにはalmbicを利用する。  
モジュールを参照できるように、
```sys.path.append(str(pathlib.Path(__file__).resolve().parents[3])) ```
を記載している部分があるが、フォーマッターが勝手に記載場所を変えてしまってマイグレーションを実行するときにエラーを吐いたところでハマった。
