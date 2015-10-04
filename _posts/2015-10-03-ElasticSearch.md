---
layout: post
title:  "Elasticsearchについて"
date:   2015-10-03 
categories: md made
---

# 目標

プロジェクトでのチケット管理のために、
残りチケット等を可視化するためのツールとして、
ElasticSearchが使えるようになる。

# やったこと

## elasticsearch環境構築

参考：[http://qiita.com/Aco-gt/items/ad351387c1ab3ad2561f](http://qiita.com/Aco-gt/items/ad351387c1ab3ad2561f)

elasticsearch 1.7.2ダウンロード

環境変数に「JAVA_HOME」を追加

elasticsearch-1.7.2/binディレクトリにて以下のコマンド実行

`./elasticsearch.bat`

[http://localhost:9200/](http://localhost:9200/)にて、以下が表示されることを確認

```
{
  "status" : 200,
  "name" : "Hercules",
  "cluster_name" : "elasticsearch",
  "version" : {
    "number" : "1.7.2",
    "build_hash" : "e43676b1385b8125d647f593f7202acbd816e8ec",
    "build_timestamp" : "2015-09-14T09:49:53Z",
    "build_snapshot" : false,
    "lucene_version" : "4.10.4"
  },
  "tagline" : "You Know, for Search"
}
```

## kibana環境構築

kibana 4.1.2ダウンロード

kibana-4.1.2-windows/binディレクトリにて以下のコマンドを実行

`./kibana.bat`

[http://localhost:5601](http://localhost:5601)にアクセスし、webサイトが表示されることを確認

### elasticsearchにてCSVを読みこませる

kuromojiをインストール。以下のコマンドを実行。
（サイトには「bin/plugin install」と書かれているが、動作しなかった。（OSのせい？））

`./bin/plugin --install elasticsearch/elasticsearch-analysis-kuromoji/2.7.0`

CSV River Pluginをインストール。以下のコマンドを実行

`./bin/plugin.bat --install river-csv -url https://github.com/AgileWorksOrg/elasticsearch-river-csv/releases/download/2.2.1/elasticsearch-river-csv-2.2.1.zip`



