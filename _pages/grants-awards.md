---
layout: page
title: Grants & Awards
permalink: /grants-awards/
nav: true
nav_order: 4
description: 
---

<style>
  .ga-hero {
    position: relative;
    overflow: hidden;
    padding: 2.5rem 2rem;
    border-radius: 24px;
    margin-bottom: 2rem;
    color: white;
    background: linear-gradient(-45deg, #0f172a, #1d4ed8, #0ea5e9, #7c3aed);
    background-size: 400% 400%;
    animation: gaGradientFlow 12s ease infinite;
    box-shadow: 0 18px 40px rgba(15, 23, 42, 0.22);
  }

  .ga-hero::before,
  .ga-hero::after {
    content: "";
    position: absolute;
    border-radius: 50%;
    filter: blur(40px);
    opacity: 0.35;
    pointer-events: none;
  }

  .ga-hero::before {
    width: 220px;
    height: 220px;
    background: rgba(255,255,255,0.18);
    top: -60px;
    right: -40px;
    animation: gaFloat 8s ease-in-out infinite;
  }

  .ga-hero::after {
    width: 180px;
    height: 180px;
    background: rgba(255,255,255,0.12);
    bottom: -50px;
    left: -30px;
    animation: gaFloat 10s ease-in-out infinite reverse;
  }

  .ga-hero h1 {
    margin: 0 0 0.7rem 0;
    font-size: 2.4rem;
    color: white;
  }

  .ga-hero p {
    margin: 0;
    max-width: 850px;
    font-size: 1.05rem;
    line-height: 1.8;
    color: rgba(255,255,255,0.95);
  }

  .ga-section-title {
    margin-top: 2.2rem;
    margin-bottom: 1rem;
    font-size: 1.75rem;
    font-weight: 800;
    letter-spacing: 0.2px;
  }

  .ga-section-title.grants {
    color: #1d4ed8;
  }

  .ga-section-title.honors {
    color: #b45309;
  }

  .ga-grid {
    display: grid;
    gap: 1.25rem;
  }

  .ga-card {
    position: relative;
    padding: 1.4rem 1.4rem 1.2rem 1.4rem;
    border-radius: 20px;
    overflow: hidden;
    background: rgba(255,255,255,0.92);
    backdrop-filter: blur(8px);
    border: 1px solid rgba(255,255,255,0.5);
    box-shadow: 0 10px 28px rgba(15, 23, 42, 0.08);
    transition: transform 0.35s ease, box-shadow 0.35s ease, border-color 0.35s ease;
    animation: gaFadeUp 0.8s ease both;
  }

  .ga-card:hover {
    transform: translateY(-8px);
    box-shadow: 0 20px 40px rgba(15, 23, 42, 0.14);
  }

  .ga-card::before {
    content: "";
    position: absolute;
    inset: 0;
    opacity: 0;
    transition: opacity 0.35s ease;
    pointer-events: none;
    background: linear-gradient(135deg, rgba(255,255,255,0.22), rgba(255,255,255,0.04));
  }

  .ga-card:hover::before {
    opacity: 1;
  }

  .ga-blue { border-left: 6px solid #2563eb; background: linear-gradient(180deg, #f8fbff, #eef6ff); }
  .ga-purple { border-left: 6px solid #7c3aed; background: linear-gradient(180deg, #fcfaff, #f5f0ff); }
  .ga-green { border-left: 6px solid #059669; background: linear-gradient(180deg, #f4fff9, #ebfff5); }
  .ga-orange { border-left: 6px solid #ea580c; background: linear-gradient(180deg, #fff9f4, #fff1e7); }
  .ga-red { border-left: 6px solid #dc2626; background: linear-gradient(180deg, #fff8f8, #fff1f1); }
  .ga-cyan { border-left: 6px solid #0891b2; background: linear-gradient(180deg, #f4fcff, #ebfbff); }
  .ga-gold { border-left: 6px solid #ca8a04; background: linear-gradient(180deg, #fffdf4, #fff9df); }
  .ga-violet { border-left: 6px solid #9333ea; background: linear-gradient(180deg, #fcf8ff, #f7efff); }

  .ga-card h3 {
    margin-top: 0;
    margin-bottom: 0.8rem;
    font-size: 1.25rem;
  }

  .ga-card p {
    margin: 0.55rem 0;
    line-height: 1.75;
  }

  .ga-card strong {
    font-weight: 700;
  }

  .ga-badges {
    display: flex;
    flex-wrap: wrap;
    gap: 0.65rem;
    margin-top: 1rem;
  }

  .ga-badge {
    display: inline-flex;
    align-items: center;
    gap: 0.45rem;
    padding: 0.55rem 0.9rem;
    border-radius: 999px;
    font-size: 0.95rem;
    font-weight: 700;
    color: #0f172a;
    background: rgba(255,255,255,0.8);
    border: 1px solid rgba(15, 23, 42, 0.08);
    box-shadow: 0 6px 16px rgba(15, 23, 42, 0.06);
    transition: transform 0.25s ease, box-shadow 0.25s ease;
    animation: gaPopIn 0.6s ease both;
  }

  .ga-badge:hover {
    transform: scale(1.06);
    box-shadow: 0 10px 18px rgba(15, 23, 42, 0.12);
  }

  .ga-link-btn {
    display: inline-block;
    margin-top: 0.7rem;
    padding: 0.65rem 1rem;
    border-radius: 999px;
    text-decoration: none !important;
    font-weight: 700;
    color: white !important;
    background: linear-gradient(90deg, #2563eb, #7c3aed);
    box-shadow: 0 10px 22px rgba(37, 99, 235, 0.22);
    transition: transform 0.25s ease, box-shadow 0.25s ease, filter 0.25s ease;
  }

  .ga-link-btn:hover {
    transform: translateY(-2px);
    filter: brightness(1.03);
    box-shadow: 0 14px 28px rgba(37, 99, 235, 0.28);
  }

  .ga-feature-list {
    margin-top: 0.6rem;
    padding-left: 1.2rem;
  }

  .ga-feature-list li {
    margin-bottom: 0.45rem;
    line-height: 1.7;
  }

  .ga-divider {
    height: 1px;
    border: none;
    margin: 2rem 0 1rem 0;
    background: linear-gradient(to right, transparent, rgba(148,163,184,0.55), transparent);
  }

  @keyframes gaGradientFlow {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
  }

  @keyframes gaFloat {
    0% { transform: translateY(0px) translateX(0px); }
    50% { transform: translateY(18px) translateX(8px); }
    100% { transform: translateY(0px) translateX(0px); }
  }

  @keyframes gaFadeUp {
    from {
      opacity: 0;
      transform: translateY(18px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  @keyframes gaPopIn {
    from {
      opacity: 0;
      transform: scale(0.9);
    }
    to {
      opacity: 1;
      transform: scale(1);
    }
  }

  @media (prefers-reduced-motion: reduce) {
    .ga-hero,
    .ga-hero::before,
    .ga-hero::after,
    .ga-card,
    .ga-badge {
      animation: none !important;
    }

    .ga-card,
    .ga-badge,
    .ga-link-btn {
      transition: none !important;
    }
  }
</style>

<div class="ga-hero">
  <h1>Grants & Awards</h1>
  <p>
    An overview of externally funded research grants, academic honors, and scholarly recognitions reflecting contributions to Advanced AI, federated learning, multimodal LLMs and cybersecurity.
  </p>
</div>

## <span class="ga-section-title grants">Research Grants</span>

<div class="ga-grid">

  <div class="ga-card ga-blue">
    <h3>💡 NSF CISE CRII Grant | $167,500 | Sole PI</h3>
      <p>
    Awarded the prestigious <strong>National Science Foundation CISE Research Initiation Initiative (CRII)</strong> grant supporting foundational research in distributed and robust AI systems.
  </p>

  <p style="margin-top: 0.6rem;">
    <strong>Project Title:</strong><br>
    <span style="color:#1d4ed8; font-weight:600;">
      CRII: RI: Federated Meta-Learning for Cross-Network Crime Analytics in Interdependent Environments
    </span>
  </p>

  <a class="ga-link-btn" href="https://www.nsf.gov/awardsearch/show-award?AWD_ID=2553868" target="_blank">
    View NSF Award Page
  </a>

    <p><strong>📚 Publications from this Grant</strong></p>
    <div class="ga-badges">
      <span class="ga-badge">🧠 CVPR 2025 | 2 papers</span>
      <span class="ga-badge">🌱 IEEE Transations on Sustanaible Computing | 1 paper</span>
      <span class="ga-badge">🎥 ICCV-W 2025 | 1 paper</span>
      <span class="ga-badge">🌐 ICDCS 2024 | 1 paper</span>
      <span class="ga-badge">💻 COMPSAC 2024 | 1 paper</span>
      <span class="ga-badge">🤖 ICMLA 2025 | 1 paper</span>
      <span class="ga-badge">📡 IEEE Consumer Electronics | 1 paper</span>
    </div>
  </div>

  <div class="ga-card ga-purple">
    <h3>🚀 NSF NAIRR Pilot Grant | Sole PI</h3>
    <p>
      Awarded the <strong>NSF National Artificial Intelligence Research Resource (NAIRR) Pilot</strong> grant for the project:
    </p>
    <p>
      <strong>“ARMOR-HAL: Unified Defense for Adversarial Robustness and Hallucination Mitigation in Large Vision-Language Models.”</strong>
    </p>
    <p>
      This project advances secure and dependable AI systems through unified defense frameworks for large vision language models.
    </p>
    <a class="ga-link-btn" href="https://nairrpilot.org/projects/awarded?_requestNumber=NAIRR250393" target="_blank">
      View Project Details
    </a>
  </div>

  <div class="ga-card ga-green">
    <h3>🌟 ORAU Research Innovation Partnership Grant | Lead PI</h3>
    <p>
      Received the <strong>ORAU Research Innovation Partnership Grant</strong> as <strong>Lead PI</strong>.
    </p>
    <p>
      Funded by <strong>Oak Ridge Associated Universities (ORAU)</strong>, this program supports innovative initiatives that foster
      interdisciplinary collaboration among university members and domain experts.
    </p>
  </div>

  <div class="ga-card ga-orange">
    <h3>🛡️ DHS CINA Grant | Collaboration with FIU | SIU PI</h3>
    <p>
      Awarded a competitive grant from the <strong>U.S. Department of Homeland Security (DHS)</strong> under the
      <strong>Criminal Investigations and Network Analysis Center (CINA)</strong> program.
    </p>
    <p>
      This project supported research and education at the intersection of artificial intelligence, public safety, and criminal activity recognition.
    </p>
    <ul class="ga-feature-list">
      <li><a href="https://thesouthern.com/news/local/education/siu-carbondale-professor-artificial-intelligence/article_adba3f3e-92fb-11ee-b904-bb81335ddd06.html" target="_blank">Southern Illinoisan News</a></li>
      <li><a href="https://cs.siu.edu/about_us/news/dhsgrant2023.php" target="_blank">SIU Computer Science News</a></li>
    </ul>
  </div>

</div>

<hr class="ga-divider">

## <span class="ga-section-title honors">Academic Honors & Distinctions</span>

<div class="ga-grid">

  <div class="ga-card ga-red">
    <h3>🏆 Outstanding Teacher of the Year Award | 2024</h3>
    <p>
      Recipient of the <strong>Outstanding Teacher of the Year Award</strong> from the School of Computing at
      <strong>Southern Illinois University</strong>, recognizing excellence in teaching, mentorship, and curriculum development.
    </p>
  </div>

  <div class="ga-card ga-cyan">
    <h3>🎓 FIU 2022 Real Triumphs Graduate Award</h3>
    <p>
      Recipient of the prestigious <strong>2022 Real Triumphs Graduate Award</strong> from
      <strong>Florida International University</strong>.
    </p>
    <p>
      Each commencement, FIU recognizes a select group of graduates whose academic excellence, perseverance, and future promise distinguish them among their peers.
    </p>
    <a class="ga-link-btn" href="https://www.youtube.com/clip/UgkxqjRl_qBIfseaXUGYMWGNl13bkWGNZImF" target="_blank">
      Watch Recognition Video
    </a>
    <br>
    <a class="ga-link-btn" href="https://bit.ly/3lY4ESK" target="_blank" style="margin-top: 0.8rem;">
      View Award Details
    </a>
  </div>

  <div class="ga-card ga-gold">
    <h3>🏅 University-Wide Outstanding Master’s Degree Graduate Award</h3>
    <p>
      Recipient of the <strong>University-Wide Outstanding Master’s Degree Graduate Award</strong>, presented to one master’s graduate in recognition of exceptional academic achievement, impactful research contributions, and dedicated service.
    </p>
  </div>

  <div class="ga-card ga-violet">
    <h3>📄 Best Paper Award | CSCI 2019</h3>
    <p>
      Received the <strong>Best Paper Award at CSCI 2019</strong> for research on distributed IoT sensing and federated learning, with a focus on scalable and privacy-preserving distributed learning frameworks.
    </p>
  </div>

</div>
