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

- <span class="label label-primary">Common</span>は全体のバージョンアップで比較的大きい変更が多いです
- <span class="label label-warning">Client</span>は各ユーザのProxy Serverのバージョンアップ
- <span class="label label-info">Server</span>はサーバ側のバージョンアップです

{% assign releases = '' | split: '' %}
{% for releaseHash in site.data.releases %}{% assign releases = releases | unshift: releaseHash[1] %}{% endfor %}
{% assign releases = releases | sort: 'date' | reverse %}{% assign nextVersion = 'master' %}{% assign offset = 0 %}{% assign limit = 10 %}
<ul class="pager">
<li class="previous disabled">
    <a href="#"><span aria-hidden="true">←</span> Newer</a>
</li>
<li class="next">
    <a href="#">Older <span aria-hidden="true">→</span></a>
</li>
</ul>
<div id="pagination">
</div>
{% assign releasesPages = releases | size | divided_by: limit %}{% for i in (0..releasesPages) %}
<div id="page-{{ i | plus: 1}}" style="display:none" markdown="1">
{% for release in releases limit:limit offset:offset %}
{% assign common = release.changes.common %}{% assign client = release.changes.client %}{% assign server = release.changes.server %}

### [Ver{{ release.version }} ({{ release.date | date: "%Y-%m-%d" }})](https://github.com/ttdoda/MyFleetGirls/compare/v{{ release.version }}...{{ nextVersion }})

{% for change in common %}
- <span class="label label-primary">Common</span>{{ change.description }}{% endfor %}{% for change in client %}
- <span class="label label-warning">Client</span>{{ change.description }}{% endfor %}{% for change in server %}
- <span class="label label-info">Server</span>{{ change.description }}{% endfor %}

{% assign nextVersion = 'v' | append: release.version %}
{% endfor %}
</div>
{% assign offset = offset | plus: limit %}{% endfor %}
<script>functions.push(()=>{var page=0;$('#page-'+(page+1)).css('display','');$('.pager>.previous').click((e)=>{e.preventDefault();if(page===0){return;}$('#page-'+(page+1)).css('display','none');page=page-1;$('#page-'+(page+1)).css('display','');if(page===0){$('.pager>.previous').addClass('disabled');}if(page!=={{ releasesPages }}){$('.pager>.next').removeClass('disabled');}return;});$('.pager>.next').click((e)=>{e.preventDefault();if(page==={{ releasesPages }}){return;}$('#page-'+(page+1)).css('display','none');page=page+1;$('#page-'+(page+1)).css('display','');if(page==={{ releasesPages }}){$('.pager>.next').addClass('disabled');}if(page!==0){$('.pager>.previous').removeClass('disabled');}return;});});</script>

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
