---
layout: page
title: MyFleetGirlsセットアップ手順
permalink: /setup_detail
---

<div class="row">

<section id="getstarted" class="col-sm-9" markdown="1">

# MyFleetGirlsセットアップ手順

## はじめに
{: #start}

MyFleetGirlsのセットアップの方法をちょこっとだけ詳しく説明して、導入を簡単にするのが目的のドキュメントです。

導入順序は[こちら]({{ '/' | relative_url }})の、「インストール・使い方」に準じて進めていきます。

こちらの説明で困らずにセットアップできた方はこれを読まなくても何の問題もありません。

パソコンの操作や知識にちょっと自信がない人向けの説明書になります。

パソコンの設定は上手くいかないときはほんとにはまってしまうので、あせらずゆっくり、落ち着いて行いましょう。

なお、OSはWindows系OS（特にWindows7）を対象とします。


## Javaセットアップ
{: #java_setup}

ここではJavaのセットアップ方法について解説します。Java8以降がインストールされていることが分かっている場合はこの章を読み飛ばしてもらって構いません。

### Javaインストール状況の確認

まず、自分のパソコンにJavaがセットアップされているか確認するために、Javaのバージョンを確認しましょう。

場合によっては一番躓いてしまうところですので、落ち着いて気長に行いましょう！！

まずコマンドプロンプトを開きます。

コマンドプロンプトって何？って人は、デスクトップ左下の「スタート」のクリックして「プログラムとファイルの検索」に`cmd`と入力して<kbd>Enter</kbd>を押します。

![cmd]({{ '/assets/img/setup/cmd.png' | relative_url }}){: .img-rounded}

そうすると、黒い画面が出てきますので、`java -version`と入力し、<kbd>Enter</kbd>を押します。

![java_cmd]({{ '/assets/img/setup/java_cmd.png' | relative_url }}){: .img-rounded}

もしJavaが正常に設定されていれば、このコマンドによってJavaのバージョンが確認できます。

![java_version]({{ '/assets/img/setup/java_version.png' | relative_url }}){: .img-rounded}

`java version`の後の数字がJavaのバージョンです。

ここで`1.7.なんとか`がJava7のバージョンで、`1.8.なんとか`がJava8のバージョンです。

MyFleetGirlsはJava8以上のバージョンが必須なので、`1.6.なんとか`等、古かったら次の節を見て最新版をインストールしましょう。

問題は上記のように表示されなかった場合です。

恐らく、このように表示されます。

![non_java]({{ '/assets/img/setup/non_java.png' | relative_url }}){: .img-rounded}

大きく分けて次の二つの場合が考えられますので、順番に確認します。

1. Javaがインストールされていない
2. Javaはインストールされているが、パソコンが`java`というコマンドを認識しない

### Javaがインストールされていない場合の対応方法

デスクトップ右下の「スタート」をクリックして「コントロールパネル」を開きましょう。

![control_panel]({{ '/assets/img/setup/control_panel.png' | relative_url }}){: .img-rounded}

その中にJavaがあれば問題ありませんので、2の対応に移ってください。

![control_java]({{ '/assets/img/setup/control_java.png' | relative_url }}){: .img-rounded}

無い場合は、公式サイトからダウンロードしてインストールを行いましょう。
[公式ダウンロードサイト](https://java.com/ja/download/)

Javaをインストールしたらまた初めの手順にもどってJavaのバージョン確認を実行して下さい。


### パソコンが`java`コマンドを認識しない場合の対応方法

パソコンの「環境設定」が必要になります。

まずはJavaがどこに保存されているか確認しましょう。

Javaがインストールされていれば、以下のように辿ればJavaのフォルダが作成作成されているかと思います。

```Cフォルダ ⇒ Program Files (x86) ⇒ Java```


![jre_dir]({{ '/assets/img/setup/jre_dir.png' | relative_url }}){: .img-rounded}

このJavaのフォルダの中にバージョンごとのJavaがあります。

例えば画像のパソコンの場合、Java7とJava8が保存されています。

jreの後の数字は、「jre7」のように一つだけならそのバージョンですが、`jre1.8.0_25`のようになっていたら、`1.`の次の数字の`8`がそのバージョンとなります。

更にここからJavaの実行フォルダの「bin」フォルダを探します。

複数バージョンがある場合は最新のバージョンを選びましょう。

今回の場合はこのように進みます。

```jre1.8.0_25 ⇒ bin```

ここが目的のJavaの実行場所です。

![address_bar]({{ '/assets/img/setup/address_bar.png' | relative_url }}){: .img-rounded}

そうしましたら、上の画像の赤で囲っているアドレスバーの何も無いところをクリックして下さい。

そうすると、このアドレスをコピーできるようになりますので、コピーしましょう。

![address_bar2]({{ '/assets/img/setup/address_bar2.png' | relative_url }}){: .img-rounded}

メモ帳を開いていったん貼り付けます。

そして、**先頭に半角セミコロン`;`を加えてください。**

![memo_colon]({{ '/assets/img/setup/memo_colon.png' | relative_url }}){: .img-rounded}

この値を「環境変数」の「Path」に加えたら完成です。

コントロールパネルから「システム」を選択してください。

![system]({{ '/assets/img/setup/system.png' | relative_url }}){: .img-rounded}

次に左のほうにある「システムの詳細設定」を選択します。

![system_detail]({{ '/assets/img/setup/system_detail.png' | relative_url }}){: .img-rounded}

そうすると、システムのプロパティ画面が開きます。

「詳細設定」のタブを選び、下のほうの「環境変数」のボタンをクリックしてください。

![system_property]({{ '/assets/img/setup/system_property.png' | relative_url }}){: .img-rounded}

環境変数の画面が開きますので、下の「システム環境変数」から「Path」を探してクリックして選択し、「編集」ボタンを押します。

![environment]({{ '/assets/img/setup/environment.png' | relative_url }}){: .img-rounded}

そしたら、さっきメモ帳で作成した文字列を変数値の一番最後に加えます。

**必ず一番最後です**間違ったらキャンセルで閉じてやり直してください。

![add_environment]({{ '/assets/img/setup/add_environment.png' | relative_url }}){: .img-rounded}

これで作業完了です、各画面を「ok」ボタンで閉じてください。

そしたらまた一番最初の作業のコマンドプロンプトでの`java -version`確認を行ってください。

正常にバージョンが確認できたら作業完了です。


## Download
{: #download}

以下のリンクのダウンロードから行いましょう。

[Downloaderのdownload]({{ site.productUrl }}/assets/zip/MyFleetGirls.zip)

保存場所ですが、作業フォルダを作成してわかりやすい場所に保存することをお勧めします。（このマニュアルでは、「D:\ツール\艦これ」という場所に保存しました。）


## 解凍
{: #extract}

先ほどダウンロードしたDownloaderを展開します。

お使いの解凍ソフトを使って展開してください。

解凍ソフトが無い場合は、ダウンロードしたZipファイルを右クリックし、「すべて展開」を選んだ後に「展開」ボタンを押してください。

下の画像のようにフォルダが展開されれば成功です。

![extract]({{ '/assets/img/setup/extract.png' | relative_url }}){: .img-rounded}


## Proxy設定
{: #proxy}

MyFleetGirlsを使用しながら艦これをプレイするには、プロキシ（Proxy）の設定が必要となります。

お使いのブラウザによって設定方法が異なりますので注意してください。

ここでは以下のブラウザにおける設定方法について説明します。

1. IEの場合
2. Google Chromeの場合
3. Mozilla Firefoxの場合

なお、プロキシの設定を行った場合MyFleetGirlsを起動しないと艦これが起動しなくなり、設定を戻す必要がありますので注意してください。

### IEの場合

「LANの設定」を変更します。

IEを開いて右上の歯車のマークの「ツール」をクリックし「インターネットオプション」を開きます。

![ie_option]({{ '/assets/img/setup/ie_option.png' | relative_url }}){: .img-rounded}

「接続」タブを選択して「LANの設定」を開きます。

![ie_connection]({{ '/assets/img/setup/ie_connection.png' | relative_url }}){: .img-rounded}

「自動構成スクリプトを使用する」にチェックを入れて、アドレスに[{{ site.productUrl }}/assets/proxy.pac]({{ site.productUrl }}/assets/proxy.pac)を加え「OK」を押します。

![ie_proxy]({{ '/assets/img/setup/ie_proxy.png' | relative_url }}){: .img-rounded}

以上で設定は完了です。

なお、この状態で艦これをプレイするには、MyFleetGirlsの起動が必要となります。

MyFleetGirlsを使用しないで艦これをプレイする場合はこの「自動構成スクリプトを使用する」の**チェックを必ず外して**ください。


### Google Chromeの場合

IEと同じように「LANの設定」を変更しますが、開く手順が違います。

まず、Chromeを開いてから右上の三本線の「ツール」を開き、「設定」を開きます。

![chrome_option]({{ '/assets/img/setup/chrome_option.png' | relative_url }}){: .img-rounded}

設定のタブが開きますので、一番下の「詳細設定を表示」をクリックします。

![chrome_settings_detail]({{ '/assets/img/setup/chrome_settings_detail.png' | relative_url }}){: .img-rounded}

そうしたら画面の下に詳細設定が開きますので、「ネットワーク」のプロキシ「設定の変更」をクリック、「インターネットのプロパティ」を開きます。

![chrome_change_proxy]({{ '/assets/img/setup/chrome_change_proxy.png' | relative_url }}){: .img-rounded}

「接続」タブを選択して「LANの設定」を開きます。

![ie_connection]({{ '/assets/img/setup/ie_connection.png' | relative_url }}){: .img-rounded}

「自動構成スクリプトを使用する」にチェックを入れて、アドレスに[{{ site.productUrl }}/assets/proxy.pac]({{ site.productUrl }}/assets/proxy.pac)を加え「OK」を押します。

![ie_proxy]({{ '/assets/img/setup/ie_proxy.png' | relative_url }}){: .img-rounded}

以上で設定は完了です。

この状態で艦これをプレイするには、MyFleetGirlsの起動が必要となります。

MyFleetGirlsを使用しないで艦これをプレイする場合はこの「自動構成スクリプトを使用する」の**チェックを必ず外して**ください。


### Mozilla Firefoxの場合

Firefoxを開いてキーボードの「Alt」を押してメニューを開きます。

そして、「ツール」⇒「オプション」を開きます。

![firefox_option]({{ '/assets/img/setup/firefox_option.png' | relative_url }}){: .img-rounded}

「ネットワーク」タブから「接続設定」をクリックします。

![firefox_connection]({{ '/assets/img/setup/firefox_connection.png' | relative_url }}){: .img-rounded}

「自動プロキシ設定スクリプトURL」を選択し、画像のように[{{ site.productUrl }}/assets/proxy.pac]({{ site.productUrl }}/assets/proxy.pac)を加えて「OK」をクリックします。

![firefox_proxy]({{ '/assets/img/setup/firefox_proxy.png' | relative_url }}){: .img-rounded}

以上で設定は完了です。

この状態で艦これをプレイするには、MyFleetGirlsの起動が必要となります。

MyFleetGirlsを使用しないで艦これをプレイする場合は**「プロキシを使用しない」を選んで**ください。


## MyFleetGirlsの起動
{: #startup}

プロキシの設定が終わったらMyFleetGirlsを起動します。

普通に起動するには「MyFleetGirls.bat」を起動すれば問題ないかと思います。

![myfleet_bat]({{ '/assets/img/setup/myfleet_bat.png' | relative_url }}){: .img-rounded}

そうすると黒い画面が出ます。

![myfleet_console]({{ '/assets/img/setup/myfleet_console.png' | relative_url }}){: .img-rounded}

これで起動は完了です。


## 艦これを起動する
{: #kancolle}

プロキシ設定したブラウザで普通に艦これを起動します。

母港画面が開いたら問題ありません。


## 動作確認
{: #check}

MyFleetGirlsのWEBサイトに接続します。
[{{ site.productUrl }}]({{ site.productUrl }})

「所属基地名」に自分の接続しているサーバーを入力してください。

この状態で自分の提督名が見つからない場合は「提督名」に自分の提督名を入れて検索してください。

以上でセットアップは完了です。


## パスワードの設定
{: #password}

MyFleetGirlsにログインできるようになると嫁艦設定などができるようになります。

ここではパスワード設定を説明します。

パスワードは一度設定すると、自力では変更できませんので注意してください。

詳細はFAQを参照してください。

まず、MyFleetGirlsのフォルダの「application.conf.sample」をコピーして貼り付けて、`application.conf - コピー.sample`を作成します。

![conf_copy]({{ '/assets/img/setup/conf_copy.png' | relative_url }}){: .img-rounded}

次に、作成した「application.conf - コピー.sample」をメモ帳で開きます。

そして、`# pass: abcde`の部分の`#`を削除して`abcde`の部分に好きなパスワードを設定し、保存して閉じます。

![memo_pass]({{ '/assets/img/setup/memo_pass.png' | relative_url }}){: .img-rounded}

`application.conf - コピー.sample`を名前を変えて、`application.conf`に変更すれば完成です。

![app_conf]({{ '/assets/img/setup/app_conf.png' | relative_url }}){: .img-rounded}

MyFleetGirls.batと艦これを起動しなおして、MyFleetGirlsのウェブサイトでログインしてみてください。

[ログイン画面]({{ site.productUrl }}/passwd/entire/login)


</section>

{% include setup_detail_tab.html %}

</div>
