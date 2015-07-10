## 東京都のオープンデータをExcelからCSV/GeoJSONに変換

[東京都オープンデータ一覧（試行版）](http://www.metro.tokyo.jp/SUB/OPENDATA/index.htm)の地物情報をCSV変換してGeoJSON化してみる。

### 変換手順
1. Excelダウンロード(例：[小学校のExcel](http://www.seikatubunka.metro.tokyo.jp/shigaku/syoutyuukou/meibo/27.4.1elementary.xls)をダウンロード)
2. CSVとして保存して下記の修正を施す
- 「学校名称」「郵便番号」「所在地」「電話番号」「latitude」「longitude」の列にまとめる
- 学校名称で文字化けしているところを修正（Mac上では「麹」とか難しい漢字が文字化けした）
- ファイルの改行をUnix, 文字コードをUTF-8に変換
- 緯度経度を
3. [地理院地図](http://maps.gsi.go.jp)のヘッダー域に住所を入れてEnterを押下すると左側に候補の地物が表示されるのでそれをクリックして地図を移動
4. 地図上で目的の地物を探して、地図上の場所を中心地に移動すると、URLに緯度経度が表示されるので、これを緯度経度として使用
5. CSVからGeoJSONという形式に変換するとGithub上で地図に表示することができる

### 参考情報
- [地理院地図](http://maps.gsi.go.jp)
- [CSVからGeoJSONに変換するツール](http://csv.togeojson.com)
- [オープンデータ保存・公開に便利なGithub](https://speakerdeck.com/benbalter/government-open-source-zheng-fu-yazi-zhi-ti-falseopunsosuhuo-yong)
- [Github利用事例](http://wakayama.keizai.biz/headline/334)
