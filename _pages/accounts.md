---
permalink: /accounts/
title: "账号详情"
author_profile: true
description: "杨凯旋（果壳小旋子）各平台账号说明、合集与精选内容。"
---

{% assign identity = site.data.identity %}

这里是各平台的展开说明。只想快速找链接，回 [首页]({{ "/" | relative_url }}) 即可。

{% for profile in identity.profiles %}

## {{ profile.platform }} · {{ profile.nickname }}
{: #{{ profile.id }}}

主页：[{{ profile.url }}]({{ profile.url }}){% if profile.short_url %} · [短链]({{ profile.short_url }}){% endif %}

{{ profile.summary }}

{% if profile.signature %}
> {{ profile.signature | strip }}
{% endif %}

{% if profile.stats %}_{{ profile.stats }}_{% endif %}

{% if profile.topics %}
{% for topic in profile.topics %}
- {{ topic }}
{% endfor %}
{% endif %}

{% if profile.collections %}
**合集 / 专栏**

{% for item in profile.collections %}
- [{{ item.title }}]({{ item.url }}){% if item.note %}（{{ item.note }}）{% endif %}
{% endfor %}
{% endif %}

{% if profile.featured %}
**可以先看**

{% for item in profile.featured %}
- [{{ item.title }}]({{ item.url }}){% if item.note %}（{{ item.note }}）{% endif %}
{% endfor %}
{% endif %}

---

{% endfor %}

{% if identity.unlinked_accounts %}
## 没有公开主页的账号

{% for account in identity.unlinked_accounts %}
- **{{ account.platform }}**{% if account.feature %}（{{ account.feature }}）{% endif %} · {{ account.nickname }} — {{ account.note }}
{% endfor %}
{% endif %}
