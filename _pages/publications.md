---
layout: page
permalink: /publications/
title: Publications
nav: true
nav_order: 2
---

<style>
/* Hide default title + description */
.post-title,
.page-title,
.post-description,
.page-description,
.subtitle {
  display: none !important;
}

/* HERO */
.pub-hero {
  padding: 2.8rem 2rem;
  border-radius: 26px;
  margin-bottom: 2rem;
  color: white;
  background: linear-gradient(-45deg, #0f172a, #1d4ed8, #7c3aed, #14b8a6);
  background-size: 400% 400%;
  animation: gradientMove 15s ease infinite;
  box-shadow: 0 20px 40px rgba(0,0,0,0.15);
}

.pub-hero h1 {
  margin: 0;
  font-size: 2.5rem;
  color: white;
}

.pub-hero p {
  margin-top: 0.5rem;
  max-width: 800px;
  opacity: 0.95;
}

/* MAIN CONTAINER */
.publications {
  margin-top: 1rem;
}

/* REMOVE OLD NUMBER + BADGE */
.publications ol.bibliography li::before {
  display: none !important;
}

.publications .abbr {
  display: none !important;
}

/* PUBLICATION CARD */
.publications ol.bibliography li {
  list-style: none;
  margin-bottom: 1.6rem;
  padding: 1.4rem;
  border-radius: 20px;
  background: linear-gradient(180deg, #ffffff, #f8fafc);
  border: 1px solid rgba(226,232,240,0.8);
  box-shadow: 0 12px 28px rgba(15,23,42,0.06);
  transition: all 0.3s ease;
  animation: fadeUp 0.8s ease both;
}

.publications ol.bibliography li:hover {
  transform: translateY(-6px);
  box-shadow: 0 20px 40px rgba(15,23,42,0.12);
}

/* VENUE TAG */
.publications .venue,
.publications .periodical,
.publications em {
  display: inline-block;
  margin-bottom: 0.6rem;
  padding: 0.35rem 0.75rem;
  border-radius: 999px;
  font-size: 0.8rem;
  font-weight: 800;
  color: white;
  background: linear-gradient(90deg, #2563eb, #7c3aed);
  box-shadow: 0 6px 14px rgba(37,99,235,0.25);
}

/* TITLE */
.publications .title {
  font-size: 1.05rem;
  font-weight: 800;
  color: #0f172a;
  line-height: 1.5;
}

/* AUTHORS */
.publications .author,
.publications .authors {
  color: #475569;
  font-size: 0.95rem;
}

/* LINKS AS BUTTONS */
.publications .links a,
.publications .btn,
.publications .btn-group a {
  display: inline-flex;
  align-items: center;
  gap: 0.4rem;
  padding: 0.5rem 0.9rem;
  border-radius: 999px;
  font-size: 0.85rem;
  font-weight: 700;
  color: white !important;
  background: linear-gradient(90deg, #2563eb, #7c3aed);
  text-decoration: none !important;
  box-shadow: 0 8px 18px rgba(37,99,235,0.18);
  transition: all 0.25s ease;
}

.publications .links a:hover {
  transform: translateY(-2px);
  box-shadow: 0 12px 22px rgba(37,99,235,0.25);
}

/* IMAGE BELOW */
.publications img {
  display: block;
  margin: 1rem auto 0 auto;
  max-width: 260px;
  border-radius: 16px;
  box-shadow: 0 10px 22px rgba(0,0,0,0.12);
  transition: transform 0.3s ease;
}

.publications img:hover {
  transform: scale(1.04);
}

/* SEARCH BOX */
.bibliography-search {
  padding: 1.2rem;
  border-radius: 20px;
  background: linear-gradient(180deg, #fcfaff, #f5f0ff);
  margin-bottom: 1.2rem;
}

.bibliography-search input {
  border-radius: 14px !important;
  padding: 0.8rem !important;
  border: 1px solid #ddd !important;
}

/* ANIMATIONS */
@keyframes gradientMove {
  0% {background-position:0% 50%;}
  50% {background-position:100% 50%;}
  100% {background-position:0% 50%;}
}

@keyframes fadeUp {
  from {opacity:0; transform:translateY(15px);}
  to {opacity:1; transform:translateY(0);}
}
</style>

<div class="pub-hero">
  <h1>Publications</h1>
  <p>
    A curated list of research publications in reverse chronological order,
    covering robust AI, vision-language models, federated learning, and multimodal intelligence.
  </p>
</div>

{% include bib_search.liquid %}

<div class="publications">
  {% bibliography %}
</div>
