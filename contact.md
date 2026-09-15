---
layout: default
title: "Contact"
description: "[PLACEHOLDER: A short invitation to get in touch.]"
---

<section class="page-hero">
  <div class="wrap narrow">
    <p class="eyebrow">Contact</p>
    <h1>Let's talk about your team's way of working.</h1>
    <p class="page-hero-copy">[PLACEHOLDER: Add a brief note about the kind of conversation that is welcome and what happens after someone gets in touch.]</p>
  </div>
</section>

<section class="section">
  <div class="wrap narrow">
    <div class="contact-options">
      <div>
        <p class="contact-label">Email</p>
        <p><a class="contact-link" href="mailto:{{ site.email }}">{{ site.email }}</a></p>
        <p class="muted">[PLACEHOLDER: Add your preferred email address in _config.yml.]</p>
      </div>
      <div>
        <p class="contact-label">LinkedIn</p>
        <p>{% if site.linkedin_url != "" %}<a class="contact-link" href="{{ site.linkedin_url }}">LinkedIn profile</a>{% else %}<span class="contact-link">[PLACEHOLDER: Your LinkedIn profile]</span>{% endif %}</p>
        <p class="muted">[PLACEHOLDER: Add your LinkedIn profile URL in _config.yml.]</p>
      </div>
    </div>
    <div class="contact-note">
      <h2>Before you write</h2>
      <p>[PLACEHOLDER: Optionally list the context that helps you respond usefully, such as team size, current challenge, timeline, or whether the work is remote or onsite.]</p>
    </div>
  </div>
</section>
