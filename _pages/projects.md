---
layout: page
title: Projects
permalink: /projects/
description: A growing collection of research, academic, and creative projects.
nav: false
nav_order: 3
display_categories: [work, fun]
horizontal: false
---

<style>
  .projects-page {
    position: relative;
  }

  .projects-hero {
    position: relative;
    overflow: hidden;
    padding: 2.6rem 2rem;
    border-radius: 24px;
    margin-bottom: 2rem;
    color: white;
    background: linear-gradient(-45deg, #0f172a, #1d4ed8, #7c3aed, #14b8a6);
    background-size: 400% 400%;
    animation: projGradientFlow 13s ease infinite;
    box-shadow: 0 18px 40px rgba(15, 23, 42, 0.18);
  }

  .projects-hero::before,
  .projects-hero::after {
    content: "";
    position: absolute;
    border-radius: 50%;
    filter: blur(42px);
    opacity: 0.26;
    pointer-events: none;
  }

  .projects-hero::before {
    width: 240px;
    height: 240px;
    background: rgba(255,255,255,0.18);
    top: -70px;
    right: -40px;
    animation: projFloat 9s ease-in-out infinite;
  }

  .projects-hero::after {
    width: 180px;
    height: 180px;
    background: rgba(255,255,255,0.12);
    bottom: -45px;
    left: -30px;
    animation: projFloat 11s ease-in-out infinite reverse;
  }

  .projects-hero h1 {
    margin: 0 0 0.8rem 0;
    font-size: 2.35rem;
    color: white;
  }

  .projects-hero p {
    margin: 0;
    max-width: 860px;
    font-size: 1.05rem;
    line-height: 1.8;
    color: rgba(255,255,255,0.95);
  }

  .projects-shell {
    position: relative;
    padding: 1.2rem;
    border-radius: 24px;
    background: linear-gradient(180deg, rgba(248,250,252,0.92), rgba(241,245,249,0.82));
    border: 1px solid rgba(226,232,240,0.8);
    box-shadow: 0 14px 36px rgba(15, 23, 42, 0.06);
    backdrop-filter: blur(8px);
  }

  .projects-shell::before {
    content: "";
    position: absolute;
    inset: 0;
    border-radius: 24px;
    pointer-events: none;
    background: linear-gradient(135deg, rgba(255,255,255,0.18), rgba(255,255,255,0.02));
  }

  .projects > a {
    text-decoration: none !important;
  }

  .projects h2.category {
    position: relative;
    display: inline-flex;
    align-items: center;
    gap: 0.6rem;
    margin-top: 0.8rem;
    margin-bottom: 1.1rem;
    padding: 0.7rem 1rem;
    border-radius: 999px;
    font-size: 1.1rem;
    font-weight: 800;
    text-transform: capitalize;
    letter-spacing: 0.25px;
    color: #0f172a;
    background: linear-gradient(90deg, rgba(37,99,235,0.12), rgba(124,58,237,0.12));
    border: 1px solid rgba(37,99,235,0.12);
    box-shadow: 0 8px 18px rgba(15, 23, 42, 0.05);
    transition: transform 0.25s ease, box-shadow 0.25s ease;
    animation: projFadeUp 0.7s ease both;
  }

  .projects h2.category::before {
    content: "✨";
    font-size: 0.95rem;
  }

  .projects h2.category:hover {
    transform: translateY(-2px);
    box-shadow: 0 12px 24px rgba(15, 23, 42, 0.09);
  }

  .projects .row {
    margin-bottom: 1.6rem;
    animation: projFadeUp 0.85s ease both;
  }

  .projects .container {
    padding-left: 0;
    padding-right: 0;
  }

  .projects .row > * {
    margin-bottom: 1.25rem;
  }

  .projects .card {
    position: relative;
    overflow: hidden;
    border: none !important;
    border-radius: 22px !important;
    background: rgba(255,255,255,0.9) !important;
    box-shadow: 0 12px 28px rgba(15, 23, 42, 0.08) !important;
    transition: transform 0.35s ease, box-shadow 0.35s ease !important;
    backdrop-filter: blur(8px);
  }

  .projects .card:hover {
    transform: translateY(-8px);
    box-shadow: 0 20px 40px rgba(15, 23, 42, 0.14) !important;
  }

  .projects .card::before {
    content: "";
    position: absolute;
    inset: 0;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.35s ease;
    background: linear-gradient(135deg, rgba(37,99,235,0.08), rgba(124,58,237,0.08), rgba(20,184,166,0.06));
  }

  .projects .card:hover::before {
    opacity: 1;
  }

  .projects .card img,
  .projects .card .card-img-top {
    border-top-left-radius: 22px !important;
    border-top-right-radius: 22px !important;
  }

  .projects .card-body {
    padding: 1.15rem 1.15rem 1.05rem 1.15rem !important;
  }

  .projects .card-title {
    font-size: 1.02rem !important;
    font-weight: 750 !important;
    line-height: 1.45 !important;
    color: #0f172a !important;
    margin-bottom: 0.55rem !important;
  }

  .projects .card-text {
    color: #475569 !important;
    font-size: 0.95rem !important;
    line-height: 1.7 !important;
  }

  .projects .card a {
    transition: color 0.25s ease, opacity 0.25s ease;
  }

  .projects .card a:hover {
    opacity: 0.92;
  }

  .projects .badge,
  .projects .btn,
  .projects .github-icon,
  .projects .repo,
  .projects .card-footer {
    position: relative;
    z-index: 2;
  }

  .projects .btn,
  .projects a.btn,
  .projects .card a.btn {
    border-radius: 999px !important;
    padding: 0.55rem 0.95rem !important;
    font-weight: 700 !important;
    border: none !important;
    background: linear-gradient(90deg, #2563eb, #7c3aed) !important;
    color: white !important;
    box-shadow: 0 8px 18px rgba(37, 99, 235, 0.18);
    transition: transform 0.25s ease, box-shadow 0.25s ease !important;
  }

  .projects .btn:hover,
  .projects a.btn:hover,
  .projects .card a.btn:hover {
    transform: translateY(-2px);
    box-shadow: 0 12px 24px rgba(37, 99, 235, 0.24);
  }

  .projects .badge {
    border-radius: 999px !important;
    padding: 0.45rem 0.8rem !important;
    font-weight: 700 !important;
    background: rgba(37,99,235,0.10) !important;
    color: #1d4ed8 !important;
    border: 1px solid rgba(37,99,235,0.10);
  }

  .projects .card-footer {
    background: transparent !important;
    border-top: 1px solid rgba(148,163,184,0.12) !important;
  }

  .projects-divider {
    height: 1px;
    border: none;
    margin: 1.4rem 0 1.2rem 0;
    background: linear-gradient(to right, transparent, rgba(148,163,184,0.45), transparent);
  }

  .projects-empty-note {
    padding: 1rem 1.1rem;
    border-radius: 16px;
    background: linear-gradient(90deg, rgba(37,99,235,0.08), rgba(124,58,237,0.08));
    border: 1px solid rgba(37,99,235,0.10);
    color: #334155;
    font-weight: 600;
    animation: projFadeUp 0.8s ease both;
  }

  @keyframes projGradientFlow {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
  }

  @keyframes projFloat {
    0% { transform: translateY(0px) translateX(0px); }
    50% { transform: translateY(18px) translateX(8px); }
    100% { transform: translateY(0px) translateX(0px); }
  }

  @keyframes projFadeUp {
    from {
      opacity: 0;
      transform: translateY(18px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  @media (prefers-reduced-motion: reduce) {
    .projects-hero,
    .projects-hero::before,
    .projects-hero::after,
    .projects .row,
    .projects h2.category {
      animation: none !important;
    }

    .projects .card,
    .projects .btn,
    .projects h2.category {
      transition: none !important;
    }
  }
</style>

<div class="projects-page">
  <div class="projects-hero">
    <h1>Projects</h1>
    <p>
      A curated collection of research, academic, and creative projects spanning intelligent systems, machine learning, multimodal AI, and other exploratory work. Browse by category to discover featured efforts, ongoing ideas, and selected implementations.
    </p>
  </div>

  <div class="projects-shell">
    <div class="projects">
    {% if site.enable_project_categories and page.display_categories %}

      {% for category in page.display_categories %}
      <a id="{{ category }}" href=".#{{ category }}">
        <h2 class="category">{{ category }}</h2>
      </a>

      {% assign categorized_projects = site.projects | where: "category", category %}
      {% assign sorted_projects = categorized_projects | sort: "importance" %}

      {% if page.horizontal %}
      <div class="container">
        <div class="row row-cols-1 row-cols-md-2">
        {% for project in sorted_projects %}
          {% include projects_horizontal.liquid %}
        {% endfor %}
        </div>
      </div>
      {% else %}
      <div class="row row-cols-1 row-cols-md-3">
        {% for project in sorted_projects %}
          {% include projects.liquid %}
        {% endfor %}
      </div>
      {% endif %}

      {% unless forloop.last %}
      <hr class="projects-divider">
      {% endunless %}
      {% endfor %}

    {% else %}

      {% assign sorted_projects = site.projects | sort: "importance" %}

      {% if page.horizontal %}
      <div class="container">
        <div class="row row-cols-1 row-cols-md-2">
        {% for project in sorted_projects %}
          {% include projects_horizontal.liquid %}
        {% endfor %}
        </div>
      </div>
      {% else %}
      <div class="row row-cols-1 row-cols-md-3">
        {% for project in sorted_projects %}
          {% include projects.liquid %}
        {% endfor %}
      </div>
      {% endif %}

    {% endif %}
    </div>
  </div>
</div>
