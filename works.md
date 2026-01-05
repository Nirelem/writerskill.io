---
layout: default
title: Works
---

<section class="genre-filter">
  <strong>Filter by genre:</strong>

  <a href="#all">All</a>

  {% assign genres = site.posts | map: "genre" | uniq | sort %}
  {% for genre in genres %}
    <a href="#{{ genre | slugify }}">{{ genre }}</a>
  {% endfor %}
</section>

<hr>

<section id="all">
  {% for post in site.posts %}
    <article class="work-card">
      <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
      <p class="meta">
        by {{ post.penname | default: post.author }} •
        {{ post.genre }} •
        {{ post.date | date: "%B %d, %Y" }}
      </p>
      <p>{{ post.excerpt }}</p>
      <a class="read-more" href="{{ post.url }}">Read →</a>
    </article>
  {% endfor %}
</section>

{% for genre in genres %}
  <section id="{{ genre | slugify }}">
    <h2>{{ genre }}</h2>
    
    {% for post in site.posts %}
      {% if post.genre == genre %}
        <article class="work-card">
          <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
          <p class="meta">
            by {{ post.penname | default: post.author }} •
            {{ post.date | date: "%B %d, %Y" }}
          </p>
          <p>{{ post.excerpt }}</p>
          <a class="read-more" href="{{ post.url }}">Read →</a>
        </article>
      {% endif %}
    {% endfor %}
  </section>
{% endfor %}
