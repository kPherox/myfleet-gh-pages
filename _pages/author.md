---
layout: page
title: 作者情報
permalink: /author
---

{% for hash in site.data.contributors %}
{% assign contributor = hash[1] %}
{% assign account = contributor %}
## {{ contributor.name }}

{{ contributor.comment }}

- [{{ account.name }}]({{ site.productUrl }}/user/{{ account.id }})

{% for link in contributor.links %}
- [{{ link.name }}]({{ link.url }}){{ link.description | default: "" }}
{% endfor %}


{% endfor %}


## Contributorの方へ

MyFleetGirlsにPull Requestしたことあって、情報載せたい人は、上に自分の情報を追記して[myfleet_web](https://github.com/ttdoda/myfleet_web)にPull Request投げてください


