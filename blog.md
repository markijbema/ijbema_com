---
layout: default
title: "Blog"
description: "My thoughts on software engineering, AI, etc"
---

<section class="page-hero">
  <div class="wrap">
    <h1>Blog</h1>
    <p class="page-hero-copy">We often hear about 10x engineers, and I don't know about that. But there are definitely 10x teams.
    It's important to take a step back once in a while and evaluate our tech and processes.</p>
  </div>
</section>

<section class="section">
  <div class="wrap narrow">
    <div class="post-list">
      {% for post in site.posts %}
        <article class="post-card">
          <p class="post-meta">{{ post.date | date: "%B %d, %Y" }}</p>
          <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
          <p>{{ post.excerpt | strip_html | truncatewords: 28 }}</p>
          <p class="post-card-link"><a href="{{ post.url | relative_url }}">Read post <span aria-hidden="true">&rarr;</span></a></p>
        </article>
      {% else %}
        <p>No posts yet.</p>
      {% endfor %}
    </div>
  </div>
</section>
