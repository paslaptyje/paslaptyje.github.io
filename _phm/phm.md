---
title: "Prognostic and Health Management(PHM) 목차"
layout: single
permalink: /phm/
toc: false
---
# Prognostic and Health Management(PHM)
### PHM 공부 내용을 정리한 글이며 아래의 전공 서적을 기반으로 작성되었습니다.
![전공서적_이미지]({{'/assets/images/phm/Prognostics and Health Management of Engineering Systems An Introduction_Nam-Ho Kim, Dawn An, Joo-Ho ChoiPermalink.jpeg' | relative_url}})
### Prognostics and Health Management of Engineering Systems An Introduction / Nam-Ho Kim, Dawn An, Joo-Ho Choi

{% assign items = site.phm | sort: "order" %}
<ul>
{% for doc in items %}
  <li><a href="{{ doc.url | relative_url }}">{{ doc.title }}</a></li>
{% endfor %}
</ul>
