# parcelを使ってみた
webpackの代わりになると噂のparcelを使ってみた。

## ディレクトリ構成
~~~
project
 ├ public
 │ ├ b2da58956e104b2afdedc5fc76883769.css # 結合後のcss
 │ ├ b2da58956e104b2afdedc5fc76883769.js # 結合後のjs
 │ └ index.html          # コンパイル後のhtml
 │
 ├ src
 │ ├ css                 
 │ │ └ style.css       # 普通にcss
 │ │
 │ ├ js                 
 │ │ ├ module
 │ │ │ └ util.js      # インポートされる側のjs
 │ │ └ app.js          # インポートする側のjs
 │ │ 
 │ └ index.html         # エントリーポイント
 │
 ├ .cache                # parcelでビルドした時にできるキャッシュ
 ├ node_modules          # nodeモジュール（git管理はしない）
 └ readme.md
~~~

## 使い方
npm run を使ってコマンドを実行する。
~~~
npm run parcel
~~~
上記のコマンドで以下のようなコマンドを読んでいる
~~~
node_modules/.bin/parcel src/index.html -d public
~~~
上記は、「src/index.htmlをエントリーポイントとし、publickディレクトリに書き出す」というコマンド

# demo
https://yuki-sakaguchi.github.io/parcel-test/public/

## 感想
勝手にwatch状態になるし、ビルドも早いのでそこそこ使えそう。  
でも書き出すファイル名とかが乱数以外つけられないっぽいし、複雑な処理や複数のエントリーポイントに対応していない？  
ので、まだwebpackほどの汎用性はないかも。

