---
layout: page
title: Teaching
permalink: /teaching/
nav: true
nav_order: 5
description: ""
---

{% assign t = site.data.teaching %}

<div class="tc">

  <div class="tc-courses" role="group" aria-label="Highlight terms by course">
    {% for c in t.courses %}
      {% assign key = c[0] %}{% assign n = 0 %}
      {% for term in t.terms %}{% if term.courses contains key %}{% assign n = n | plus: 1 %}{% endif %}{% endfor %}
      <button class="tc-course" data-c="{{ key }}" aria-pressed="false">
        <span class="tc-cname">{{ c[1] }}</span>
        <span class="tc-ccount">{% if n == 1 %}1 term{% else %}{{ n }} terms{% endif %}</span>
      </button>
    {% endfor %}
  </div>
  <p class="tc-hint" aria-live="polite">Select a course to highlight the terms it was taught.</p>

  {% for s in t.schools %}
  {% assign sk = s[0] %}
  <section class="tc-school">
    <h2 class="tc-h2">{{ s[1] }}{% if sk == "fau" %}<span class="tc-now">Current</span>{% endif %}</h2>
    <ol class="tc-timeline">
      {% for term in t.terms %}{% if term.school == sk %}
      <li class="tc-term" data-c="{{ term.courses | join: ' ' }}">
        <div class="tc-when">{{ term.term }}</div>
        <div class="tc-what">
          {% for k in term.courses %}<span class="tc-pill" data-c="{{ k }}">{{ t.courses[k] }}</span>{% endfor %}
          {% if term.note %}<div class="tc-note">{{ term.note }}</div>{% endif %}
        </div>
      </li>
      {% endif %}{% endfor %}
    </ol>
  </section>
  {% endfor %}

  <section class="tc-school">
    <h2 class="tc-h2">Courses developed</h2>
    <ul class="tc-dev">
      {% for d in t.developed %}
      <li><span class="tc-devtitle">{{ d.title }}</span><span class="tc-devdetail">{{ d.detail }}</span></li>
      {% endfor %}
    </ul>
  </section>

  <section class="tc-school">
    <h2 class="tc-h2">Teaching recognition</h2>
    <div class="tc-award">
      <div class="tc-awardyear">2024</div>
      <div>
        <div class="tc-devtitle">Outstanding Teacher of the Year Award</div>
        <p>School of Computing, Southern Illinois University Carbondale. For dedication to teaching excellence, student mentorship and curriculum innovation, including the development of modern AI-focused coursework.</p>
      </div>
    </div>
  </section>

</div>

<style>
.tc [hidden] { display: none !important; }
.tc { max-width: 980px; margin: 0 auto; }

.tc-courses { display: grid; grid-template-columns: repeat(5, minmax(0, 1fr)); border-top: 2px solid var(--global-text-color); border-bottom: 1px solid var(--global-divider-color); }
.tc-course { all: unset; cursor: pointer; padding: 1rem 0.85rem 0.9rem; border-right: 1px solid var(--global-divider-color); display: flex; flex-direction: column; gap: 0.3rem; position: relative; }
.tc-course:last-child { border-right: 0; }
.tc-cname { font-weight: 700; font-size: 0.98rem; line-height: 1.3; color: var(--global-text-color); }
.tc-ccount { font-size: 0.85rem; color: var(--global-text-color-light); font-variant-numeric: tabular-nums; }
.tc-course:hover .tc-cname { color: var(--global-theme-color); }
.tc-course[aria-pressed="true"]::after { content: ""; position: absolute; left: 0; right: 0; bottom: -1px; height: 3px; background: var(--global-theme-color); }
.tc-course[aria-pressed="true"] .tc-cname, .tc-course[aria-pressed="true"] .tc-ccount { color: var(--global-theme-color); }
.tc-course:focus-visible { outline: 2px solid var(--global-theme-color); outline-offset: -2px; }
.tc-hint { font-size: 0.88rem; color: var(--global-text-color-light); margin: 0.7rem 0 0; min-height: 1.4em; }

.tc-school { padding-top: 2rem; }
.tc-h2 { font-size: 1.35rem; font-weight: 700; margin: 0 0 0.3rem; padding-bottom: 0.7rem; border-bottom: 1px solid var(--global-text-color); display: flex; align-items: baseline; gap: 0.8rem; }
.tc-now { font-size: 0.78rem; font-weight: 700; color: var(--global-theme-color); border: 1px solid var(--global-theme-color); border-radius: 4px; padding: 0.1rem 0.5rem; }

