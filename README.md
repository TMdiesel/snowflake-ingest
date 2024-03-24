# snowflake-ingest

snowpipe streaming を用いた ingest を試すリポジトリです。

## 手順

1. `profile.json.example` を `profile.json` にリネームして、対象の Snowflake アカウントへの接続情報に書き換える。
2. Snowflake で下記の SQL を実行し、対象のデータベース、スキーマ、テーブルを作成する。

   ```SQL
   create or replace database MY_DATABASE;
   create or replace schema MY_SCHEMA;
   create or replace table MY_TABLE(c1 number);
   ```

3. 下記コマンドを実行し、対象テーブルにストリーミングデータを書き込む。

   ```bash
   mvn clean install
   java -cp target/java17-examples-1.0-SNAPSHOT.jar net.snowflake.ingest.streaming.example.SnowflakeStreamingIngestExample
   ```

## 参考

- https://github.com/snowflakedb/snowflake-ingest-java/tree/master
