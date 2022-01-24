# FastAPI Practice
PythonのフレームワークであるFastAPIの練習用リポジトリ。  
以下のサイトを参考に勉強をする。  
https://nmomos.com/tips/2021/04/11/fastapi-docker-10/

## Section1
FastAPI + DockerでHelloWorldを行った。  
FastAPIのAPIRouterを使うことで、エントリーポイントを持つ関数を複数のファイルに分割ができる。  
Dockerは、Vimでモジュールの補完が表示されるように多少手を加えている。

## Section2
SQLAlchemyでPostgreSQLに接続をするための準備。  
マイグレーションにはalmbicを利用する。  
モジュールを参照できるように、
```sys.path.append(str(pathlib.Path(__file__).resolve().parents[3])) ```
を記載している部分があるが、フォーマッターが勝手に記載場所を変えてしまってマイグレーションを実行するときにエラーを吐いたところでハマった。

## Section3
DB接続を実際に行う。  
リポジトリの作成や依存性の注入も行う。  
モデルクラスは以下の方針で作られているのが勉強になる。  

>今回作成した5つのモデルは、ほぼすべてのリソースで使用されるパターンを示しています。
>
>- Base: 全リソースで共有する属性
>- Create: 新しいリソースを作成する際に必須の属性
>- Update: 更新することが可能な属性
>- InDB: データベースから取得するリソースに存在する属性
>- Public: GET, POST, PUTリクエストで返されるデータに存在する属性  

依存性に関しては ```db/tasks.py``` でアプリケーションのステートに入れているDB接続インスタンスを利用している。  
ここが今後実行時引数などで変更される？？
