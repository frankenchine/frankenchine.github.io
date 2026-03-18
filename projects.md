---
layout: page
title: Projects
permalink: /projects/
---

Here are a few things I’m building and maintaining. For the latest updates, see [AI Weekly]({{ '/weekly/' | relative_url }}).

{% assign all_projects = site.data.projects %}

{% if all_projects and all_projects.size > 0 %}
  <div class="grid">
    {% for p in all_projects %}
      <section class="card card--wide">
        <div class="card__header">
          <h2 style="margin:0">
            <a href="{{ p.url }}" target="_blank" rel="noreferrer noopener">{{ p.name }}</a>
          </h2>
          {% if p.status %}
            <span class="pill pill--{{ p.status | escape }}">{{ p.status }}</span>
          {% endif %}
        </div>

        {% if p.desc %}<p class="muted" style="margin-top:0">{{ p.desc }}</p>{% endif %}

        {% if p.highlights %}
          <ul>
            {% for h in p.highlights %}
              <li>{{ h }}</li>
            {% endfor %}
          </ul>
        {% endif %}

        {% if p.tags %}
          <div class="tags">
            {% for t in p.tags %}
              <span class="tag">{{ t }}</span>
            {% endfor %}
          </div>
        {% endif %}
      </section>
    {% endfor %}
  </div>
{% else %}
  <p class="muted">Edit <code>_data/projects.yml</code> to add projects.</p>
{% endif %}

