# はじめに

やりたいこと、理論上できることは分かっていても、あれこれ最近の技術にキャッチアップするのがつらかったので放っておいたアイデアについて、ChatGPTに聞くとホイホイ実装してくれることが分かったので土日や平日の隙間時間に遊んでいます。

## [tsfrv: 電子公告ビューア telnets版](https://github.com/masanork/tsfrv)

telnetプロトコルで電子公告する一般社団法人ができたので、閲覧結果をログに残すことができる専用ビューアをつくりました。Telnet over SSL/TLSに対応し、公告とチャットを分けてログに保存できます。似たようなことをやる組織が現れるとは思えませんが、コマンドラインで接続先を指定すれば、そこに繋がるようにはしています。macOSで使うことを念頭に作成しましたが、Windows Terminalでも文字化けせず使えました。

## [sorane](https://masanork.github.io/sorane/)

WebFont埋込機能を組み込んだ静的サイトジェネレーターです。Markdownで書いた記事をHTMLに変換するだけのシンプルなものですが、WebFont埋込機能を組み込んでいるので、ブラウザのデフォルトフォントに依存せずに、氏名の異体字や外国語を正確に表現したり、様々な書体を組み合わせて使うことができます。

## [GlyphPicker](https://masanork.github.io/GlyphPicker/)

GlyphPickerは、TrueTypeフォントから必要なグラフだけを抜き出してWOFF2フォーマットのWebFontを生成するツールです。日本語は文字数が多いことから、これまでWebfontで自由に様々な書体を組み合わせて使うことが難しかったのですが、実際に使われているグリフだけを抜き出すことで、端末の設定に依存せず様々な書体を組み合わせて使ったり、氏名の異体字など特殊な字形を表示できます。

## [Base2136 常用漢字エンコーダー](https://github.com/masanork/bs2136)

BASE2136はBASE64やBASE58のような、バイト列をテキストに変換する仕組みで、数字やアルファベットの代わりに常用漢字2,136文字を利用します。13桁までの数字を漢字4文字で表現できるのですが、覚えやすいかというと漢字によりけりになってしまって、何か使い途があるかは分かりません。文字数が多過ぎるのでアルゴリズムとしてはBASE系よりもBIP39あたりを見るべきか。あくまでネタとしての実験なので、あまり深く考えずにご笑覧ください。

## [loev: List of Entity Verifier](https://github.com/masanork/loev)

loevは2つの同じ項目を持ったリストの比較を行うツールです。それぞれのカラムを別々に正規化して中間生成ファイルを記録に残し、最終的にはそれらを統合して検証結果を出力します。カラムはプログラムの呼び出し方で柔軟に追加削除できるようになっています。中間生成ファイルを記録として全て残すことで、処理の流れを容易に追うことができ、仮に不具合があった場合の障害の切り分けの手がかりを提供します。

## [異体字漢字コンバーター](https://github.com/masanork/ikc)

氏名住所の名寄せや機械学習の前処理において、漢字の異体字を正字に寄せることは重要な作業です。異体字シソーラスとして網羅的なものは見つけられていないのですが、とりあえず[史料編纂所データベース異体字同定一覧](https://wwwap.hi.u-tokyo.ac.jp/ships/itaiji_list.jsp)のデータを元に変換表を作成するmkitaiji.pyと、変換表を使ってテキストを処理するフィルターikcが含まれます。

## [住基ネット統一文字コード変換表](https://github.com/masanork/jkc)

住基ネット統一文字コードを文字情報基盤に変換する文字コード変換表です。MJ文字一覧表のCSVファイルから文字コード変換表を生成するmkjk2mj.pyと、生成した変換表を使って実際のコード変換を行うフィルターjkcが含まれます。

## [faq2fc: FAQからJSONファイルを生成](https://github.com/masanork/faq2fc)

Markdownで記載されたFAQをAzure OpenAIのfine tuningに使うJSONに変換するプログラム。といってもまだちゃんとfine tuningで遊べていないので、そのうちやります。
