---
layout: page
title: 更新情報
permalink: /change
---

<section id="change_log" markdown="1">

## [Change Log](https://github.com/ttdoda/MyFleetGirls/releases)

現行のChange LogはGitHubのReleaseで管理しているのでこちらをご覧下さい


</section>

<section id="old_change_log" markdown="1">

## 過去のChange Log

- <span class="label label-warning" style="width:68px;display:inline-block;padding:.4em;margin-right:.3em;">Client</span>は各ユーザのProxy Serverのバージョンアップ
- <span class="label label-info" style="width:68px;display:inline-block;padding:.4em;margin-right:.3em;">Server</span>はサーバ側のバージョンアップです
- <span class="label label-primary" style="width:68px;display:inline-block;padding:.4em;margin-right:.3em;">Common</span>は全体のバージョンアップで比較的大きい変更が多いです

{% for hash in site.data.releases %}{% assign release = hash[1] %}
{% assign common = release.changes.common %}{% assign client = release.changes.client %}{% assign server = release.changes.server %}
### Ver{{ release.version }}

{% for change in common %}- <span class="label label-primary" style="width:68px;display:inline-block;padding:.4em;margin-right:.3em;">Common</span>{{ change.description }}
{% endfor %}{% for change in client %}- <span class="label label-warning" style="width:68px;display:inline-block;padding:.4em;margin-right:.3em;">Client</span>{{ change.description }}
{% endfor %}{% for change in server %}- <span class="label label-info" style="width:68px;display:inline-block;padding:.4em;margin-right:.3em;">Server</span>{{ change.description }}
{% endfor %}

{% endfor %}




### Ver0.8.9

- <span class="label label-info">Server</span>艦娘のConditionに色付け
- <span class="label label-info">Server</span>その他細かい見せ方の修正


### Ver0.8.8

- <span class="label label-info">Server</span>艦娘名から建造レシピを検索する機能を追加
- <span class="label label-info">Server</span>艦隊リストを表示


### Ver0.8.7

- <span class="label label-info">Server</span>提督検索機能を追加


### Ver0.8.6

- <span class="label label-info">Server</span>装備所持艦娘リストを追加


### Ver0.8.5

- <span class="label label-info">Server</span>装備リストを追加


### Ver0.8.4

- <span class="label label-info">Server</span>建造統計画面を改良


### Ver0.8.3

- <span class="label label-info">Server</span>建造統計画面の追加
- <span class="label label-info">Server</span>建造・開発のPagingを追加


### Ver0.8.2

- <span class="label label-info">Server</span>Tweetボタンを追加


### Ver0.8.1

- <span class="label label-info">Server</span>各艦娘詳細情報を追加


### Ver0.8.0

- <span class="label label-primary">Common</span>装備情報を表示


### Ver0.7.0

- <span class="label label-primary">Common</span>海域進捗を表示
- <span class="label label-info">Server</span>routesのこまいところを修正


### Ver0.6.3

- <span class="label label-info">Server</span>navbar表示を追加
- <span class="label label-info">Server</span>画像URLにHEAD Methodを実装


### Ver0.6.2

- <span class="label label-warning">Client</span>建造・開発履歴が更新されないバグを修正


### Ver0.6.1

- <span class="label label-info">Server</span>嫁艦が間違っているバグを修正
- <span class="label label-warning">Client</span>初期設定のurl.postをponkotuy.com:9003に変更


### Ver0.6.0

- <span class="label label-info">Server</span>嫁艦・旗艦情報表示を追加
- <span class="label label-warning">Client</span>画像upload機能を追加
- <span class="label label-info">Server</span>ユーザページのURLを分離


### Ver0.5.1

- <span class="label label-info">Server</span>装備開発履歴に旗艦の表示を追加


### Ver0.5.0

- <span class="label label-warning">Client</span>Postできない致命的なバグを修正
- <span class="label label-warning">Client</span>改の画像が異なる場合は別で中破画像の有無が付くように


### Ver0.4.1

- <span class="label label-primary">Common</span>Master登録者を追加


### Ver0.4.0

- <span class="label label-primary">Common</span>艦船・装備図鑑を実装


### Ver0.3.1

- <span class="label label-info">Server</span>zipファイルの中身変更


### Ver0.3.0

- <span class="label label-primary">Common</span>装備開発履歴を実装


### Ver0.2.1

- <span class="label label-info">Server</span>zipファイルを追加


### Ver0.2.0

- <span class="label label-warning">Client</span>艦これサーバ過負荷時にTimeoutする問題を多分修正
- <span class="label label-info">Server</span>バージョン情報表示
- <span class="label label-info">Server</span>Change Log付与


### Ver0.1.0

- <span class="label label-primary">Common</span>バージョン付与


### Ver0.1.0-SNAPSHOT

- <span class="label label-primary">Common</span>Release Version


</section>
