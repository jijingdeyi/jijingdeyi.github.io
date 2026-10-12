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

<div class="identity-home">

<div class="identity-home__lead">
{{ identity.bio | markdownify }}
</div>

<p class="identity-home__tagline">{{ identity.tagline }}</p>

<h2 class="identity-home__section-title">账号</h2>

<ul class="identity-card-list">
{% for profile in identity.profiles %}
  <li class="identity-card">
    <div class="identity-card__main">
      <a class="identity-card__title" href="{{ "/" | append: profile.id | append: "/" | relative_url }}">{{ profile.platform }}</a>
      <p class="identity-card__blurb">{{ profile.blurb }}</p>
    </div>
    <div class="identity-card__links">
      <a href="{{ "/" | append: profile.id | append: "/" | relative_url }}">站内详情</a>
      <a href="{{ profile.url }}">平台主页</a>
    </div>
  </li>
{% endfor %}
  <li class="identity-card">
    <div class="identity-card__main">
      <a class="identity-card__title" href="https://github.com/jijingdeyi">GitHub</a>
      <p class="identity-card__blurb">代码与本站仓库</p>
    </div>
    <div class="identity-card__links">
      <a href="https://github.com/jijingdeyi">打开仓库</a>
    </div>
  </li>
</ul>

{% if identity.unlinked_accounts %}
{% for account in identity.unlinked_accounts %}
<p class="identity-note">
  <strong>{{ account.platform }}{% if account.feature %}（{{ account.feature }}）{% endif %}</strong>
  · {{ account.nickname }}
  {% if account.note %} — {{ account.note }}{% endif %}
</p>
{% endfor %}
{% endif %}

<p class="identity-home__foot">
  各平台详情见上方卡片；给程序看的摘要见
  <a href="{{ "/llms.txt" | relative_url }}">llms.txt</a>。
</p>

</div>
