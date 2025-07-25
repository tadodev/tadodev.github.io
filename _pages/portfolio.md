---
title: Portfolio
layout: single
permalink: /portfolio/
classes: wide
author_profile: true
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/portfolio-header.jpg
  caption: "Building solutions that matter"
excerpt: "Explore my projects that bridge engineering and software development."
toc: true
toc_sticky: true
---

Welcome to my portfolio! Here you'll find a collection of projects that showcase my journey from structural engineering to software development. Each project represents a step in my evolution as a developer and demonstrates how I apply engineering principles to software solutions.

## Featured Projects

<div class="portfolio-grid">
{% assign featured_projects = site.portfolio | where: "featured", true %}
{% for project in featured_projects %}
  <div class="portfolio-item">
    {% if project.header.teaser %}
      <div class="portfolio-item__image">
        <img src="{{ project.header.teaser | relative_url }}" alt="{{ project.title }}">
        <div class="portfolio-item__overlay">
          <a href="{{ project.url | relative_url }}" class="btn btn--light-outline">View Project</a>
        </div>
      </div>
    {% endif %}
    <div class="portfolio-item__content">
      <h3><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h3>
      <p>{{ project.excerpt | markdownify | strip_html | truncatewords: 20 }}</p>
      
      {% if project.tech_stack %}
        <div class="tech-stack">
          {% for tech in project.tech_stack limit:5 %}
            <span class="tech">{{ tech }}</span>
          {% endfor %}
        </div>
      {% endif %}
    </div>
  </div>
{% endfor %}
</div>

## All Projects

<div class="portfolio-grid">
{% assign all_projects = site.portfolio | sort: 'date' | reverse %}
{% for project in all_projects %}
  <div class="portfolio-item">
    {% if project.header.teaser %}
      <div class="portfolio-item__image">
        <img src="{{ project.header.teaser | relative_url }}" alt="{{ project.title }}">
        <div class="portfolio-item__overlay">
          <a href="{{ project.url | relative_url }}" class="btn btn--light-outline">View Project</a>
        </div>
      </div>
    {% endif %}
    <div class="portfolio-item__content">
      <h3><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h3>
      <p>{{ project.excerpt | markdownify | strip_html | truncatewords: 20 }}</p>

      {% if project.tech_stack %}
        <div class="tech-stack">
          {% for tech in project.tech_stack limit:5 %}
            <span class="tech">{{ tech }}</span>
          {% endfor %}
        </div>
      {% endif %}
    </div>
  </div>
{% endfor %}
</div>

<style>
.portfolio-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
  margin-top: 2rem;
}

.portfolio-item {
  background: #fff;
  border: 1px solid #e5e5e5;
  border-radius: 8px;
  overflow: hidden;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.portfolio-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

.portfolio-item__image {
  position: relative;
}

.portfolio-item__image img {
  width: 100%;
  height: auto;
  display: block;
}

.portfolio-item__overlay {
  position: absolute;
  bottom: 10px;
  left: 10px;
}

.portfolio-item__content {
  padding: 1rem;
}

.tech-stack {
  margin-top: 0.5rem;
}

.tech {
  display: inline-block;
  background-color: #f2f2f2;
  color: #333;
  font-size: 0.85rem;
  padding: 0.25rem 0.5rem;
  border-radius: 4px;
  margin-right: 0.4rem;
  margin-top: 0.4rem;
}
</style>

---

Want to learn more about a project or collaborate on something new?  
[Contact me](/contact/) — I'd love to hear from you!
