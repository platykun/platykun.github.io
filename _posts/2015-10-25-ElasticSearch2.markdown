---
layout: post
title:  作業手順まとめ
date:   2015-10-25
categories: matome
---

### elasticsearch使い方

####index追加削除

追加

    curl -XPOST http://localhost:9200/index_name

削除

    curl -XDELETE http://localhost:9200/index_name

### 今後やるべきことの検討

Redmineのチケットの未達成のものを、グラフで可視化するために必要な手順

1. Redmineから必要なデータをcsvで出力する。
2. csvファイルからelasticsearchへ取り込む
3. Kibanaによって、ステータスが未達成、達成のものを日付ごとに表示させる。

Kibanaで表示させたいグラフ： <br>
x軸：日付 <br>
y軸：count <br>
折れ線１：起票されたチケット合計数 <br>
折れ線２：起票されているかつ、ステータスが達成のもの <br>
折れ線３：起票されているかつ、ステータスが未達成のもの

懸念事項： <br>
条件指定がどこまで複雑なものが許されるのか
→elasticsearchにデータを投入する前後にデータを整形する必要がある


