---
layout: default
title: "Blog"
description: "[PLACEHOLDER: A short description of the topics covered in this blog.]"
---

<section class="page-hero">
  <div class="wrap">
    <p class="eyebrow">Blog</p>
    <h1>Notes on software delivery and engineering practice.</h1>
    <p class="page-hero-copy">[PLACEHOLDER: Add a sentence about what readers can expect from future posts.]</p>
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
        <p>No posts yet. Add a Markdown file to <code>_posts/</code> to publish your first post.</p>
      {% endfor %}
    </div>
  </div>
</section>
