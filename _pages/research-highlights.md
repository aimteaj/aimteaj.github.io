---
layout: page
title: Research Projects
permalink: /research-highlights/
description: ""
nav: true
nav_order: 3
---

<div class="research-highlights-page">

  <div class="rh-hero">
    <p>
      Selected research highlights spanning robust artificial intelligence, vision-language models, federated learning, multimodal systems, and trustworthy machine intelligence.
    </p>

    <div class="rh-hero-badges">
      <span class="rh-hero-badge">Vision-Language Models</span>
      <span class="rh-hero-badge">Federated Learning</span>
      <span class="rh-hero-badge">Robust, Efficient and Secure AI</span>
      <span class="rh-hero-badge">Trustworthy AI, Agentic AI and Cybersecurity</span>
      <span class="rh-hero-badge">Real-World Applications</span>
    </div>
  </div>

  {% assign lab = site.data.lab_projects %}

  <!-- ===== Selected Research: Our latest work, in motion (mirrored from speedlab.network) ===== -->
  <section class="lab-section">
    <div class="lab-eyebrow">Selected Research</div>
    <h2 class="lab-title">Our latest work, <em>in motion</em></h2>

    <div class="teaser-grid">
      {% for t in lab.latest %}
      <article class="teaser-card">
        <div class="teaser-media">
          <video class="teaser-video" muted loop playsinline controls preload="none"
                 poster="{{ site.baseurl }}/assets/img/lab-projects/{{ t.poster }}">
            <source src="{{ site.baseurl }}/assets/video/{{ t.video }}" type="video/mp4">
          </video>
        </div>
        <div class="teaser-body">
          <div class="teaser-meta">
            <span class="teaser-short">{{ t.short }}</span>
            <span class="teaser-venue">{{ t.venue }}</span>
          </div>
          <h3 class="teaser-title">{{ t.title }}</h3>
          <p class="teaser-subtitle">{{ t.subtitle }}</p>
          <p class="teaser-desc">{{ t.description }}</p>
          <div class="teaser-tags">
            {% for tag in t.tags %}<span class="teaser-tag">{{ tag }}</span>{% endfor %}
          </div>
          {% if t.link != "" %}
          <a href="{{ t.link }}" class="rh-btn teaser-link" target="_blank" rel="noopener noreferrer">
            <i class="fas fa-globe"></i><span>Project Page</span>
          </a>
          {% endif %}
        </div>
      </article>
      {% endfor %}
    </div>
  </section>

  <!-- ===== Ongoing Research: Projects in progress (mirrored from speedlab.network) ===== -->
  <section class="lab-section">
    <div class="lab-eyebrow">Ongoing Research</div>
    <h2 class="lab-title">Projects in progress</h2>
    <p class="lab-lead">Active projects across vision-language models, generative AI and safety-critical applications.</p>

    <div class="ongoing-list">
      {% for p in lab.ongoing %}
      <article class="ongoing-row{% cycle '', ' is-flipped' %}">
        <div class="ongoing-media">
          <img src="{{ site.baseurl }}/assets/img/lab-projects/{{ p.image }}" alt="{{ p.title }}" loading="lazy">
        </div>
        <div class="ongoing-body">
          <span class="status-pill"><span class="pulse-dot"></span> Ongoing</span>
          <h3>{{ p.title }}</h3>
          <p>{{ p.description }}</p>
        </div>
      </article>
      {% endfor %}
    </div>

    <h3 class="lab-subhead">More projects</h3>
    <div class="mini-grid">
      {% for p in lab.more %}
      <article class="mini-card">
        <div class="mini-media">
          <img src="{{ site.baseurl }}/assets/img/lab-projects/{{ p.image }}" alt="" loading="lazy">
        </div>
        <div class="mini-body">
          <h4>{{ p.title }}</h4>
          <p>{{ p.description }}</p>
        </div>
      </article>
      {% endfor %}
    </div>
  </section>

  <section class="lab-section lab-section--tight">
    <div class="lab-eyebrow">Publications</div>
    <h2 class="lab-title">Research highlights</h2>
  </section>

  <div class="research-highlights">
    <div class="container">

      {% assign sorted_projects = site.data.research_highlights | sort: "importance" %}
      {% for project in sorted_projects %}
      {% if project.teaser %}{% continue %}{% endif %}
      <div class="research-project">

        <div class="project-header">
          <div class="project-title-wrap">
            <h2 class="project-title">{{ project.title }}</h2>
          </div>

          <div class="project-authors">
            {% for author in project.authors %}
              <span class="author">{{ author.name }}</span>{% unless forloop.last %}<span class="author-sep">•</span>{% endunless %}
            {% endfor %}
          </div>

          <div class="project-meta">
            <span class="venue">{{ project.venue }}</span>
            {% if project.status %}
              <span class="status status-{{ project.status | downcase | replace: ' ', '-' | replace: '(', '' | replace: ')', '' | replace: '.', '' | replace: ',', '' | replace: '|', '' }}">
                {{ project.status }}
              </span>
            {% endif %}
          </div>

          <div class="project-links">
            {% for link in project.links %}
              <a href="{{ link.url }}" class="rh-btn" target="_blank" rel="noopener noreferrer">
                <i class="fas {{ link.icon }}"></i>
                <span>{{ link.name }}</span>
              </a>
            {% endfor %}
          </div>
        </div>

        <div class="architecture-container-large">
          <div class="architecture-image-large">
            {% if project.video %}
            <video class="teaser-video architecture-img" muted loop playsinline controls preload="none"
                   {% if project.image %}poster="{{ site.baseurl }}/assets/img/{{ project.image }}"{% endif %}>
              <source src="{{ site.baseurl }}/assets/video/{{ project.video }}" type="video/mp4">
            </video>
            {% else %}
            <img src="{{ site.baseurl }}/assets/img/{{ project.image }}" alt="{{ project.image_alt }}" class="img-fluid architecture-img">
            {% endif %}
          </div>

          <div class="architecture-caption-large">
            <div class="caption-label">{{ project.image_alt }}</div>
            <div class="caption-text">{{ project.description }}</div>
          </div>
        </div>

      </div>
      {% endfor %}

    </div>
  </div>
