---
layout: page
title: Research Highlights
permalink: /research-highlights/
description: Selected research highlights and publications
nav: false
nav_order: 3
---

<div class="research-highlights">
  <div class="container">
    <div class="row">
      <div class="col-lg-12">
        <h1 class="research-title">Research Highlights</h1>
        <p class="research-subtitle">Discover our innovative approaches to building robust and secure AI systems</p>
      </div>
    </div>

    {% assign sorted_projects = site.data.research_highlights | sort: "importance" %}
    {% for project in sorted_projects %}
    <div class="research-project">
      <div class="project-header">
        <h2 class="project-title">{{ project.title }}</h2>
        <div class="project-authors">
          {% for author in project.authors %}
            <span class="author">{{ author.name }}</span>{% unless forloop.last %}, {% endunless %}
          {% endfor %}
        </div>
        <div class="project-meta">
          <span class="venue">{{ project.venue }}</span>
          {% if project.status %}
            <span class="status status-{{ project.status | downcase | replace: ' ', '-' | replace: '(', '' | replace: ')', '' }}">
              {{ project.status }}
            </span>
          {% endif %}
        </div>
        <div class="project-links">
          {% for link in project.links %}
            <a href="{{ link.url }}" class="btn btn-outline-primary btn-sm" target="_blank">
              <i class="fas {{ link.icon }}"></i> {{ link.name }}
            </a>
          {% endfor %}
        </div>
      </div>

      <div class="architecture-container-large">
        <div class="architecture-image-large">
          <img src="assets/img/{{ project.image }}" alt="{{ project.image_alt }}" class="img-fluid architecture-img">
        </div>
        <div class="architecture-caption-large">
          <strong>{{ project.image_alt }}:</strong> {{ project.description }}
        </div>
      </div>
    </div>
    {% endfor %}

  </div>
</div>

<style>
.research-highlights {
  padding: 2rem 0;
}

.research-title {
  font-size: 3rem;
  font-weight: bold;
  color: #333;
  margin-bottom: 0.5rem;
  text-align: center;
}

.research-subtitle {
  font-size: 1.2rem;
  color: #666;
  text-align: center;
  margin-bottom: 3rem;
}

.research-project {
  margin-bottom: 4rem;
  padding: 2rem;
  border-radius: 10px;
  background-color: #f8f9fa;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.research-project:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 25px rgba(0,0,0,0.15);
}

.project-header {
  margin-bottom: 2rem;
}

.project-title {
  font-size: 1.8rem;
  font-weight: bold;
  color: #333;
  margin-bottom: 1rem;
  line-height: 1.3;
}

.project-authors {
  font-size: 1.1rem;
  color: #555;
  margin-bottom: 0.75rem;
}

.author {
  font-weight: 500;
}

.project-meta {
  margin-bottom: 1rem;
  display: flex;
  gap: 1rem;
  align-items: center;
  flex-wrap: wrap;
}

.venue {
  font-size: 0.95rem;
  color: #666;
  font-style: italic;
}

.status {
  padding: 0.25rem 0.75rem;
  border-radius: 20px;
  font-size: 0.85rem;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.status-accepted {
  background-color: #d4edda;
  color: #155724;
  border: 1px solid #c3e6cb;
}

.status-published {
  background-color: #d1ecf1;
  color: #0c5460;
  border: 1px solid #bee5eb;
}

.status-under-review-in-ieee-transactions-on-big-data {
  background-color: #fff3cd;
  color: #856404;
  border: 1px solid #ffeaa7;
}

.status-published-q1-journal {
  background-color: #d4edda;
  color: #155724;
  border: 1px solid #c3e6cb;
}

.project-links {
  display: flex;
  gap: 0.5rem;
  flex-wrap: wrap;
}

.btn-outline-primary {
  border-color: #007bff;
  color: #007bff;
  background-color: transparent;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.btn-outline-primary:hover {
  background-color: #007bff;
  color: white;
  border-color: #007bff;
  transform: translateY(-2px);
}

.btn-outline-primary i {
  font-size: 0.9rem;
}

/* Large Architecture Container with Prominent Border */
.architecture-container-large {
  border: 4px solid #000;
  border-radius: 12px;
  padding: 2rem;
  background-color: white;
  box-shadow: 0 6px 20px rgba(0,0,0,0.15);
  transition: all 0.3s ease;
  margin: 2rem 0;
}

.architecture-container-large:hover {
  border-color: #007bff;
  box-shadow: 0 8px 25px rgba(0,0,0,0.2);
}

.architecture-image-large {
  text-align: center;
  margin-bottom: 1.5rem;
}

.architecture-img {
  max-width: 95%;
  /* height: auto; */
  border-radius: 8px;
  transition: transform 0.3s ease;
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

.architecture-img:hover {
  transform: scale(1.02);
}

.architecture-caption-large {
  font-size: 1.1rem;
  color: #555;
  text-align: center;
  font-style: italic;
  line-height: 1.5;
  padding: 1rem;
  background-color: #f8f9fa;
  border-radius: 8px;
  border: 1px solid #e9ecef;
}

/* Responsive design */
@media (max-width: 768px) {
  .research-title {
    font-size: 2.5rem;
  }
  
  .project-title {
    font-size: 1.5rem;
  }
  
  .project-links {
    justify-content: center;
  }
  
  .architecture-container-large {
    padding: 1.5rem;
    margin: 1.5rem 0;
  }
  
  .project-meta {
    flex-direction: column;
    align-items: flex-start;
    gap: 0.5rem;
  }
  
  .architecture-caption-large {
    font-size: 1rem;
    padding: 0.75rem;
  }
}
</style>
