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
<ul class="pager"><li class="previous"><a href="#"><span aria-hidden="true">←</span> Newer</a></li><li class="next"><a href="#">Older <span aria-hidden="true">→</span></a></li></ul>
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
<script>functions.push(()=>{var params=new URLSearchParams(window.location.search),page=(parseInt(params.get('page'))||1)-1;$('#page-'+(page+1)).css('display','');if(page<=0){$('.pager>.previous').addClass('disabled');}else if(page>={{ releasesPages }}){$('.pager>.next').addClass('disabled');}$('.pager>.previous').click((e)=>{e.preventDefault();if(page===0){return;}$('#page-'+(page+1)).css('display','none');page-=1;$('#page-'+(page+1)).css('display','');if(page<=0){$('.pager>.previous').addClass('disabled');}if(page<{{ releasesPages }}){$('.pager>.next').removeClass('disabled');}params.set('page',page+1);window.history.replaceState({},'',`${location.pathname}?${params}`);return;});$('.pager>.next').click((e)=>{e.preventDefault();if(page==={{ releasesPages }}){return;}$('#page-'+(page+1)).css('display','none');page+=1;$('#page-'+(page+1)).css('display','');if(page>={{ releasesPages }}){$('.pager>.next').addClass('disabled');}if(page>0){$('.pager>.previous').removeClass('disabled');}params.set('page',page+1);window.history.replaceState({},'',`${location.pathname}?${params}`);return;});});</script>
</section>
