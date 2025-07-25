---
layout: home
author_profile: true
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/header-bg.jpg
  actions:
    - label: "View My Work"
      url: "/portfolio/"
  caption: "Building bridges between engineering and technology"
excerpt: "Welcome to my digital space where structural engineering meets software development. Explore my journey, projects, and insights."
intro: 
  - excerpt: 'As a structural engineer transitioning into software development, I bring a unique perspective to problem-solving. I combine analytical thinking with creative coding to build robust, scalable solutions.'
feature_row_about:
  - image_path: /assets/images/engineering-unsplash.jpg
    alt: "Engineering Background"
    title: "Engineering Foundation"
    excerpt: "Years of experience in structural engineering have taught me the importance of precision, safety, and systematic thinking."
    url: "/about/"
    btn_label: "Learn More"
    btn_class: "btn--primary"
  - image_path: /assets/images/code-unsplash.jpg
    alt: "Software Development"  
    title: "Software Development"
    excerpt: "Passionate about creating clean, efficient code and exploring new technologies to solve real-world problems."
    url: "/portfolio/"
    btn_label: "View Projects"
    btn_class: "btn--primary"
  - image_path: /assets/images/opensource-unsplash.jpg
    alt: "Open Source"
    title: "Open Source Contributor"
    excerpt: "Believe in the power of community-driven development and contributing to projects that make a difference."
    url: "https://github.com/tadodev"
    btn_label: "GitHub Profile"
    btn_class: "btn--primary"
---

{% include feature_row id="intro" type="center" %}
{% include feature_row id="feature_row_about" %}

---

## 📰 Featured Articles

<section class="card-grid">
  {% assign featured_posts = site.posts | where: "featured", true | limit: 3 %}
  {% for post in featured_posts %}
    <article class="card">
      <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <p>{{ post.excerpt | markdownify | strip_html | truncatewords: 25 }}</p>
      <p class="card-meta">
        <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
        {% if post.tags %}
          • {% for tag in post.tags limit:2 %}
            <span class="tag">{{ tag }}</span>{% unless forloop.last %}, {% endunless %}
          {% endfor %}
        {% endif %}
      </p>
    </article>
  {% endfor %}
</section>

<div class="text-center">
  <a href="/posts/" class="btn btn--primary">View All Articles</a>
</div>

---

## 🚀 Featured Projects

<section class="card-grid">
  {% assign featured_projects = site.portfolio | where: "featured", true | limit: 3 %}
  {% for project in featured_projects %}
    <article class="card">
      {% if project.header.teaser %}
        <img src="{{ project.header.teaser | relative_url }}" alt="{{ project.title }}">
      {% endif %}
      <h3><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h3>
      <p>{{ project.excerpt | markdownify | strip_html | truncatewords: 25 }}</p>

      {% if project.tech_stack %}
        <div class="tech-stack">
          {% for tech in project.tech_stack limit:4 %}
            <span class="tag">{{ tech }}</span>
          {% endfor %}
        </div>
      {% endif %}

      <div class="project-links">
        <a href="{{ project.url | relative_url }}" class="btn btn--info btn--small">Learn More</a>
        {% if project.github_url %}
          <a href="{{ project.github_url }}" class="btn btn--inverse btn--small"><i class="fab fa-github"></i> GitHub</a>
        {% endif %}
        {% if project.demo_url %}
          <a href="{{ project.demo_url }}" class="btn btn--primary btn--small"><i class="fas fa-external-link-alt"></i> Demo</a>
        {% endif %}
      </div>
    </article>
  {% endfor %}
</section>

<div class="text-center">
  <a href="/portfolio/" class="btn btn--primary">View All Projects</a>
</div>

---

## 📝 Latest Blog Posts

{% for post in site.posts limit:5 %}
  <div class="list__item">
    <article class="archive__item">
      <h2 class="archive__item-title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <p class="archive__item-excerpt">{{ post.excerpt | markdownify | strip_html | truncatewords: 30 }}</p>
      <p class="page__meta">
        <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
        {% if post.read_time %} • {% include read-time.html %}{% endif %}
      </p>
    </article>
  </div>
{% endfor %}

---

<style>
.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin: 2rem 0;
}

.card {
  border: 1px solid #e1e5e9;
  border-radius: 8px;
  padding: 1.5rem;
  background: #fff;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.card:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 10px rgba(0,0,0,0.1);
}

.card img {
  width: 100%;
  height: 180px;
  object-fit: cover;
  margin-bottom: 1rem;
  border-radius: 4px;
}

.card h3 {
  margin-top: 0.5rem;
}

.card-meta {
  font-size: 0.875rem;
  color: #666;
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

.project-links {
  margin-top: 1rem;
}

.project-links .btn {
  margin: 0.25rem 0.5rem 0.25rem 0;
}

@media (max-width: 768px) {
  .card-grid {
    grid-template-columns: 1fr;
  }
}
</style>
