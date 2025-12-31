---
title: "Prognostic and Health Management(PHM)"
layout: single
permalink: /phm/
toc: false
---

### PHM 공부 내용을 정리한 글이며 아래의 전공 서적을 기반으로 작성되었습니다.
저작권 관련 문제가 있다면 아래의 이메일로 연락주세요.
dnz60ar20085@gmail.com
![전공서적_이미지]({{'/assets/images/phm/Prognostics and Health Management of Engineering Systems An Introduction_Nam-Ho Kim, Dawn An, Joo-Ho ChoiPermalink.jpeg' | relative_url}})
### Prognostics and Health Management of Engineering Systems An Introduction / Nam-Ho Kim, Dawn An, Joo-Ho Choi

{% assign items = site.phm | sort: "order" %}
<ul>
{% for doc in items %}
  <li><a href="{{ doc.url | relative_url }}">{{ doc.title }}</a></li>
{% endfor %}
</ul>
