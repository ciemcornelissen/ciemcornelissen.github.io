---
layout: page
title: talks
permalink: /talks/
description: Recorded talks and invited presentations currently available on YouTube.
nav: true
nav_order: 9
---

<!-- _pages/talks.md -->
<p>
  Explore recent presentations, panels, and invited talks. New recordings are added as they become available.
</p>

{% assign talks = site.data.talks | sort: "date" | reverse %}

<div class="talks-grid">
  {% for talk in talks %}
  <article class="talk-card">
    <header>
      <h2 class="talk-title">{{ talk.title }}</h2>
      {% if talk.event or talk.date %}
      <p class="talk-meta">
        {% if talk.event %}<span class="talk-event">{{ talk.event }}</span>{% endif %}
        {% if talk.event and talk.date %} &middot; {% endif %}
        {% if talk.date %}<time datetime="{{ talk.date | date_to_xmlschema }}">{{ talk.date | date: "%B %-d, %Y" }}</time>{% endif %}
      </p>
      {% endif %}
    </header>
    {% if talk.description %}
    <p class="talk-description">{{ talk.description }}</p>
    {% endif %}
    {% if talk.video_id %}
    <div class="talk-video">
      <iframe
        src="https://www.youtube.com/embed/{{ talk.video_id }}"
        title="{{ talk.title | escape }}"
        loading="lazy"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        allowfullscreen
      ></iframe>
    </div>
    {% endif %}
    {% if talk.youtube_url %}
    <p class="talk-links"><a href="{{ talk.youtube_url }}" target="_blank" rel="noopener">Watch on YouTube</a></p>
    {% endif %}
  </article>
  {% endfor %}
</div>
