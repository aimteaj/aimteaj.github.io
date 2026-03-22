 ---
layout: page
title: project 1
description: with background image
img: assets/img/12.jpg
importance: 1
category: work
related_publications: true
---

<style>
  .proj-detail-page {
    position: relative;
  }

  .proj-detail-hero {
    position: relative;
    overflow: hidden;
    padding: 2.8rem 2rem;
    border-radius: 26px;
    margin-bottom: 2rem;
    color: white;
    background: linear-gradient(-45deg, #0f172a, #1d4ed8, #7c3aed, #14b8a6);
    background-size: 400% 400%;
    animation: pdGradient 14s ease infinite;
    box-shadow: 0 20px 44px rgba(15, 23, 42, 0.18);
  }

  .proj-detail-hero::before,
  .proj-detail-hero::after {
    content: "";
    position: absolute;
    border-radius: 50%;
    filter: blur(44px);
    opacity: 0.24;
    pointer-events: none;
  }

  .proj-detail-hero::before {
    width: 240px;
    height: 240px;
    background: rgba(255,255,255,0.18);
    top: -75px;
    right: -35px;
    animation: pdFloat 10s ease-in-out infinite;
  }

  .proj-detail-hero::after {
    width: 180px;
    height: 180px;
    background: rgba(255,255,255,0.13);
    bottom: -45px;
    left: -25px;
    animation: pdFloat 12s ease-in-out infinite reverse;
  }

  .proj-detail-hero h1 {
    margin: 0 0 0.7rem 0;
    font-size: 2.5rem;
    color: white;
  }

  .proj-detail-hero p {
    max-width: 860px;
    margin: 0;
    font-size: 1.05rem;
    line-height: 1.85;
    color: rgba(255,255,255,0.95);
  }

  .proj-detail-shell {
    position: relative;
    padding: 1.35rem;
    border-radius: 24px;
    background: linear-gradient(180deg, rgba(248,250,252,0.95), rgba(241,245,249,0.88));
    border: 1px solid rgba(226,232,240,0.8);
    box-shadow: 0 14px 34px rgba(15, 23, 42, 0.06);
    backdrop-filter: blur(8px);
  }

  .proj-detail-shell::before {
    content: "";
    position: absolute;
    inset: 0;
    border-radius: 24px;
    pointer-events: none;
    background: linear-gradient(135deg, rgba(255,255,255,0.18), rgba(255,255,255,0.03));
  }

  .proj-intro-card,
  .proj-section-card,
  .proj-code-card {
    position: relative;
    overflow: hidden;
    padding: 1.35rem 1.35rem 1.2rem 1.35rem;
    margin-bottom: 1.3rem;
    border-radius: 20px;
    background: rgba(255,255,255,0.9);
    border: 1px solid rgba(255,255,255,0.55);
    box-shadow: 0 10px 28px rgba(15, 23, 42, 0.07);
    animation: pdFadeUp 0.85s ease both;
  }

  .proj-intro-card {
    background: linear-gradient(180deg, #f8fbff, #eef6ff);
    border-left: 6px solid #2563eb;
  }

  .proj-section-card {
    background: linear-gradient(180deg, #fcfaff, #f5f0ff);
    border-left: 6px solid #7c3aed;
  }

  .proj-code-card {
    background: linear-gradient(180deg, #f6fffb, #ecfff6);
    border-left: 6px solid #059669;
  }

  .proj-intro-card::before,
  .proj-section-card::before,
  .proj-code-card::before {
    content: "";
    position: absolute;
    inset: 0;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.35s ease;
    background: linear-gradient(135deg, rgba(255,255,255,0.20), rgba(255,255,255,0.03));
  }

  .proj-intro-card:hover::before,
  .proj-section-card:hover::before,
  .proj-code-card:hover::before {
    opacity: 1;
  }

  .proj-block-title {
    display: inline-flex;
    align-items: center;
    gap: 0.55rem;
    margin: 0 0 0.7rem 0;
    padding: 0.6rem 0.95rem;
    border-radius: 999px;
    font-size: 1.02rem;
    font-weight: 800;
    color: #0f172a;
    background: linear-gradient(90deg, rgba(37,99,235,0.12), rgba(124,58,237,0.10));
    border: 1px solid rgba(37,99,235,0.10);
    box-shadow: 0 8px 18px rgba(15, 23, 42, 0.05);
  }

  .proj-detail-shell p {
    color: #334155;
    line-height: 1.85;
    font-size: 0.98rem;
  }

  .proj-detail-shell strong {
    color: #0f172a;
  }

  .proj-highlight {
    display: inline-block;
    margin-top: 0.7rem;
    padding: 0.78rem 1rem;
    border-radius: 16px;
    background: linear-gradient(90deg, rgba(37,99,235,0.10), rgba(20,184,166,0.10));
    border: 1px solid rgba(37,99,235,0.12);
    color: #0f172a;
    font-weight: 650;
  }

  .proj-gallery {
    margin-top: 1rem;
    margin-bottom: 0.35rem;
  }

  .proj-gallery .col-sm,
  .proj-gallery .col-sm-4,
  .proj-gallery .col-sm-8 {
    transition: transform 0.35s ease;
  }

  .proj-gallery .col-sm:hover,
  .proj-gallery .col-sm-4:hover,
  .proj-gallery .col-sm-8:hover {
    transform: translateY(-6px);
  }

  .proj-gallery img,
  .proj-gallery .img-fluid {
    border-radius: 18px !important;
    box-shadow: 0 12px 26px rgba(15, 23, 42, 0.10) !important;
    transition: transform 0.35s ease, box-shadow 0.35s ease, filter 0.35s ease;
  }

  .proj-gallery img:hover,
  .proj-gallery .img-fluid:hover {
    transform: scale(1.02);
    box-shadow: 0 18px 36px rgba(15, 23, 42, 0.16) !important;
    filter: brightness(1.02);
  }

  .proj-caption {
    margin: 0.85rem 0 1.45rem 0;
    padding: 0.95rem 1rem;
    border-radius: 16px;
    font-size: 0.94rem;
    line-height: 1.75;
    color: #475569;
    background: linear-gradient(90deg, rgba(255,255,255,0.78), rgba(248,250,252,0.92));
    border: 1px solid rgba(148,163,184,0.14);
    box-shadow: 0 8px 18px rgba(15, 23, 42, 0.04);
    animation: pdFadeUp 0.95s ease both;
  }

  .proj-code-card pre {
    border-radius: 18px !important;
    padding: 1rem 1.1rem !important;
    background: #0f172a !important;
    box-shadow: 0 12px 24px rgba(15, 23, 42, 0.12);
  }

  .proj-code-card code {
    font-size: 0.92rem;
  }

  .proj-inline-code {
    display: block;
    margin-top: 0.85rem;
    padding: 0.9rem 1rem;
    border-radius: 16px;
    background: rgba(15,23,42,0.95);
    color: #e2e8f0;
    font-family: monospace;
    overflow-x: auto;
    line-height: 1.7;
  }

  .proj-divider {
    height: 1px;
    border: none;
    margin: 1.7rem 0 1.3rem 0;
    background: linear-gradient(to right, transparent, rgba(148,163,184,0.45), transparent);
  }

  @keyframes pdGradient {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
  }

  @keyframes pdFloat {
    0% { transform: translateY(0px) translateX(0px); }
    50% { transform: translateY(18px) translateX(8px); }
    100% { transform: translateY(0px) translateX(0px); }
  }

  @keyframes pdFadeUp {
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
    .proj-detail-hero,
    .proj-detail-hero::before,
    .proj-detail-hero::after,
    .proj-intro-card,
    .proj-section-card,
    .proj-code-card,
    .proj-caption {
      animation: none !important;
    }

    .proj-gallery .col-sm,
    .proj-gallery .col-sm-4,
    .proj-gallery .col-sm-8,
    .proj-gallery img,
    .proj-gallery .img-fluid {
      transition: none !important;
    }
  }
</style>

<div class="proj-detail-page">
  <div class="proj-detail-hero">
    <h1>Project 1</h1>
    <p>
      A visually rich project showcase page designed to present featured work with polished layouts, elegant image arrangements, and clean technical documentation. This format is ideal for highlighting research prototypes, design explorations, and portfolio-ready project narratives.
    </p>
  </div>

  <div class="proj-detail-shell">

    <div class="proj-intro-card">
      <div class="proj-block-title">🌟 Project Overview</div>
      <p>
        Every project can have a refined showcase page with strong visual presentation and flexible content layout. This example demonstrates how to combine introductory text, image galleries, descriptive captions, and code snippets into a single polished project page.
      </p>
      <p>
        Images can be displayed in elegant <strong>three-column</strong>, <strong>two-column</strong>, or <strong>full-width</strong> arrangements, making it easy to present project outcomes in a visually engaging way.
      </p>
      <div class="proj-highlight">
        Use the <strong>img</strong> field in the front matter to assign a background image for the project card in the portfolio page.
      </div>
    </div>

    <div class="proj-section-card">
      <div class="proj-block-title">🖼️ Background Image Setup</div>
      <p>
        To display a background image for the project on the portfolio page, include the image path directly in the front matter:
      </p>

      <div class="proj-inline-code">
layout: page<br>
title: project<br>
description: a project with a background image<br>
img: /assets/img/12.jpg
      </div>
    </div>

    <hr class="proj-divider">

    <div class="proj-section-card">
      <div class="proj-block-title">📸 Three-Column Gallery</div>
      <p>
        A balanced three-column image layout works well for feature highlights, visual comparisons, or showcasing multiple outputs side by side.
      </p>

      <div class="row proj-gallery">
        <div class="col-sm mt-3 mt-md-0">
          {% include figure.liquid loading="eager" path="assets/img/1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
          {% include figure.liquid loading="eager" path="assets/img/3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-3 mt-md-0">
          {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
      </div>

      <div class="proj-caption">
        Caption photos elegantly. On the left, a road passes through a tunnel. In the middle, leaves drift through a stylized scene. On the right, another nature-focused composition highlights texture and atmosphere.
      </div>
    </div>

    <div class="proj-section-card">
      <div class="proj-block-title">🖼️ Full-Width Showcase</div>
      <p>
        A full-width image can be used when a single visual deserves stronger emphasis or when you want a more immersive presentation.
      </p>

      <div class="row proj-gallery">
        <div class="col-sm mt-3 mt-md-0">
          {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
      </div>

      <div class="proj-caption">
        This layout is especially useful for hero visuals, final results, or screenshots that benefit from a wider presentation.
      </div>
    </div>

    <div class="proj-section-card">
      <div class="proj-block-title">✍️ Narrative Between Visuals</div>
      <p>
        You can place regular narrative text between image rows to explain the motivation, process, or significance of the project. This creates a more complete and engaging project story rather than showing visuals alone.
      </p>
      <p>
        For example, you may want to describe the problem setting, summarize the design process, or discuss implementation details before presenting the next visual results. Citations can also be integrated naturally within the text, such as {% cite einstein1950meaning %}.
      </p>
    </div>

    <div class="proj-section-card">
      <div class="proj-block-title">🧩 Two-Thirds and One-Third Layout</div>
      <p>
        A mixed layout can create a more dynamic composition by combining a larger primary visual with a smaller supporting image.
      </p>

      <div class="row justify-content-sm-center proj-gallery">
        <div class="col-sm-8 mt-3 mt-md-0">
          {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm-4 mt-3 mt-md-0">
          {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
        </div>
      </div>

      <div class="proj-caption">
        This 2/3 plus 1/3 configuration is ideal for pairing a dominant result with a complementary detail view.
      </div>
    </div>

    <hr class="proj-divider">

    <div class="proj-code-card">
      <div class="proj-block-title">💻 Implementation Example</div>
      <p>
        The layout is simple to implement. Wrap each image inside a Bootstrap column and place those columns inside a row container. Responsive behavior comes from the grid system, while classes such as <strong>img-fluid</strong>, <strong>rounded</strong>, and <strong>z-depth-1</strong> improve visual presentation.
      </p>
      <p>
        Here is the code for the final mixed-width image row:
      </p>

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
