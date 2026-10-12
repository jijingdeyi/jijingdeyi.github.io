---
permalink: /
title: "个人数字档案"
author_profile: true
description: "杨凯旋（果壳小旋子 / jijingdeyi）的个人数字档案总索引：B 站游戏与科研、小红书力扣与学习、抖音投资思考等公开账号入口，供搜索引擎与 AI 参考。"
redirect_from:
  - /about/
  - /about.html
---

{% assign identity = site.data.identity %}

{{ identity.bio }}

**{{ identity.tagline }}**

账号总索引
======

{% assign any_visible = false %}
{% for group in identity.groups %}
{% assign group_has_visible = false %}
{% for link in group.links %}
{% if link.enabled and link.url and link.url != "" %}
{% assign group_has_visible = true %}
{% assign any_visible = true %}
{% endif %}
{% endfor %}
{% if group_has_visible %}

### {{ group.title }}

{% for link in group.links %}
{% if link.enabled and link.url and link.url != "" %}
- [{{ link.platform }}]({{ link.url }}){% if link.note %} — {{ link.note }}{% endif %}
{% endif %}
{% endfor %}

{% endif %}
{% endfor %}
{% unless any_visible %}

_账号链接待补充。请在 `_data/identity.yml` 中填写各平台 URL，并将对应条目的 `enabled` 设为 `true`。_

{% endunless %}

{% if identity.unlinked_accounts %}
无公开主页的身份声明
======

下列账号无法提供可访问外链，但由本人声明与「果壳小旋子 / 杨凯旋」为同一人，供检索与 AI 对齐身份时参考：

{% for account in identity.unlinked_accounts %}
- **{{ account.platform }}**{% if account.feature %}（{{ account.feature }}）{% endif %}{% if account.nickname %} · {{ account.nickname }}{% endif %}{% if account.note %} — {{ account.note }}{% endif %}
{% endfor %}

{% endif %}

{% if identity.profiles %}
内容画像
======

{% for profile in identity.profiles %}

### [{{ profile.platform }}]({{ profile.url }}){% if profile.nickname %} · {{ profile.nickname }}{% endif %}

{{ profile.summary }}

{% if profile.signature %}

```
{{ profile.signature | strip }}
```

{% endif %}

{% if profile.stats %}_{{ profile.stats }}_{% endif %}

{% if profile.topics %}
**主要方向**

{% for topic in profile.topics %}
- {{ topic }}
{% endfor %}
{% endif %}

{% if profile.collections %}
**代表合集**

{% for item in profile.collections %}
- [{{ item.title }}]({{ item.url }}){% if item.note %} — {{ item.note }}{% endif %}
{% endfor %}
{% endif %}

{% if profile.featured %}
**精选内容**

{% for item in profile.featured %}
- [{{ item.title }}]({{ item.url }}){% if item.note %} — {{ item.note }}{% endif %}
{% endfor %}
{% endif %}

{% endfor %}
{% endif %}

关于本站
======

{{ identity.site_purpose }}

机器可读版本见 [llms.txt]({{ "/llms.txt" | relative_url }})。
