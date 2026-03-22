---
layout: page
title: Teaching
permalink: /teaching/
nav: true
nav_order: 5
description: Courses taught and curriculum development
---

<style>
  .teach-hero {
    position: relative;
    overflow: hidden;
    padding: 2.4rem 2rem;
    border-radius: 24px;
    margin-bottom: 2rem;
    color: white;
    background: linear-gradient(-45deg, #0f172a, #2563eb, #0ea5e9, #14b8a6);
    background-size: 400% 400%;
    animation: teachGradient 12s ease infinite;
    box-shadow: 0 18px 40px rgba(15, 23, 42, 0.18);
  }

  .teach-hero::before,
  .teach-hero::after {
    content: "";
    position: absolute;
    border-radius: 50%;
    filter: blur(40px);
    opacity: 0.28;
    pointer-events: none;
  }

  .teach-hero::before {
    width: 220px;
    height: 220px;
    background: rgba(255,255,255,0.20);
    top: -70px;
    right: -50px;
    animation: teachFloat 9s ease-in-out infinite;
  }

  .teach-hero::after {
    width: 180px;
    height: 180px;
    background: rgba(255,255,255,0.14);
    bottom: -50px;
    left: -40px;
    animation: teachFloat 11s ease-in-out infinite reverse;
  }

  .teach-hero h1 {
    margin: 0 0 0.75rem 0;
    font-size: 2.3rem;
    color: white;
  }

  .teach-hero p {
    margin: 0;
    max-width: 860px;
    line-height: 1.8;
    font-size: 1.04rem;
    color: rgba(255,255,255,0.95);
  }

  .teach-section-title {
    margin-top: 2rem;
    margin-bottom: 1rem;
    font-size: 1.65rem;
    font-weight: 800;
    letter-spacing: 0.2px;
  }

  .teach-section-title.current { color: #1d4ed8; }
  .teach-section-title.previous { color: #7c3aed; }
  .teach-section-title.developed { color: #059669; }
  .teach-section-title.recognition { color: #ea580c; }

  .teach-grid {
    display: grid;
    gap: 1.2rem;
  }

  .teach-card {
    position: relative;
    overflow: hidden;
    padding: 1.35rem 1.35rem 1.2rem 1.35rem;
    border-radius: 20px;
    background: rgba(255,255,255,0.94);
    border: 1px solid rgba(255,255,255,0.55);
    box-shadow: 0 10px 28px rgba(15, 23, 42, 0.07);
    transition: transform 0.35s ease, box-shadow 0.35s ease;
    animation: teachFadeUp 0.8s ease both;
  }

  .teach-card:hover {
    transform: translateY(-8px);
    box-shadow: 0 18px 36px rgba(15, 23, 42, 0.12);
  }

  .teach-card::before {
    content: "";
    position: absolute;
    inset: 0;
    opacity: 0;
    transition: opacity 0.35s ease;
    background: linear-gradient(135deg, rgba(255,255,255,0.22), rgba(255,255,255,0.04));
    pointer-events: none;
  }

  .teach-card:hover::before {
    opacity: 1;
  }

  .teach-blue { border-left: 6px solid #2563eb; background: linear-gradient(180deg, #f8fbff, #eef6ff); }
  .teach-purple { border-left: 6px solid #7c3aed; background: linear-gradient(180deg, #fcfaff, #f4efff); }
  .teach-green { border-left: 6px solid #059669; background: linear-gradient(180deg, #f6fff9, #ebfff5); }
  .teach-orange { border-left: 6px solid #ea580c; background: linear-gradient(180deg, #fff9f4, #fff1e8); }

  .teach-card h3 {
    margin-top: 0;
    margin-bottom: 0.35rem;
    font-size: 1.05rem;
    font-weight: 750;
    color: #0f172a;
  }

  .teach-subtitle {
    font-size: 0.92rem;
    font-weight: 650;
    color: #475569;
    margin-bottom: 0.8rem;
  }

  .teach-card p {
    margin: 0.45rem 0;
    color: #334155;
    line-height: 1.75;
  }

  .teach-course-list {
    display: grid;
    gap: 0.75rem;
    margin-top: 0.8rem;
  }

  .teach-course-item {
    display: flex;
    align-items: flex-start;
    gap: 0.8rem;
    padding: 0.9rem 1rem;
    border-radius: 14px;
    background: rgba(255,255,255,0.72);
    border: 1px solid rgba(148,163,184,0.16);
    box-shadow: 0 6px 14px rgba(15, 23, 42, 0.04);
    transition: transform 0.25s ease, box-shadow 0.25s ease;
  }

  .teach-course-item:hover {
    transform: translateX(4px);
    box-shadow: 0 10px 18px rgba(15, 23, 42, 0.08);
  }

  .teach-icon {
    font-size: 1.05rem;
    line-height: 1.5;
    margin-top: 0.08rem;
  }

  .teach-course-meta {
    min-width: 135px;
    font-weight: 750;
    color: #1e3a8a;
  }

  .teach-course-text {
    color: #0f172a;
    line-height: 1.65;
  }

  .teach-badges {
    display: flex;
    flex-wrap: wrap;
    gap: 0.65rem;
    margin-top: 1rem;
  }

  .teach-badge {
    display: inline-flex;
    align-items: center;
    padding: 0.55rem 0.95rem;
    border-radius: 999px;
    background: rgba(255,255,255,0.82);
    color: #0f172a;
    font-size: 0.93rem;
    font-weight: 700;
    border: 1px solid rgba(148,163,184,0.18);
    box-shadow: 0 6px 14px rgba(15, 23, 42, 0.05);
    transition: transform 0.25s ease, box-shadow 0.25s ease;
    animation: teachPop 0.6s ease both;
  }

  .teach-badge:hover {
    transform: scale(1.05);
    box-shadow: 0 10px 18px rgba(15, 23, 42, 0.10);
  }

  .teach-highlight {
    display: inline-block;
    margin-top: 0.7rem;
    padding: 0.72rem 1rem;
    border-radius: 16px;
    background: linear-gradient(90deg, rgba(37,99,235,0.10), rgba(14,165,233,0.10));
    border: 1px solid rgba(37,99,235,0.14);
    color: #0f172a;
    font-weight: 650;
  }

  .teach-divider {
    height: 1px;
    border: none;
    margin: 2rem 0 1rem 0;
    background: linear-gradient(to right, transparent, rgba(148,163,184,0.5), transparent);
  }

  @keyframes teachGradient {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
  }

  @keyframes teachFloat {
    0% { transform: translateY(0px) translateX(0px); }
    50% { transform: translateY(18px) translateX(8px); }
    100% { transform: translateY(0px) translateX(0px); }
  }

  @keyframes teachFadeUp {
    from {
      opacity: 0;
      transform: translateY(18px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  @keyframes teachPop {
    from {
      opacity: 0;
      transform: scale(0.92);
    }
    to {
      opacity: 1;
      transform: scale(1);
    }
  }

  @media (max-width: 720px) {
    .teach-course-item {
      flex-direction: column;
      gap: 0.35rem;
    }

    .teach-course-meta {
      min-width: unset;
    }
  }

  @media (prefers-reduced-motion: reduce) {
    .teach-hero,
    .teach-hero::before,
    .teach-hero::after,
    .teach-card,
    .teach-badge {
      animation: none !important;
    }

    .teach-card,
    .teach-course-item,
    .teach-badge {
      transition: none !important;
    }
  }
</style>

<div class="teach-hero">
  <p>
    A snapshot of courses taught, curriculum development efforts, and teaching recognition across undergraduate and graduate education in
    artificial intelligence, machine learning, data structures, and large language models.
  </p>
</div>

## <span class="teach-section-title current">Current and Upcoming Teaching</span>

<div class="teach-grid">
  <div class="teach-card teach-blue">
    <h3>📍 Florida Atlantic University</h3>
    <div class="teach-subtitle">Current instructional portfolio</div>

    <div class="teach-course-list">
      <div class="teach-course-item">
        <div class="teach-icon">🧠</div>
        <div class="teach-course-meta">Fall 2025</div>
        <div class="teach-course-text"><strong>Artificial Intelligence</strong></div>
      </div>

      <div class="teach-course-item">
        <div class="teach-icon">🤖</div>
        <div class="teach-course-meta">Spring 2026</div>
        <div class="teach-course-text"><strong>Artificial Intelligence</strong></div>
      </div>

      <div class="teach-course-item">
        <div class="teach-icon">✨</div>
        <div class="teach-course-meta">Fall 2026</div>
        <div class="teach-course-text"><strong>Large Language Models</strong> <span style="color:#7c3aed; font-weight:700;">| New course</span></div>
      </div>
    </div>

    <div class="teach-highlight">
      Focused on building strong foundations in modern AI while expanding advanced offerings in emerging areas.
    </div>
  </div>
</div>

<hr class="teach-divider">

## <span class="teach-section-title previous">Courses Previously Taught</span>

<div class="teach-grid">
  <div class="teach-card teach-purple">
    <h3>📚 Southern Illinois University Carbondale</h3>
    <div class="teach-subtitle">Previous teaching experience across core and emerging AI areas</div>

    <div class="teach-course-list">
      <div class="teach-course-item">
        <div class="teach-icon">📘</div>
        <div class="teach-course-meta">Fall 2022</div>
        <div class="teach-course-text"><strong>Machine Learning & Soft Computing</strong></div>
      </div>

      <div class="teach-course-item">
        <div class="teach-icon">🧠</div>
        <div class="teach-course-meta">Spring 2023</div>
        <div class="teach-course-text"><strong>Artificial Intelligence</strong></div>
      </div>

      <div class="teach-course-item">
        <div class="teach-icon">📗</div>
        <div class="teach-course-meta">Fall 2023</div>
        <div class="teach-course-text"><strong>Machine Learning & Soft Computing</strong></div>
      </div>

      <div class="teach-course-item">
        <div class="teach-icon">💻</div>
        <div class="teach-course-meta">Spring 2024</div>
        <div class="teach-course-text"><strong>Data Structures and Artificial Intelligence</strong></div>
      </div>

      <div class="teach-course-item">
        <div class="teach-icon">⚡</div>
        <div class="teach-course-meta">Summer 2024</div>
        <div class="teach-course-text"><strong>Generative AI</strong> <span style="color:#475569;">| CS Department</span></div>
      </div>

      <div class="teach-course-item">
        <div class="teach-icon">📘</div>
        <div class="teach-course-meta">Fall 2024</div>
        <div class="teach-course-text"><strong>Machine Learning & Soft Computing</strong></div>
      </div>

      <div class="teach-course-item">
        <div class="teach-icon">🚀</div>
        <div class="teach-course-meta">Spring 2025</div>
        <div class="teach-course-text">
          <strong>Artificial Intelligence, Data Structures, and Generative AI</strong><br>
          <span style="color:#7c3aed; font-weight:650;">Interdisciplinary Undergraduate Course</span>
        </div>
      </div>
    </div>
  </div>
</div>

<hr class="teach-divider">

## <span class="teach-section-title developed">Courses Developed</span>

<div class="teach-grid">
  <div class="teach-card teach-green">
    <h3>🛠️ Curriculum Development</h3>
    <div class="teach-subtitle">Designed new course offerings in rapidly growing AI domains</div>

    <div class="teach-course-list">
      <div class="teach-course-item">
        <div class="teach-icon">🌟</div>
        <div class="teach-course-text">
          <strong>CS491-955: Generative Artificial Intelligence</strong><br>
          <span style="color:#475569;">Offered Summer 2024 | CS Department</span>
        </div>
      </div>

      <div class="teach-course-item">
        <div class="teach-icon">🎓</div>
        <div class="teach-course-text">
          <strong>Generative AI: Computing and Ethical Perspectives</strong><br>
          <span style="color:#475569;">Offered Spring 2025 | University Honors Program</span>
        </div>
      </div>
    </div>

    <div class="teach-badges">
      <span class="teach-badge">Curriculum Innovation</span>
      <span class="teach-badge">Emerging AI Topics</span>
      <span class="teach-badge">Interdisciplinary Teaching</span>
      <span class="teach-badge">New Course Design</span>
    </div>
  </div>
</div>

<hr class="teach-divider">

## <span class="teach-section-title recognition">Teaching Recognition</span>

<div class="teach-grid">
  <div class="teach-card teach-orange">
    <h3>🏆 Outstanding Teacher of the Year Award</h3>
    <div class="teach-subtitle">Southern Illinois University School of Computing | 2024</div>

    <p>
      Honored to receive the <strong>Outstanding Teacher of the Year Award</strong> for dedication to teaching excellence,
      student mentorship, and curriculum innovation.
    </p>

    <div class="teach-highlight">
      Recognized for impactful instruction, student-centered mentoring, and continued development of modern AI-focused coursework.
    </div>
  </div>
</div>
