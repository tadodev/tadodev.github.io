---
layout: home
author_profile: true
header:
  overlay_color: "#0078d4"
  overlay_filter: "0.4"
  overlay_image: /assets/images/header-bg.jpg
  actions:
    - label: "View Portfolio"
      url: "/portfolio/"
      btn_class: "btn--light-outline btn--large"
  caption: "Engineering meets Software Development"
excerpt: "Structural Engineer turned Full-Stack Developer. Building reliable software with engineering precision."
---

<section class="homepage-section">
  <h2 class="homepage-section__title">Featured Projects</h2>
  
  <div class="cards-grid">
    {% assign featured_projects = site.portfolio | where: "featured", true | limit: 3 %}
    {% for project in featured_projects %}
    <article class="feature-card">
      {% if project.header.teaser %}
      <div class="feature-card__image">
        <img src="{{ project.header.teaser | relative_url }}" alt="{{ project.title }}">
      </div>
      {% endif %}
      
      <div class="feature-card__content">
        <h3 class="feature-card__title">
          <a href="{{ project.url | relative_url }}">{{ project.title }}</a>
        </h3>
        
        <p class="feature-card__excerpt">{{ project.excerpt | strip_html | truncatewords: 20 }}</p>
        
        {% if project.tech_stack %}
        <div class="feature-card__tags">
          {% for tech in project.tech_stack limit:4 %}
          <span class="feature-card__tag">{{ tech }}</span>
          {% endfor %}
        </div>
        {% endif %}
        
        <div class="feature-card__links">
          <a href="{{ project.url | relative_url }}" class="feature-card__link">Learn More</a>
          {% if project.github_url %}
          <a href="{{ project.github_url }}" class="feature-card__link feature-card__link--secondary">GitHub</a>
          {% endif %}
        </div>
      </div>
    </article>
    {% endfor %}
  </div>
  
  <div style="text-align: center; margin-top: 2rem;">
    <a href="/portfolio/" class="feature-card__link" style="padding: 0.75rem 2rem;">View All Projects</a>
  </div>
</section>

<section class="homepage-section">
  <h2 class="homepage-section__title">Featured Articles</h2>
  
  <div class="cards-grid">
    {% assign featured_posts = site.posts | where: "featured", true | limit: 3 %}
    {% for post in featured_posts %}
    <article class="feature-card">
      {% if post.header.teaser %}
      <div class="feature-card__image">
        <img src="{{ post.header.teaser | relative_url }}" alt="{{ post.title }}">
      </div>
      {% endif %}
      
      <div class="feature-card__content">
        <div class="feature-card__meta">
          <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
          {% if post.read_time %} • {% include read-time.html %}{% endif %}
        </div>
        
        <h3 class="feature-card__title">
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </h3>
        
        <p class="feature-card__excerpt">{{ post.excerpt | strip_html | truncatewords: 20 }}</p>
        
        {% if post.tags %}
        <div class="feature-card__tags">
          {% for tag in post.tags limit:3 %}
          <span class="feature-card__tag">{{ tag }}</span>
          {% endfor %}
        </div>
        {% endif %}
        
        <div class="feature-card__links">
          <a href="{{ post.url | relative_url }}" class="feature-card__link">Read More</a>
        </div>
      </div>
    </article>
    {% endfor %}
  </div>
  
  <div style="text-align: center; margin-top: 2rem;">
    <a href="/posts/" class="feature-card__link" style="padding: 0.75rem 2rem;">View All Articles</a>
  </div>
</section>