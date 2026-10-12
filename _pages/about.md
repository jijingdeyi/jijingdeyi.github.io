---
permalink: /
title: "关于"
author_profile: true
description: "杨凯旋（果壳小旋子）：算法工程师。公开账号索引。"
redirect_from:
  - /about/
  - /about.html
---

{% assign identity = site.data.identity %}

{{ identity.bio }}

**{{ identity.tagline }}**

账号
======

{% for profile in identity.profiles %}
- [{{ profile.platform }}]({{ profile.url }}){% if profile.blurb %} — {{ profile.blurb }}{% endif %} · [详情]({{ "/accounts/" | relative_url }}#{{ profile.id }})
{% endfor %}
- [GitHub](https://github.com/jijingdeyi) — 代码与本站仓库
{% for account in identity.unlinked_accounts %}
- {{ account.platform }}{% if account.feature %}（{{ account.feature }}）{% endif %} · {{ account.nickname }}{% if account.note %} — {{ account.note }}{% endif %}
{% endfor %}

更多平台说明、合集和精选内容，见 [账号详情]({{ "/accounts/" | relative_url }})。  
给程序看的摘要：[llms.txt]({{ "/llms.txt" | relative_url }})。