</div>

<style>
.research-highlights-page {
  position: relative;
}

/* Hero */
.rh-hero {
  position: relative;
  overflow: hidden;
  padding: 2.9rem 2rem;
  border-radius: 28px;
  margin-bottom: 2rem;
  color: white;
  background: linear-gradient(-45deg, #0f172a, #1d4ed8, #7c3aed, #14b8a6, #0ea5e9);
  background-size: 500% 500%;
  animation: rhGradient 16s ease infinite;
  box-shadow: 0 22px 46px rgba(15, 23, 42, 0.18);
}

.rh-hero::before,
.rh-hero::after {
  content: "";
  position: absolute;
  border-radius: 50%;
  filter: blur(48px);
  pointer-events: none;
  opacity: 0.24;
}

.rh-hero::before {
  width: 250px;
  height: 250px;
  background: rgba(255,255,255,0.18);
  top: -80px;
  right: -40px;
  animation: rhFloat 10s ease-in-out infinite;
}

.rh-hero::after {
  width: 180px;
  height: 180px;
  background: rgba(255,255,255,0.12);
  bottom: -50px;
  left: -20px;
  animation: rhFloat 12s ease-in-out infinite reverse;
}

.rh-hero h1 {
  margin: 0 0 0.75rem 0;
  font-size: 2.6rem;
  color: white;
  letter-spacing: 0.2px;
}

.rh-hero p {
  margin: 0;
  max-width: 900px;
  font-size: 1.05rem;
  line-height: 1.9;
  color: rgba(255,255,255,0.96);
}

.rh-hero-badges {
  display: flex;
  flex-wrap: wrap;
  gap: 0.7rem;
  margin-top: 1.2rem;
}

.rh-hero-badge {
  display: inline-flex;
  align-items: center;
  padding: 0.55rem 0.95rem;
  border-radius: 999px;
  background: rgba(255,255,255,0.16);
  border: 1px solid rgba(255,255,255,0.18);
  backdrop-filter: blur(10px);
  color: white;
  font-size: 0.92rem;
  font-weight: 700;
  box-shadow: 0 8px 18px rgba(15, 23, 42, 0.10);
  animation: rhPop 0.7s ease both;
}

/* Section */
.research-highlights {
  padding: 0.25rem 0 2rem 0;
}

/* Project card */
.research-project {
  position: relative;
  overflow: hidden;
  margin-bottom: 2rem;
  padding: 1.6rem;
  border-radius: 24px;
  background: linear-gradient(180deg, rgba(248,250,252,0.96), rgba(241,245,249,0.90));
  border: 1px solid rgba(226,232,240,0.85);
  box-shadow: 0 16px 34px rgba(15, 23, 42, 0.07);
  backdrop-filter: blur(8px);
  transition: transform 0.35s ease, box-shadow 0.35s ease;
  animation: rhFadeUp 0.85s ease both;
}

.research-project:hover {
  transform: translateY(-8px);
  box-shadow: 0 22px 42px rgba(15, 23, 42, 0.12);
}

.research-project::before {
  content: "";
  position: absolute;
  inset: 0;
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.35s ease;
  background: linear-gradient(135deg, rgba(37,99,235,0.06), rgba(124,58,237,0.06), rgba(20,184,166,0.05));
}

.research-project:hover::before {
  opacity: 1;
}

.project-header {
  margin-bottom: 1.35rem;
}

.project-title-wrap {
  margin-bottom: 0.9rem;
}

.project-title {
  display: inline-block;
  margin: 0;
  font-size: 1.7rem;
  font-weight: 800;
  line-height: 1.35;
  color: #0f172a;
}

.project-authors {
  display: flex;
  flex-wrap: wrap;
  gap: 0.35rem;
  align-items: center;
  margin-bottom: 0.85rem;
  font-size: 1rem;
  color: #475569;
}

.author {
  font-weight: 650;
  color: #334155;
}

.author-sep {
  margin: 0 0.15rem;
  color: #94a3b8;
}

.project-meta {
  margin-bottom: 1rem;
  display: flex;
  gap: 0.7rem;
  align-items: center;
  flex-wrap: wrap;
}

.venue {
  display: inline-flex;
  align-items: center;
  padding: 0.45rem 0.8rem;
  border-radius: 999px;
  background: rgba(37,99,235,0.08);
  border: 1px solid rgba(37,99,235,0.10);
  color: #1d4ed8;
  font-size: 0.92rem;
  font-weight: 700;
}

.status {
  display: inline-flex;
  align-items: center;
  padding: 0.45rem 0.85rem;
  border-radius: 999px;
  font-size: 0.86rem;
  font-weight: 800;
  letter-spacing: 0.2px;
  box-shadow: 0 6px 14px rgba(15, 23, 42, 0.04);
}

/* Default status style */
.status {
  background: linear-gradient(90deg, #eef2ff, #f5f3ff);
  color: #4338ca;
  border: 1px solid rgba(99,102,241,0.16);
}

.status-accepted {
  background: linear-gradient(90deg, #ecfdf5, #f0fdf4);
  color: #047857;
  border: 1px solid rgba(16,185,129,0.18);
}

.status-published {
  background: linear-gradient(90deg, #eff6ff, #ecfeff);
  color: #0c4a6e;
  border: 1px solid rgba(14,165,233,0.18);
}

.status-under-review-in-ieee-transactions-on-big-data {
  background: linear-gradient(90deg, #fff7ed, #fefce8);
  color: #9a3412;
  border: 1px solid rgba(245,158,11,0.18);
}

.status-published-q1-journal {
  background: linear-gradient(90deg, #ecfdf5, #f0fdf4);
  color: #065f46;
  border: 1px solid rgba(34,197,94,0.18);
}

/* Buttons */
.project-links {
  display: flex;
  gap: 0.65rem;
  flex-wrap: wrap;
}

.rh-btn {
  display: inline-flex;
  align-items: center;
  gap: 0.55rem;
  padding: 0.62rem 1rem;
  border-radius: 999px;
  text-decoration: none !important;
  font-size: 0.92rem;
  font-weight: 700;
  color: white !important;
  background: linear-gradient(90deg, #2563eb, #7c3aed);
  box-shadow: 0 10px 20px rgba(37,99,235,0.18);
  transition: transform 0.25s ease, box-shadow 0.25s ease, filter 0.25s ease;
}

.rh-btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 14px 24px rgba(37,99,235,0.24);
  filter: brightness(1.03);
}

.rh-btn i {
  font-size: 0.9rem;
}

/* Image showcase */
.architecture-container-large {
  position: relative;
  overflow: hidden;
  border-radius: 22px;
  padding: 1.5rem;
  background: linear-gradient(180deg, #ffffff, #f8fafc);
  border: 1px solid rgba(226,232,240,0.8);
  box-shadow: 0 12px 28px rgba(15, 23, 42, 0.08);
  transition: transform 0.35s ease, box-shadow 0.35s ease;
}

.architecture-container-large:hover {
  transform: translateY(-4px);
  box-shadow: 0 18px 34px rgba(15, 23, 42, 0.12);
}

.architecture-container-large::before {
  content: "";
  position: absolute;
  inset: 0;
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.35s ease;
  background: linear-gradient(135deg, rgba(37,99,235,0.05), rgba(124,58,237,0.05), rgba(20,184,166,0.05));
}

.architecture-container-large:hover::before {
  opacity: 1;
}

.architecture-image-large {
  text-align: center;
  margin-bottom: 1.2rem;
}

.architecture-img {
  max-width: 100%;
  border-radius: 18px;
  box-shadow: 0 12px 24px rgba(15, 23, 42, 0.10);
  transition: transform 0.35s ease, box-shadow 0.35s ease, filter 0.35s ease;
}

.architecture-img:hover {
  transform: scale(1.02);
  box-shadow: 0 18px 34px rgba(15, 23, 42, 0.16);
  filter: brightness(1.02);
}

.architecture-caption-large {
  padding: 1rem 1rem;
  border-radius: 18px;
  background: linear-gradient(90deg, rgba(248,250,252,0.95), rgba(255,255,255,0.92));
  border: 1px solid rgba(226,232,240,0.8);
  box-shadow: 0 8px 18px rgba(15, 23, 42, 0.04);
  text-align: center;
}

.caption-label {
  display: inline-block;
  margin-bottom: 0.45rem;
  padding: 0.45rem 0.8rem;
  border-radius: 999px;
  background: rgba(124,58,237,0.08);
  border: 1px solid rgba(124,58,237,0.10);
  color: #6d28d9;
  font-size: 0.88rem;
  font-weight: 800;
}

.caption-text {
  font-size: 1rem;
  color: #475569;
  line-height: 1.75;
}

/* Animations */
@keyframes rhGradient {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}

@keyframes rhFloat {
  0% { transform: translateY(0px) translateX(0px); }
  50% { transform: translateY(18px) translateX(8px); }
  100% { transform: translateY(0px) translateX(0px); }
}

@keyframes rhFadeUp {
  from {
    opacity: 0;
    transform: translateY(18px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes rhPop {
  from {
    opacity: 0;
    transform: scale(0.92);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}

/* Responsive */
@media (max-width: 768px) {
  .rh-hero {
    padding: 2.3rem 1.35rem;
  }

  .rh-hero h1 {
    font-size: 2.15rem;
  }

  .project-title {
    font-size: 1.35rem;
  }

  .research-project {
    padding: 1.2rem;
  }

  .project-links {
    justify-content: flex-start;
  }

  .project-meta {
    flex-direction: column;
    align-items: flex-start;
    gap: 0.55rem;
  }

  .architecture-container-large {
    padding: 1rem;
  }

  .caption-text {
    font-size: 0.95rem;
  }
}

@media (prefers-reduced-motion: reduce) {
  .rh-hero,
  .rh-hero::before,
  .rh-hero::after,
  .rh-hero-badge,
  .research-project {
    animation: none !important;
  }

  .research-project,
  .rh-btn,
  .architecture-container-large,
  .architecture-img {
    transition: none !important;
  }
}

/* ===== Lab sections: latest work (videos), ongoing projects, more projects ===== */
.lab-section { margin: 2.6rem 0 1rem; }
.lab-section--tight { margin: 2.8rem 0 0.6rem; }
.lab-eyebrow {
  font-size: 0.78rem; font-weight: 800; letter-spacing: 0.14em; text-transform: uppercase;
  color: #7c3aed; margin-bottom: 0.35rem;
}
.lab-title { font-size: 2rem; font-weight: 800; color: #0f172a; margin: 0 0 0.5rem; line-height: 1.2; }
.lab-title em { font-style: italic; background: linear-gradient(90deg, #2563eb, #7c3aed); -webkit-background-clip: text; background-clip: text; color: transparent; }
.lab-lead { color: #475569; font-size: 1.05rem; margin: 0 0 1.4rem; max-width: 46rem; }
.lab-subhead { font-size: 1.35rem; font-weight: 800; color: #0f172a; margin: 2.4rem 0 1rem; }

.teaser-grid { display: grid; grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 1.4rem; margin-top: 1.2rem; }
.teaser-card {
  display: flex; flex-direction: column; border-radius: 22px; overflow: hidden; background: #fff;
  border: 1px solid rgba(15,23,42,0.08); box-shadow: 0 16px 36px rgba(15,23,42,0.08);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}
.teaser-card:hover { transform: translateY(-4px); box-shadow: 0 22px 44px rgba(37,99,235,0.14); }
.teaser-media { background: #0b1020; aspect-ratio: 16 / 9; }
.teaser-video { display: block; width: 100%; height: 100%; object-fit: cover; background: #0b1020; }
.architecture-image-large .teaser-video { height: auto; border-radius: 16px; }
.teaser-body { padding: 1.2rem 1.35rem 1.4rem; display: flex; flex-direction: column; gap: 0.55rem; flex: 1; }
.teaser-meta { display: flex; gap: 0.5rem; flex-wrap: wrap; align-items: center; }
.teaser-short { font-weight: 800; font-size: 0.85rem; color: #fff; background: linear-gradient(90deg, #2563eb, #7c3aed); padding: 0.25rem 0.7rem; border-radius: 999px; }
.teaser-venue { font-weight: 700; font-size: 0.85rem; color: #1d4ed8; background: rgba(37,99,235,0.08); padding: 0.25rem 0.7rem; border-radius: 999px; }
.teaser-title { font-size: 1.3rem; font-weight: 800; color: #0f172a; margin: 0.2rem 0 0; line-height: 1.3; }
.teaser-subtitle { font-weight: 650; color: #334155; margin: 0; }
.teaser-desc { color: #475569; margin: 0; line-height: 1.6; }
.teaser-tags { display: flex; flex-wrap: wrap; gap: 0.4rem; margin-top: auto; padding-top: 0.3rem; }
.teaser-tag { font-size: 0.8rem; font-weight: 650; color: #0f766e; background: rgba(20,184,166,0.10); border: 1px solid rgba(20,184,166,0.18); padding: 0.2rem 0.6rem; border-radius: 999px; }
.teaser-link { align-self: flex-start; margin-top: 0.4rem; }

.ongoing-list { display: flex; flex-direction: column; gap: 1.6rem; }
.ongoing-row {
  display: grid; grid-template-columns: minmax(0, 1fr) minmax(0, 1.15fr); gap: 1.6rem; align-items: center;
  background: #fff; border: 1px solid rgba(15,23,42,0.08); border-radius: 22px; padding: 1.2rem;
  box-shadow: 0 12px 30px rgba(15,23,42,0.06);
}
.ongoing-row.is-flipped .ongoing-media { order: 2; }
.ongoing-media img { width: 100%; border-radius: 16px; display: block; background: #f8fafc; }
.ongoing-body h3 { font-size: 1.3rem; font-weight: 800; color: #0f172a; margin: 0.6rem 0 0.5rem; line-height: 1.3; }
.ongoing-body p { color: #475569; line-height: 1.65; margin: 0; }
.status-pill { display: inline-flex; align-items: center; gap: 0.45rem; font-size: 0.8rem; font-weight: 800; color: #15803d; background: rgba(34,197,94,0.10); border: 1px solid rgba(34,197,94,0.22); padding: 0.25rem 0.7rem; border-radius: 999px; }
.pulse-dot { width: 8px; height: 8px; border-radius: 50%; background: #22c55e; box-shadow: 0 0 0 0 rgba(34,197,94,0.6); animation: labPulse 1.8s infinite; }
@keyframes labPulse { 0% { box-shadow: 0 0 0 0 rgba(34,197,94,0.55); } 70% { box-shadow: 0 0 0 8px rgba(34,197,94,0); } 100% { box-shadow: 0 0 0 0 rgba(34,197,94,0); } }

.mini-grid { display: grid; grid-template-columns: repeat(3, minmax(0, 1fr)); gap: 1.1rem; }
.mini-card { background: #fff; border: 1px solid rgba(15,23,42,0.08); border-radius: 18px; overflow: hidden; box-shadow: 0 10px 24px rgba(15,23,42,0.06); transition: transform 0.25s ease; }
.mini-card:hover { transform: translateY(-3px); }
.mini-media { aspect-ratio: 16 / 10; background: #f8fafc; overflow: hidden; }
.mini-media img { width: 100%; height: 100%; object-fit: cover; display: block; }
.mini-body { padding: 0.95rem 1.05rem 1.1rem; }
.mini-body h4 { font-size: 1.02rem; font-weight: 800; color: #0f172a; margin: 0 0 0.4rem; line-height: 1.35; }
.mini-body p { font-size: 0.92rem; color: #475569; margin: 0; line-height: 1.55; }

html[data-theme="dark"] .lab-title, html[data-theme="dark"] .lab-subhead,
html[data-theme="dark"] .teaser-title, html[data-theme="dark"] .ongoing-body h3,
html[data-theme="dark"] .mini-body h4 { color: #f1f5f9; }
html[data-theme="dark"] .lab-lead, html[data-theme="dark"] .teaser-desc,
html[data-theme="dark"] .ongoing-body p, html[data-theme="dark"] .mini-body p { color: #cbd5e1; }
html[data-theme="dark"] .teaser-subtitle { color: #e2e8f0; }
html[data-theme="dark"] .teaser-card, html[data-theme="dark"] .ongoing-row,
html[data-theme="dark"] .mini-card { background: #111827; border-color: rgba(148,163,184,0.18); }
html[data-theme="dark"] .teaser-venue { color: #93c5fd; background: rgba(59,130,246,0.15); }
html[data-theme="dark"] .teaser-tag { color: #5eead4; }
html[data-theme="dark"] .status-pill { color: #86efac; }

@media (max-width: 900px) {
  .teaser-grid { grid-template-columns: 1fr; }
  .mini-grid { grid-template-columns: repeat(2, minmax(0, 1fr)); }
  .ongoing-row { grid-template-columns: 1fr; }
  .ongoing-row.is-flipped .ongoing-media { order: 0; }
}
@media (max-width: 560px) {
  .mini-grid { grid-template-columns: 1fr; }
  .lab-title { font-size: 1.6rem; }
}
@media (prefers-reduced-motion: reduce) {
  .pulse-dot { animation: none; }
  .teaser-card, .mini-card { transition: none; }
}
</style>

<script>
  // Play teaser videos (muted) only while on screen, so the page stays light.
  (function () {
    var vids = document.querySelectorAll(".teaser-video");
    var reduce = window.matchMedia && window.matchMedia("(prefers-reduced-motion: reduce)").matches;
    if (reduce || !("IntersectionObserver" in window)) return;
    var io = new IntersectionObserver(function (entries) {
      entries.forEach(function (e) {
        var v = e.target;
        if (e.isIntersecting) { v.preload = "auto"; var p = v.play(); if (p && p.catch) p.catch(function () {}); }
        else if (!v.paused) { v.pause(); }
      });
    }, { threshold: 0.35 });
    vids.forEach(function (v) { io.observe(v); });
  })();
</script>
