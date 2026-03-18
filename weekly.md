---
layout: page
title: AI Weekly
permalink: /weekly/
---

每周 AI 科技动态（偏工程实践与 Agent/LLM 应用）。新增周报只需要在 `_posts/` 下创建 `YYYY-MM-DD-ai-weekly.md`，并设置 `categories: [weekly]`。

{% assign weekly_posts = site.categories.weekly %}

{% if weekly_posts and weekly_posts.size > 0 %}
  <div class="timeline">
    {% for post in weekly_posts %}
      <article class="timeline__item">
        <div class="timeline__meta">
          <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y-%m-%d" }}</time>
          {% if post.tags and post.tags.size > 0 %}
            <span class="timeline__tags">
              {% for t in post.tags limit: 6 %}
                <span class="tag">{{ t }}</span>
              {% endfor %}
            </span>
          {% endif %}
        </div>
        <h2 class="timeline__title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
        {% if post.excerpt %}
          <p class="muted">{{ post.excerpt | strip_html | strip_newlines | truncate: 180 }}</p>
        {% endif %}
      </article>
    {% endfor %}
  </div>
{% else %}
  <p class="muted">还没有周报。先从创建第一篇开始吧。</p>
{% endif %}

