---
layout: page
title: Mentorship
permalink: /mentorship/
nav: true
nav_order: 6
description: ""
---

<style>
  .mentor-hero {
    position: relative;
    overflow: hidden;
    padding: 2.5rem 2rem;
    border-radius: 24px;
    margin-bottom: 2rem;
    color: white;
    background: linear-gradient(-45deg, #0f172a, #2563eb, #7c3aed, #14b8a6);
    background-size: 400% 400%;
    animation: mentorGradient 12s ease infinite;
    box-shadow: 0 18px 40px rgba(15, 23, 42, 0.18);
  }

  .mentor-hero::before,
  .mentor-hero::after {
    content: "";
    position: absolute;
    border-radius: 50%;
    filter: blur(40px);
    opacity: 0.26;
    pointer-events: none;
  }

  .mentor-hero::before {
    width: 230px;
    height: 230px;
    background: rgba(255,255,255,0.18);
    top: -80px;
    right: -40px;
    animation: mentorFloat 9s ease-in-out infinite;
  }

  .mentor-hero::after {
    width: 170px;
    height: 170px;
    background: rgba(255,255,255,0.14);
    bottom: -45px;
    left: -25px;
    animation: mentorFloat 11s ease-in-out infinite reverse;
  }

  .mentor-hero h1 {
    margin: 0 0 0.8rem 0;
    font-size: 2.35rem;
    color: white;
  }

  .mentor-hero p {
    margin: 0;
    max-width: 860px;
    font-size: 1.04rem;
    line-height: 1.8;
    color: rgba(255,255,255,0.95);
  }

  .mentor-section-title {
    margin-top: 2rem;
    margin-bottom: 1rem;
    font-size: 1.65rem;
    font-weight: 800;
    letter-spacing: 0.2px;
  }

  .mentor-section-title.phd { color: #1d4ed8; }
  .mentor-section-title.ms { color: #7c3aed; }
  .mentor-section-title.ug { color: #059669; }
  .mentor-section-title.program { color: #ea580c; }
  .mentor-section-title.community { color: #be185d; }

  .mentor-grid {
    display: grid;
    gap: 1.2rem;
  }

  .mentor-card {
    position: relative;
    overflow: hidden;
    padding: 1.35rem 1.35rem 1.2rem 1.35rem;
    border-radius: 20px;
    background: rgba(255,255,255,0.95);
    border: 1px solid rgba(255,255,255,0.5);
    box-shadow: 0 10px 28px rgba(15, 23, 42, 0.07);
    transition: transform 0.35s ease, box-shadow 0.35s ease;
    animation: mentorFadeUp 0.8s ease both;
  }

  .mentor-card:hover {
    transform: translateY(-8px);
    box-shadow: 0 18px 38px rgba(15, 23, 42, 0.13);
  }

  .mentor-card::before {
    content: "";
    position: absolute;
    inset: 0;
    opacity: 0;
    transition: opacity 0.35s ease;
    background: linear-gradient(135deg, rgba(255,255,255,0.20), rgba(255,255,255,0.05));
    pointer-events: none;
  }

  .mentor-card:hover::before {
    opacity: 1;
  }

  .mentor-blue { border-left: 6px solid #2563eb; background: linear-gradient(180deg, #f8fbff, #eef6ff); }
  .mentor-purple { border-left: 6px solid #7c3aed; background: linear-gradient(180deg, #fcfaff, #f5f0ff); }
  .mentor-green { border-left: 6px solid #059669; background: linear-gradient(180deg, #f6fff9, #ecfff5); }
  .mentor-orange { border-left: 6px solid #ea580c; background: linear-gradient(180deg, #fff9f4, #fff1e7); }
  .mentor-pink { border-left: 6px solid #be185d; background: linear-gradient(180deg, #fff8fc, #fff0f7); }

  .mentor-card h3 {
    margin-top: 0;
    margin-bottom: 0.35rem;
    font-size: 1.05rem;
    font-weight: 750;
    color: #0f172a;
  }

  .mentor-subtitle {
    font-size: 0.92rem;
    font-weight: 650;
    color: #475569;
    margin-bottom: 0.85rem;
  }

  .mentor-card p {
    margin: 0.45rem 0;
    line-height: 1.75;
    color: #334155;
  }

  .mentor-list {
    display: grid;
    gap: 0.75rem;
    margin-top: 0.8rem;
  }

  .mentor-item {
    display: flex;
    align-items: flex-start;
    gap: 0.8rem;
    padding: 0.9rem 1rem;
    border-radius: 14px;
    background: rgba(255,255,255,0.76);
    border: 1px solid rgba(148,163,184,0.16);
    box-shadow: 0 6px 14px rgba(15, 23, 42, 0.04);
    transition: transform 0.25s ease, box-shadow 0.25s ease;
  }

  .mentor-item:hover {
    transform: translateX(4px);
    box-shadow: 0 10px 18px rgba(15, 23, 42, 0.08);
  }

  .mentor-icon {
    font-size: 1.02rem;
    line-height: 1.5;
    margin-top: 0.06rem;
  }

  .mentor-name {
    font-weight: 750;
    color: #0f172a;
  }

  .mentor-role {
    color: #475569;
    font-weight: 600;
    margin-top: 0.1rem;
  }

  .mentor-topic {
    color: #334155;
    margin-top: 0.18rem;
    line-height: 1.6;
  }

  .mentor-badges {
    display: flex;
    flex-wrap: wrap;
    gap: 0.65rem;
    margin-top: 1rem;
  }

  .mentor-badge {
    display: inline-flex;
    align-items: center;
    padding: 0.55rem 0.95rem;
    border-radius: 999px;
    background: rgba(255,255,255,0.84);
    color: #0f172a;
    font-size: 0.93rem;
    font-weight: 700;
    border: 1px solid rgba(148,163,184,0.18);
    box-shadow: 0 6px 14px rgba(15, 23, 42, 0.05);
    transition: transform 0.25s ease, box-shadow 0.25s ease;
    animation: mentorPop 0.6s ease both;
  }

  .mentor-badge:hover {
    transform: scale(1.05);
    box-shadow: 0 10px 18px rgba(15, 23, 42, 0.10);
  }

  .mentor-highlight {
    display: inline-block;
    margin-top: 0.8rem;
    padding: 0.75rem 1rem;
    border-radius: 16px;
    background: linear-gradient(90deg, rgba(37,99,235,0.10), rgba(124,58,237,0.10));
    border: 1px solid rgba(37,99,235,0.14);
    color: #0f172a;
    font-weight: 650;
  }

  .mentor-columns {
    display: grid;
    grid-template-columns: 1fr;
    gap: 1.2rem;
  }

  .mentor-divider {
    height: 1px;
    border: none;
    margin: 2rem 0 1rem 0;
    background: linear-gradient(to right, transparent, rgba(148,163,184,0.5), transparent);
  }

  @media (min-width: 980px) {
    .mentor-columns.two {
      grid-template-columns: 1fr 1fr;
    }
  }

  @keyframes mentorGradient {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
  }

  @keyframes mentorFloat {
    0% { transform: translateY(0px) translateX(0px); }
    50% { transform: translateY(18px) translateX(8px); }
    100% { transform: translateY(0px) translateX(0px); }
  }

  @keyframes mentorFadeUp {
    from {
      opacity: 0;
      transform: translateY(18px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  @keyframes mentorPop {
    from {
      opacity: 0;
      transform: scale(0.92);
    }
    to {
      opacity: 1;
      transform: scale(1);
    }
  }

  @media (prefers-reduced-motion: reduce) {
    .mentor-hero,
    .mentor-hero::before,
    .mentor-hero::after,
    .mentor-card,
    .mentor-badge {
      animation: none !important;
    }

    .mentor-card,
    .mentor-item,
    .mentor-badge {
      transition: none !important;
    }
  }
</style>

<div class="mentor-hero">
  <p>
    A record of student advising, research mentorship, and academic guidance across doctoral, master’s, undergraduate, and community-centered programs.
  </p>
</div>

## <span class="mentor-section-title phd">PhD Students</span>

<div class="mentor-grid">
  <div class="mentor-card mentor-blue">
    <h3>🎓 Doctoral Advising</h3>
    <div class="mentor-subtitle">Current PhD mentees</div>

    <div class="mentor-list">
      <div class="mentor-item">
        <div class="mentor-icon">🔹</div>
        <div>
          <div class="mentor-name">Md Zarif Hossain</div>
          <div class="mentor-role">PhD Candidate</div>
        </div>
      </div>

      <div class="mentor-item">
        <div class="mentor-icon">🔹</div>
        <div>
          <div class="mentor-name">Awal Ahmed Fime</div>
          <div class="mentor-role">PhD Student</div>
        </div>
      </div>
    </div>

    <div class="mentor-highlight">
      Mentoring doctoral researchers in advanced AI, secure learning systems, and next-generation multimodal intelligence.
    </div>
  </div>
</div>

<hr class="mentor-divider">

## <span class="mentor-section-title ms">Graduated MS Thesis and Project Students</span>

<div class="mentor-grid">
  <div class="mentor-card mentor-purple">
    <h3>📚 Master’s Student Mentorship</h3>
    <div class="mentor-subtitle">Graduated thesis and project students</div>

    <div class="mentor-list">
      <div class="mentor-item">
        <div class="mentor-icon">📘</div>
        <div>
          <div class="mentor-name">Dina Famouri</div>
          <div class="mentor-topic">Human Activity Recognition with Keypoint Analysis</div>
        </div>
      </div>

      <div class="mentor-item">
        <div class="mentor-icon">📘</div>
        <div>
          <div class="mentor-name">Oleksandr Jockusch</div>
          <div class="mentor-topic">Federated Meta-Learning for Emotion and Sentiment-Aware Multi-modal Complaint Identification</div>
        </div>
      </div>

      <div class="mentor-item">
        <div class="mentor-icon">📘</div>
        <div>
          <div class="mentor-name">Revathi Gajjala</div>
          <div class="mentor-topic">Physics-Informed Neural Networks</div>
        </div>
      </div>

      <div class="mentor-item">
        <div class="mentor-icon">📘</div>
        <div>
          <div class="mentor-name">Veerendra Reddy Ayaluri</div>
          <div class="mentor-topic">Federated Learning Testbed for Mobile Agents</div>
        </div>
      </div>

      <div class="mentor-item">
        <div class="mentor-icon">📘</div>
        <div>
          <div class="mentor-name">Sai Sandhiptha Bayya</div>
          <div class="mentor-topic">Ensuring Fairness in Federated Learning for Healthcare Systems</div>
        </div>
      </div>

      <div class="mentor-item">
        <div class="mentor-icon">📘</div>
        <div>
          <div class="mentor-name">Mark Sidhom</div>
          <div class="mentor-topic">Fine-Tuned LLM for Healthcare</div>
        </div>
      </div>

      <div class="mentor-item">
        <div class="mentor-icon">📘</div>
        <div>
          <div class="mentor-name">Prince Duo</div>
          <div class="mentor-topic">Hallucination Attacks and Impacts on Large-Language Models</div>
        </div>
      </div>

      <div class="mentor-item">
        <div class="mentor-icon">📘</div>
        <div>
          <div class="mentor-name">Venkata Gnana Prakash Paruchuri</div>
          <div class="mentor-topic">Topic Modeling on Research Articles using BERT</div>
        </div>
      </div>

      <div class="mentor-item">
        <div class="mentor-icon">📘</div>
        <div>
          <div class="mentor-name">Gireesh Nadh Mekala</div>
          <div class="mentor-topic">Road Traffic Prediction using Federated Learning</div>
        </div>
      </div>

      <div class="mentor-item">
        <div class="mentor-icon">📘</div>
        <div>
          <div class="mentor-name">Srivatsa Tangirala</div>
          <div class="mentor-topic">Poisoning Attacks in Federated Learning using GANs</div>
        </div>
      </div>

      <div class="mentor-item">
        <div class="mentor-icon">📘</div>
        <div>
          <div class="mentor-name">Madhu Nimeshika Dasika</div>
          <div class="mentor-topic">Skin Cancer Classification using Transfer Learning</div>
        </div>
      </div>

      <div class="mentor-item">
        <div class="mentor-icon">📘</div>
        <div>
          <div class="mentor-name">Wasimuddin Fathimullah</div>
          <div class="mentor-topic">Intrusion Detection with Federated Reinforcement Learning</div>
        </div>
      </div>
    </div>

    <div class="mentor-badges">
      <span class="mentor-badge">AI Research Mentorship</span>
      <span class="mentor-badge">Thesis Supervision</span>
      <span class="mentor-badge">Project Advising</span>
      <span class="mentor-badge">Applied Machine Learning</span>
    </div>
  </div>
</div>

<hr class="mentor-divider">

## <span class="mentor-section-title ug">Undergraduate Research Students</span>

<div class="mentor-grid">
  <div class="mentor-card mentor-green">
    <h3>🧪 Undergraduate Research Mentorship</h3>
    <div class="mentor-subtitle">Student researchers engaged in advanced AI projects</div>

    <div class="mentor-list">
      <div class="mentor-item">
        <div class="mentor-icon">🌱</div>
        <div>
          <div class="mentor-name">Nadia D Lafontant</div>
          <div class="mentor-topic">Resource-Efficient Fine-Tuning of Vision-Language Models</div>
        </div>
      </div>

      <div class="mentor-item">
        <div class="mentor-icon">🌱</div>
        <div>
          <div class="mentor-name">Ian Tudor</div>
          <div class="mentor-topic">Drone Swarming, Distributed Streaming, and Learning</div>
        </div>
      </div>
    </div>

    <div class="mentor-highlight">
      Supporting undergraduate researchers through hands-on projects in efficient AI, distributed systems, and emerging multimodal technologies.
    </div>
  </div>
</div>

<hr class="mentor-divider">

## <span class="mentor-section-title program">Program Mentorship</span>

<div class="mentor-columns two">
  <div class="mentor-card mentor-orange">
    <h3>🧑‍🏫 NSF-DoD REU Site Mentor</h3>
    <div class="mentor-subtitle">Research Experiences for Undergraduates</div>

    <div class="mentor-list">
      <div class="mentor-item">
        <div class="mentor-icon">⭐</div>
        <div>
          <div class="mentor-name">Raghad Alabagi</div>
        </div>
      </div>

      <div class="mentor-item">
        <div class="mentor-icon">⭐</div>
        <div>
          <div class="mentor-name">Meileik Hyman</div>
        </div>
      </div>
    </div>
  </div>

  <div class="mentor-card mentor-orange">
    <h3>🏫 NSF-DoD RET Site Mentor</h3>
    <div class="mentor-subtitle">Research Experiences for Teachers</div>

    <div class="mentor-list">
      <div class="mentor-item">
        <div class="mentor-icon">⭐</div>
        <div>
          <div class="mentor-name">Marisa Behar</div>
        </div>
      </div>

      <div class="mentor-item">
        <div class="mentor-icon">⭐</div>
        <div>
          <div class="mentor-name">Yoandra Abad</div>
        </div>
      </div>
    </div>
  </div>
</div>

<hr class="mentor-divider">

## <span class="mentor-section-title community">Recognition and Community Projects</span>

<div class="mentor-grid">
  <div class="mentor-card mentor-pink">
    <h3>📰 Recognition and Broader Mentoring Engagement</h3>
    <div class="mentor-subtitle">Community-connected and collaborative mentoring efforts</div>

    <div class="mentor-list">
      <div class="mentor-item">
        <div class="mentor-icon">📰</div>
        <div>
          <div class="mentor-name">Featured in FIU CEC News and KFSCIS News</div>
          <div class="mentor-topic"><a href="#">View coverage</a></div>
        </div>
      </div>

      <div class="mentor-item">
        <div class="mentor-icon">🤝</div>
        <div>
          <div class="mentor-name">Mentor of FIU Thrive ML Team</div>
          <div class="mentor-topic">Part of the Green Family Foundation Neighborhood Health Education Learning Program (NeighborhoodHELP)</div>
        </div>
      </div>

      <div class="mentor-item">
        <div class="mentor-icon">💡</div>
        <div>
          <div class="mentor-name">Collaborative AI-Driven Health Research Project</div>
          <div class="mentor-topic">Funded by the Florida Department of Health in Miami-Dade</div>
        </div>
      </div>
    </div>

    <div class="mentor-badges">
      <span class="mentor-badge">Student Development</span>
      <span class="mentor-badge">Research Leadership</span>
      <span class="mentor-badge">Community Engagement</span>
      <span class="mentor-badge">Collaborative Mentoring</span>
    </div>
  </div>
</div>
