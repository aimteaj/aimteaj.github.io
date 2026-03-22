---
layout: page
permalink: /publications/
title: Publications
description: publications by categories in reversed chronological order.
nav: true
nav_order: 2
---

<style>
  .post-title,
  .page-title,
  .post-description,
  .page-description,
  h1.post-title,
  .subtitle {
    display: none !important;
  }

  .pub-page {
    position: relative;
  }

  .pub-hero {
    position: relative;
    overflow: hidden;
    padding: 2.9rem 2rem;
    border-radius: 28px;
    margin-bottom: 2rem;
    color: white;
    background: linear-gradient(-45deg, #0f172a, #1d4ed8, #7c3aed, #14b8a6, #0ea5e9);
    background-size: 500% 500%;
    animation: pubGradient 16s ease infinite;
    box-shadow: 0 22px 46px rgba(15, 23, 42, 0.18);
  }

  .pub-hero::before,
  .pub-hero::after {
    content: "";
    position: absolute;
    border-radius: 50%;
    filter: blur(48px);
    pointer-events: none;
    opacity: 0.24;
  }

  .pub-hero::before {
    width: 250px;
    height: 250px;
    background: rgba(255,255,255,0.18);
    top: -80px;
    right: -40px;
    animation: pubFloat 10s ease-in-out infinite;
  }

  .pub-hero::after {
    width: 180px;
    height: 180px;
    background: rgba(255,255,255,0.12);
    bottom: -50px;
    left: -20px;
    animation: pubFloat 12s ease-in-out infinite reverse;
  }

  .pub-hero h1 {
    margin: 0 0 0.75rem 0;
    font-size: 2.6rem;
    color: white;
    letter-spacing: 0.2px;
  }

  .pub-hero p {
    margin: 0;
    max-width: 900px;
    font-size: 1.05rem;
    line-height: 1.9;
    color: rgba(255,255,255,0.96);
  }

  .pub-hero-badges {
    display: flex;
    flex-wrap: wrap;
    gap: 0.7rem;
    margin-top: 1.2rem;
  }

  .pub-hero-badge {
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
    animation: pubPop 0.7s ease both;
  }

  .pub-shell {
    position: relative;
    padding: 1.4rem;
    border-radius: 26px;
    background: linear-gradient(180deg, rgba(248,250,252,0.96), rgba(241,245,249,0.90));
    border: 1px solid rgba(226,232,240,0.85);
    box-shadow: 0 16px 36px rgba(15, 23, 42, 0.06);
    backdrop-filter: blur(8px);
  }

  .pub-shell::before {
    content: "";
    position: absolute;
    inset: 0;
    border-radius: 26px;
    pointer-events: none;
    background: linear-gradient(135deg, rgba(255,255,255,0.18), rgba(255,255,255,0.03));
  }

  .pub-intro-card {
    position: relative;
    overflow: hidden;
    padding: 1.35rem 1.35rem 1.2rem 1.35rem;
    margin-bottom: 1.35rem;
    border-radius: 22px;
    background: linear-gradient(180deg, #f8fbff, #eef6ff);
    border: 1px solid rgba(255,255,255,0.58);
    border-left: 6px solid #2563eb;
    box-shadow: 0 12px 30px rgba(15, 23, 42, 0.07);
    animation: pubFadeUp 0.85s ease both;
  }

  .pub-intro-title {
    display: inline-flex;
    align-items: center;
    gap: 0.55rem;
    margin: 0 0 0.8rem 0;
    padding: 0.62rem 1rem;
    border-radius: 999px;
    font-size: 1rem;
    font-weight: 800;
    color: #0f172a;
    background: linear-gradient(90deg, rgba(37,99,235,0.12), rgba(124,58,237,0.10));
    border: 1px solid rgba(37,99,235,0.10);
    box-shadow: 0 8px 18px rgba(15, 23, 42, 0.05);
  }

  .pub-intro-card p {
    margin: 0;
    color: #334155;
    line-height: 1.85;
    font-size: 0.98rem;
  }

  .publications {
    position: relative;
    z-index: 2;
  }

  .publications h2 {
    display: inline-flex;
    align-items: center;
    gap: 0.55rem;
    margin-top: 1.2rem;
    margin-bottom: 1rem;
    padding: 0.68rem 1rem;
    border-radius: 999px;
    font-size: 1.15rem;
    font-weight: 800;
    color: #0f172a;
    background: linear-gradient(90deg, rgba(37,99,235,0.10), rgba(124,58,237,0.09));
    border: 1px solid rgba(37,99,235,0.10);
    box-shadow: 0 8px 18px rgba(15, 23, 42, 0.04);
    animation: pubFadeUp 0.85s ease both;
  }

  .publications h2::before {
    content: "📚";
    font-size: 0.95rem;
  }

  .publications ol.bibliography {
    list-style: none;
    padding-left: 0;
    counter-reset: pub-counter;
  }

  .publications ol.bibliography li {
    counter-increment: pub-counter;
    position: relative;
    margin-bottom: 1.35rem;
    padding: 1.35rem 1.35rem 1.2rem 1.35rem;
    border-radius: 22px;
    background: linear-gradient(180deg, rgba(255,255,255,0.95), rgba(248,250,252,0.92));
    border: 1px solid rgba(226,232,240,0.85);
    box-shadow: 0 12px 28px rgba(15, 23, 42, 0.06);
    transition: transform 0.35s ease, box-shadow 0.35s ease;
    animation: pubFadeUp 0.85s ease both;
    overflow: hidden;
  }

  .publications ol.bibliography li:hover {
    transform: translateY(-6px);
    box-shadow: 0 20px 38px rgba(15, 23, 42, 0.11);
  }

  .publications ol.bibliography li::before {
    content: counter(pub-counter);
    position: absolute;
    top: 1rem;
    right: 1rem;
    width: 34px;
    height: 34px;
    border-radius: 999px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: linear-gradient(90deg, #2563eb, #7c3aed);
    color: white;
    font-weight: 800;
    font-size: 0.88rem;
    box-shadow: 0 8px 18px rgba(37,99,235,0.18);
  }

  .publications ol.bibliography li::after {
    content: "";
    position: absolute;
    inset: 0;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.35s ease;
    background: linear-gradient(135deg, rgba(37,99,235,0.05), rgba(124,58,237,0.05), rgba(20,184,166,0.05));
  }

  .publications ol.bibliography li:hover::after {
    opacity: 1;
  }

  .publications .title {
    font-size: 1.08rem;
    font-weight: 800;
    color: #0f172a;
    line-height: 1.55;
  }

  .publications .author,
  .publications .authors {
    color: #475569;
    line-height: 1.75;
    font-size: 0.97rem;
  }

  .publications .year {
    color: #1d4ed8;
    font-weight: 800;
  }

  .publications .periodical,
  .publications .venue,
  .publications em {
    color: #6d28d9;
    font-style: italic;
    font-weight: 650;
  }

  .publications a {
    color: #1d4ed8;
    font-weight: 700;
    text-decoration: none !important;
    transition: color 0.25s ease, opacity 0.25s ease;
  }

  .publications a:hover {
    color: #7c3aed;
    opacity: 0.95;
  }

  .publications .abbr {
    display: inline-flex;
    align-items: center;
    padding: 0.38rem 0.7rem;
    border-radius: 999px;
    background: rgba(37,99,235,0.10);
    border: 1px solid rgba(37,99,235,0.10);
    color: #1d4ed8;
    font-size: 0.82rem;
    font-weight: 800;
    margin-right: 0.45rem;
  }

  .publications .award {
    display: inline-flex;
    align-items: center;
    padding: 0.38rem 0.7rem;
    border-radius: 999px;
    background: rgba(234,179,8,0.12);
    border: 1px solid rgba(234,179,8,0.16);
    color: #a16207;
    font-size: 0.82rem;
    font-weight: 800;
    margin-left: 0.45rem;
  }

  .publications .links,
  .publications .badges,
  .publications .btn-group {
    display: flex;
    flex-wrap: wrap;
    gap: 0.55rem;
    margin-top: 0.9rem;
  }

  .publications .links a,
  .publications .badges a,
  .publications .btn-group a,
  .publications .btn {
    display: inline-flex;
    align-items: center;
    gap: 0.45rem;
    padding: 0.55rem 0.95rem;
    border-radius: 999px !important;
    font-size: 0.9rem;
    font-weight: 700;
    text-decoration: none !important;
    border: none !important;
    color: white !important;
    background: linear-gradient(90deg, #2563eb, #7c3aed) !important;
    box-shadow: 0 8px 18px rgba(37,99,235,0.18);
    transition: transform 0.25s ease, box-shadow 0.25s ease, filter 0.25s ease;
  }

  .publications .links a:hover,
  .publications .badges a:hover,
  .publications .btn-group a:hover,
  .publications .btn:hover {
    transform: translateY(-3px);
    box-shadow: 0 14px 24px rgba(37,99,235,0.24);
    filter: brightness(1.03);
  }

  .publications .abstract,
  .publications .bibtex,
  .publications .hidden {
    margin-top: 0.9rem;
    padding: 1rem 1rem;
    border-radius: 16px;
    background: linear-gradient(180deg, #f8fafc, #ffffff);
    border: 1px solid rgba(226,232,240,0.8);
    box-shadow: 0 8px 18px rgba(15, 23, 42, 0.04);
  }

  .publications pre,
  .publications code {
    border-radius: 14px;
  }

  .publications pre {
    padding: 0.95rem 1rem !important;
    background: #0f172a !important;
    color: #e2e8f0 !important;
    box-shadow: 0 10px 22px rgba(15, 23, 42, 0.12);
  }

  .publications .selected,
  .publications .featured {
    position: relative;
  }

  .publications .selected::after,
  .publications .featured::after {
    content: "Featured";
    display: inline-flex;
    align-items: center;
    margin-left: 0.6rem;
    padding: 0.35rem 0.65rem;
    border-radius: 999px;
    background: rgba(16,185,129,0.10);
    border: 1px solid rgba(16,185,129,0.16);
    color: #047857;
    font-size: 0.8rem;
    font-weight: 800;
    vertical-align: middle;
  }

  .bibliography-search {
    position: relative;
    margin-bottom: 1.3rem;
    padding: 1.2rem;
    border-radius: 22px;
    background: linear-gradient(180deg, #fcfaff, #f5f0ff);
    border: 1px solid rgba(226,232,240,0.82);
    box-shadow: 0 12px 26px rgba(15, 23, 42, 0.05);
    animation: pubFadeUp 0.8s ease both;
  }

  .bibliography-search input,
  .bibliography-search .search,
  .bibsearch input,
  input[type="text"] {
    border-radius: 16px !important;
    border: 1px solid rgba(203,213,225,0.9) !important;
    padding: 0.85rem 1rem !important;
    box-shadow: none !important;
    transition: border-color 0.25s ease, box-shadow 0.25s ease, transform 0.25s ease;
  }

  .bibliography-search input:focus,
  .bibliography-search .search:focus,
  .bibsearch input:focus,
  input[type="text"]:focus {
    border-color: #7c3aed !important;
    box-shadow: 0 0 0 4px rgba(124,58,237,0.10) !important;
    transform: translateY(-1px);
    outline: none !important;
  }

  @keyframes pubGradient {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
  }

  @keyframes pubFloat {
    0% { transform: translateY(0px) translateX(0px); }
    50% { transform: translateY(18px) translateX(8px); }
    100% { transform: translateY(0px) translateX(0px); }
  }

  @keyframes pubFadeUp {
    from {
      opacity: 0;
      transform: translateY(18px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  @keyframes pubPop {
    from {
      opacity: 0;
      transform: scale(0.92);
    }
    to {
      opacity: 1;
      transform: scale(1);
    }
  }

  @media (max-width: 768px) {
    .pub-hero {
      padding: 2.3rem 1.35rem;
    }

    .pub-hero h1 {
      font-size: 2.15rem;
    }

    .pub-shell {
      padding: 1rem;
    }

    .publications ol.bibliography li {
      padding: 1.1rem;
    }

    .publications ol.bibliography li::before {
      top: 0.8rem;
      right: 0.8rem;
    }

    .publications .title {
      font-size: 1rem;
      padding-right: 2.2rem;
    }
  }

  @media (prefers-reduced-motion: reduce) {
    .pub-hero,
    .pub-hero::before,
    .pub-hero::after,
    .pub-hero-badge,
    .pub-intro-card,
    .publications h2,
    .publications ol.bibliography li,
    .bibliography-search {
      animation: none !important;
    }

    .publications ol.bibliography li,
    .publications .links a,
    .publications .badges a,
    .publications .btn-group a,
    .publications .btn,
    .bibliography-search input {
      transition: none !important;
    }
  }
</style>

<div class="pub-page">
  <div class="pub-hero">
    <h1>Publications</h1>
    <p>
      A curated list of research publications presented in reverse chronological order, highlighting contributions across secure artificial intelligence, federated learning, vision-language models, multimodal systems, and trustworthy machine learning.
    </p>

    <div class="pub-hero-badges">
      <span class="pub-hero-badge">Reverse Chronological Order</span>
      <span class="pub-hero-badge">Selected Research</span>
      <span class="pub-hero-badge">AI and ML</span>
      <span class="pub-hero-badge">Scholarly Output</span>
    </div>
  </div>

  <div class="pub-shell">
    <div class="pub-intro-card">
      <div class="pub-intro-title">📘 Research Publications</div>
      <p>
        Browse publications by year and category. Use the search box to quickly locate papers by title, venue, topic, or author.
      </p>
    </div>

    {% include bib_search.liquid %}

    <div class="publications">
      {% bibliography %}
    </div>
  </div>
</div>