.tc-timeline { list-style: none; margin: 0; padding: 0; position: relative; }
.tc-timeline::before { content: ""; position: absolute; left: 140px; top: 0; bottom: 0; width: 1px; background: var(--global-divider-color); }
.tc-term { display: grid; grid-template-columns: 140px minmax(0, 1fr); gap: 1.6rem; padding: 0.95rem 0; position: relative; transition: opacity 0.2s ease; }
.tc-term::before { content: ""; position: absolute; left: 136px; top: 1.35rem; width: 9px; height: 9px; border-radius: 50%; background: var(--global-bg-color); border: 2px solid var(--global-text-color-light); transition: background 0.2s ease, border-color 0.2s ease; }
.tc-when { font-weight: 700; font-variant-numeric: tabular-nums; color: var(--global-text-color); padding-top: 0.15rem; }
.tc-what { display: flex; flex-wrap: wrap; gap: 0.45rem; align-items: center; padding-left: 0.4rem; }
.tc-pill { font-size: 0.92rem; padding: 0.25rem 0.75rem; border: 1px solid var(--global-divider-color); border-radius: 6px; color: var(--global-text-color); transition: background 0.2s ease, color 0.2s ease, border-color 0.2s ease; }
.tc-note { flex-basis: 100%; font-size: 0.85rem; color: var(--global-text-color-light); }

/* highlight state */
.tc.is-filtering .tc-term { opacity: 0.35; }
.tc.is-filtering .tc-term.is-hit { opacity: 1; }
.tc.is-filtering .tc-term.is-hit::before { background: var(--global-theme-color); border-color: var(--global-theme-color); }
.tc-pill.is-hit { background: var(--global-theme-color); border-color: var(--global-theme-color); color: #fff; }

.tc-dev { list-style: none; margin: 0; padding: 0; }
.tc-dev li { display: grid; grid-template-columns: minmax(0, 1fr) minmax(0, 1fr); gap: 1.5rem; padding: 0.95rem 0; border-bottom: 1px solid var(--global-divider-color); }
.tc-devtitle { font-weight: 700; color: var(--global-text-color); }
.tc-devdetail { color: var(--global-text-color-light); font-size: 0.93rem; line-height: 1.5; }

.tc-award { display: grid; grid-template-columns: 140px minmax(0, 1fr); gap: 1.6rem; padding: 1.1rem 0; }
.tc-awardyear { font-size: 1.6rem; font-weight: 700; color: var(--global-theme-color); line-height: 1.1; }
.tc-award p { margin: 0.35rem 0 0; line-height: 1.65; max-width: 68ch; color: var(--global-text-color); }

@media (max-width: 760px) {
  .tc-courses { grid-template-columns: repeat(2, minmax(0, 1fr)); }
  .tc-course { border-bottom: 1px solid var(--global-divider-color); }
  .tc-course:nth-child(2n) { border-right: 0; }
  .tc-timeline::before { left: 4px; }
  .tc-term { grid-template-columns: 1fr; gap: 0.4rem; padding-left: 1.5rem; }
  .tc-term::before { left: 0; }
  .tc-what { padding-left: 0; }
  .tc-dev li { grid-template-columns: 1fr; gap: 0.2rem; }
  .tc-award { grid-template-columns: 1fr; gap: 0.3rem; }
}
@media (prefers-reduced-motion: reduce) { .tc-term, .tc-term::before, .tc-pill { transition: none; } }
</style>

<script>
(function () {
  var root = document.querySelector('.tc'); if (!root) return;
  var btns = root.querySelectorAll('.tc-course'), hint = root.querySelector('.tc-hint');
  var defaultHint = hint.textContent;
  btns.forEach(function (b) {
    b.addEventListener('click', function () {
      var on = b.getAttribute('aria-pressed') !== 'true', key = b.dataset.c;
      btns.forEach(function (x) { x.setAttribute('aria-pressed', x === b && on ? 'true' : 'false'); });
      root.classList.toggle('is-filtering', on);
      root.querySelectorAll('.tc-term').forEach(function (term) {
        term.classList.toggle('is-hit', on && term.dataset.c.split(' ').indexOf(key) > -1);
      });
      root.querySelectorAll('.tc-pill').forEach(function (p) { p.classList.toggle('is-hit', on && p.dataset.c === key); });
      hint.textContent = on ? b.querySelector('.tc-cname').textContent + ': taught in ' + b.querySelector('.tc-ccount').textContent + '. Select it again to clear.' : defaultHint;
    });
  });
})();
</script>
