---
layout: home
author_profile: true
classes: wide
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/header-bg.jpg
  actions:
    - label: "View My Work"
      url: "/portfolio/"
  caption: "Building bridges between engineering and technology"
excerpt: "Welcome to my digital space where structural engineering meets software development. Explore my journey, projects, and insights."
---

<div class="intro-section">
  <div class="intro-content">
    <p>As a structural engineer transitioning into software development, I bring a unique perspective to problem-solving. I combine analytical thinking with creative coding to build robust, scalable solutions.</p>
  </div>
</div>

## 🚀 Featured Projects

<div class="card-grid">
  {% assign featured_projects = site.portfolio | where: "featured", true | limit: 3 %}
  {% for project in featured_projects %}
  <div class="card">
    {% if project.header.teaser %}
    <div class="card-image">
      <img src="{{ project.header.teaser | relative_url }}" alt="{{ project.title }}">
    </div>
    {% endif %}
    <div class="card-content">
      <h3 class="card-title">
        <a href="{{ project.url | relative_url }}">{{ project.title }}</a>
      </h3>
      <p class="card-excerpt">{{ project.excerpt | markdownify | strip_html | truncatewords: 25 }}</p>
      
      {% if project.tech_stack %}
      <div class="tech-stack">
        {% for tech in project.tech_stack limit:4 %}
        <span class="tech-tag">{{ tech }}</span>
        {% endfor %}
      </div>
      {% endif %}

      <div class="project-links">
        <a href="{{ project.url | relative_url }}" class="btn btn--info btn--small">Learn More</a>
        {% if project.github_url %}
        <a href="{{ project.github_url }}" class="btn btn--inverse btn--small">
          <i class="fab fa-github"></i> GitHub
        </a>
        {% endif %}
        {% if project.demo_url %}
        <a href="{{ project.demo_url }}" class="btn btn--primary btn--small">
          <i class="fas fa-external-link-alt"></i> Demo
        </a>
        {% endif %}
      </div>
    </div>
  </div>
  {% endfor %}
</div>

<div class="text-center" style="margin-top: 3rem;">
  <a href="/portfolio/" class="btn btn--primary btn--large">View All Projects</a>
</div>

---

## 📰 Featured Articles

<div class="card-grid">
  {% assign featured_posts = site.posts | where: "featured", true | limit: 3 %}
  {% for post in featured_posts %}
  <div class="card">
    <div class="card-content">
      <div class="post-meta">
        <time datetime="{{ post.date | date_to_xmlschema }}" class="post-date">
          {{ post.date | date: "%B %d, %Y" }}
        </time>
      </div>
      <h3 class="card-title">
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h3>
      <p class="card-excerpt">{{ post.excerpt | markdownify | strip_html | truncatewords: 25 }}</p>
      
      {% if post.tags %}
      <div class="tech-stack">
        {% for tag in post.tags limit:3 %}
        <span class="tech-tag">{{ tag }}</span>
        {% endfor %}
      </div>
      {% endif %}
      
      <div class="read-time">
        {% include read-time.html %}
      </div>
    </div>
  </div>
  {% endfor %}
</div>

<div class="text-center" style="margin-top: 3rem;">
  <a href="/posts/" class="btn btn--primary btn--large">View All Articles</a>
</div>

---

## 📝 Latest Blog Posts

<div class="recent-posts">
  {% for post in site.posts limit:5 %}
  <article class="post-preview">
    <h3 class="post-title">
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </h3>
    <p class="post-excerpt">{{ post.excerpt | markdownify | strip_html | truncatewords: 30 }}</p>
    <div class="post-meta">
      <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
      {% if post.read_time %} • {% include read-time.html %}{% endif %}
      {% if post.tags %}
      • {% for tag in post.tags limit:2 %}
        <span class="tag">{{ tag }}</span>{% unless forloop.last %}, {% endunless %}
      {% endfor %}
      {% endif %}
    </div>
  </article>
  {% endfor %}
</div>

<style>
/* Home page specific styles */
.intro-section {
  background: white;
  padding: 3rem 0;
  margin: 2rem 0;
  border-radius: 12px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
}

.intro-content {
  max-width: 800px;
  margin: 0 auto;
  text-align: center;
}

.intro-content p {
  font-size: 1.2rem;
  color: #4a5568;
  line-height: 1.8;
  margin: 0;
}

/* Card Grid Layout */
.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
  margin: 2rem 0;
}

@media (min-width: 1024px) {
  .card-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

@media (max-width: 768px) {
  .card-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
}

.card {
  background: white;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  border: 1px solid #e2e8f0;
}

.card:hover {
  transform: translateY(-8px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
}

.card-image {
  width: 100%;
  height: 200px;
  overflow: hidden;
}

.card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.card:hover .card-image img {
  transform: scale(1.05);
}

.card-content {
  padding: 1.5rem;
}

.card-title {
  font-size: 1.4rem;
  font-weight: 600;
  margin-bottom: 0.75rem;
  color: #2d3748;
  line-height: 1.3;
}

.card-title a {
  text-decoration: none;
  color: inherit;
  transition: color 0.2s ease;
}

.card-title a:hover {
  color: #667eea;
}

.card-excerpt {
  color: #718096;
  margin-bottom: 1rem;
  line-height: 1.6;
}

.post-meta {
  margin-bottom: 1rem;
}

.post-date {
  color: #667eea;
  font-weight: 500;
  font-size: 0.875rem;
}

/* Tech Stack Tags */
.tech-stack {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-bottom: 1rem;
}

.tech-tag {
  display: inline-block;
  background: #edf2f7;
  color: #4a5568;
  padding: 0.25rem 0.75rem;
  font-size: 0.75rem;
  border-radius: 20px;
  font-weight: 500;
}

.tag {
  display: inline-block;
  background: #f2f2f2;
  color: #444;
  padding: 0.25rem 0.5rem;
  font-size: 0.75rem;
  border-radius: 4px;
  margin-right: 0.25rem;
}

/* Project Links */
.project-links {
  display: flex;
  gap: 0.5rem;
  flex-wrap: wrap;
}

.read-time {
  font-size: 0.875rem;
  color: #a0aec0;
}

/* Recent Posts Section */
.recent-posts {
  max-width: 800px;
  margin: 0 auto;
}

.post-preview {
  padding: 1.5rem 0;
  border-bottom: 1px solid #e2e8f0;
}

.post-preview:last-child {
  border-bottom: none;
}

.post-title {
  font-size: 1.5rem;
  margin-bottom: 0.5rem;
}

.post-title a {
  text-decoration: none;
  color: #2d3748;
  transition: color 0.2s ease;
}

.post-title a:hover {
  color: #667eea;
}

.post-excerpt {
  color: #718096;
  margin-bottom: 0.75rem;
  line-height: 1.6;
}

.post-meta {
  font-size: 0.875rem;
  color: #a0aec0;
}

/* Button Styles */
.btn--large {
  padding: 14px 28px;
  font-size: 1.1rem;
  border-radius: 8px;
}

.text-center {
  text-align: center;
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .intro-content p {
    font-size: 1.1rem;
  }
  
  .card-title {
    font-size: 1.2rem;
  }
  
  .post-title {
    font-size: 1.3rem;
  }
}
</style>