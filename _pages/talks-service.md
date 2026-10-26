---
layout: page
title: Talks and Service
permalink: /talks-service/
nav: true
nav_order: 7
description: ""
---

{% assign d = site.data.talks_service %}
{% assign n_review = d.conferences.size | plus: d.journals.size %}
{% assign n_talks = d.talks.size | plus: d.lab_presentations.size %}

<div class="ts">

  <div class="ts-tabs" role="group" aria-label="Filter by activity">
    <button class="ts-tab is-on" data-f="all" aria-pressed="true"><span class="ts-n">All</span><span class="ts-l">activities</span></button>
    <button class="ts-tab" data-f="lead" aria-pressed="false"><span class="ts-n">{{ d.leadership.size }}</span><span class="ts-l">Leadership roles</span></button>
    <button class="ts-tab" data-f="talks" aria-pressed="false"><span class="ts-n">{{ n_talks }}</span><span class="ts-l">Talks and presentations</span></button>
    <button class="ts-tab" data-f="review" aria-pressed="false"><span class="ts-n">{{ n_review }}</span><span class="ts-l">Conferences and journals reviewed</span></button>
    <button class="ts-tab" data-f="panels" aria-pressed="false"><span class="ts-n">{{ d.panels.size }}</span><span class="ts-l">Proposal review panels</span></button>
    <button class="ts-tab" data-f="media" aria-pressed="false"><span class="ts-n">{{ d.media.size }}</span><span class="ts-l">Media coverage</span></button>
  </div>

  <section class="ts-sec" data-g="lead">
    <h2 class="ts-h2">Conference leadership and editorial roles</h2>
    {% for x in d.leadership %}
    <div class="ts-row">
      <div class="ts-when">{{ x.year }}</div>
      <div>
        <div class="ts-role">{{ x.role }}</div>
        <div class="ts-what">{{ x.venue }}</div>
        {% if x.detail %}<div class="ts-detail">{{ x.detail }}</div>{% endif %}
      </div>
    </div>
    {% endfor %}
  </section>

  <section class="ts-sec" data-g="talks">
    <h2 class="ts-h2">Talks and presentations</h2>
    {% for x in d.talks %}
    <div class="ts-row">
      <div class="ts-when">{{ x.date }}</div>
      <div>
        <span class="ts-kind">{{ x.kind }}</span>
        <div class="ts-role ts-title">{% if x.link %}<a href="{{ x.link }}" target="_blank" rel="noopener">{{ x.title }}</a>{% else %}{{ x.title }}{% endif %}</div>
        <div class="ts-what">{{ x.venue }}</div>
      </div>
    </div>
    {% endfor %}

    <details class="ts-more">
      <summary>Papers presented by the SPEED Lab at conferences ({{ d.lab_presentations.size }})</summary>
      <ul class="ts-mini">
        {% for x in d.lab_presentations %}
        <li><span class="ts-mini-when">{{ x.date }}</span><span><strong>{{ x.venue }}</strong>: {{ x.what }}</span></li>
        {% endfor %}
      </ul>
    </details>
  </section>

  <section class="ts-sec" data-g="review">
    <h2 class="ts-h2">Peer review</h2>
    <p class="ts-lead">Reviewer or program committee member for more than 20 international conferences and more than 15 journals, including:</p>
    <h3 class="ts-h3">Conferences</h3>
    <div class="ts-chips">
      {% for c in d.conferences %}
      <span class="ts-chip{% if c.year %} is-current{% endif %}"><b>{{ c.name }}</b>{% if c.year %} <span class="ts-chip-y">{{ c.year }}</span>{% endif %}{% if c.note %}<span class="ts-chip-note">{{ c.note }}</span>{% endif %}</span>
      {% endfor %}
    </div>
    <h3 class="ts-h3">Journals</h3>
    <ul class="ts-journals">
      {% for j in d.journals %}<li>{{ j }}</li>{% endfor %}
    </ul>
  </section>

  <section class="ts-sec" data-g="panels">
    <h2 class="ts-h2">Proposal review panels</h2>
    <div class="ts-panels">
      {% for x in d.panels %}
      <div class="ts-panel">
        <div class="ts-panel-org">{{ x.org }}</div>
        <div class="ts-panel-what">{{ x.what }}</div>
        {% if x.year %}<div class="ts-panel-y">{{ x.year }}</div>{% endif %}
      </div>
      {% endfor %}
    </div>
  </section>

  <section class="ts-sec" data-g="media">
    <h2 class="ts-h2">In the news</h2>
    {% for x in d.media %}
    <a class="ts-row ts-news" href="{{ x.link }}" target="_blank" rel="noopener">
      <div class="ts-when">{{ x.year }}</div>
      <div>
        <div class="ts-outlet">{{ x.outlet }}</div>
        <div class="ts-role ts-title">{{ x.title }}</div>
      </div>
    </a>
    {% endfor %}
  </section>

  <section class="ts-sec" data-g="inst">
    <h2 class="ts-h2">University service</h2>
    {% for x in d.institutional %}
    <div class="ts-row ts-row--inst">
      <div class="ts-role">{{ x.role }}</div>
      <div class="ts-what">{% if x.link %}<a href="{{ x.link }}" target="_blank" rel="noopener">{{ x.unit }}</a>{% else %}{{ x.unit }}{% endif %}</div>
    </div>
    {% endfor %}
  </section>
</div>

<style>
.ts [hidden] { display: none !important; }
.ts { max-width: 980px; margin: 0 auto; }
.ts a { text-decoration: none; }

.ts-tabs { display: grid; grid-template-columns: repeat(6, minmax(0, 1fr)); border-top: 2px solid var(--global-text-color); border-bottom: 1px solid var(--global-divider-color); }
.ts-tab { all: unset; cursor: pointer; padding: 1rem 0.8rem 0.9rem; display: flex; flex-direction: column; gap: 0.2rem; border-right: 1px solid var(--global-divider-color); position: relative; }
.ts-tab:last-child { border-right: 0; }
.ts-n { font-size: 1.9rem; font-weight: 700; line-height: 1.1; color: var(--global-text-color); font-variant-numeric: tabular-nums; }
.ts-l { font-size: 0.82rem; color: var(--global-text-color-light); font-weight: 600; line-height: 1.3; }
.ts-tab:hover .ts-n { color: var(--global-theme-color); }
.ts-tab.is-on::after { content: ""; position: absolute; left: 0; right: 0; bottom: -1px; height: 3px; background: var(--global-theme-color); }
.ts-tab.is-on .ts-n, .ts-tab.is-on .ts-l { color: var(--global-theme-color); }
.ts-tab:focus-visible, .ts-more summary:focus-visible, .ts-news:focus-visible { outline: 2px solid var(--global-theme-color); outline-offset: 2px; }

.ts-sec { padding-top: 2.2rem; }
.ts-h2 { font-size: 1.35rem; font-weight: 700; margin: 0 0 0.3rem; padding-bottom: 0.7rem; border-bottom: 1px solid var(--global-text-color); }
.ts-h3 { font-size: 1rem; font-weight: 700; margin: 1.3rem 0 0.7rem; color: var(--global-text-color); }
.ts-lead { margin: 0.9rem 0 0; color: var(--global-text-color-light); }

.ts-row { display: grid; grid-template-columns: 130px minmax(0, 1fr); gap: 1.5rem; padding: 1rem 0; border-bottom: 1px solid var(--global-divider-color); color: var(--global-text-color); }
.ts-when { font-weight: 700; color: var(--global-theme-color); font-variant-numeric: tabular-nums; padding-top: 0.1rem; }
.ts-role { font-weight: 700; color: var(--global-text-color); line-height: 1.45; }
.ts-title a { color: var(--global-text-color); }
.ts-title a:hover, .ts-news:hover .ts-title { color: var(--global-theme-color); }
.ts-what { color: var(--global-text-color); line-height: 1.5; margin-top: 0.15rem; }
.ts-what a { color: var(--global-theme-color); font-weight: 600; }
.ts-detail { color: var(--global-text-color-light); font-size: 0.92rem; line-height: 1.5; margin-top: 0.25rem; }
.ts-kind { display: inline-block; font-size: 0.74rem; font-weight: 700; color: var(--global-theme-color); border: 1px solid var(--global-theme-color); border-radius: 4px; padding: 0.05rem 0.45rem; margin-bottom: 0.35rem; }
.ts-outlet { font-size: 0.85rem; font-weight: 700; color: var(--global-text-color-light); margin-bottom: 0.15rem; }
.ts-news .ts-title::after { content: " ↗"; color: var(--global-text-color-light); font-weight: 400; }
.ts-row--inst { grid-template-columns: 260px minmax(0, 1fr); }

.ts-more { margin-top: 1rem; }
.ts-more summary { cursor: pointer; font-weight: 600; color: var(--global-theme-color); list-style: none; display: inline-flex; align-items: center; gap: 0.45rem; }
.ts-more summary::-webkit-details-marker { display: none; }
.ts-more summary::before { content: ""; width: 0.45rem; height: 0.45rem; border-right: 2px solid currentColor; border-bottom: 2px solid currentColor; transform: rotate(-45deg); transition: transform 0.2s ease; }
.ts-more[open] summary::before { transform: rotate(45deg); }
.ts-mini { list-style: none; padding: 0; margin: 0.8rem 0 0; }
.ts-mini li { display: grid; grid-template-columns: 130px minmax(0, 1fr); gap: 1.5rem; padding: 0.55rem 0; border-bottom: 1px dashed var(--global-divider-color); font-size: 0.93rem; color: var(--global-text-color); }
.ts-mini-when { color: var(--global-text-color-light); font-weight: 600; }

.ts-chips { display: flex; flex-wrap: wrap; gap: 0.5rem; }
.ts-chip { display: inline-flex; align-items: baseline; gap: 0.35rem; padding: 0.4rem 0.8rem; border: 1px solid var(--global-divider-color); border-radius: 8px; color: var(--global-text-color); font-size: 0.95rem; }
.ts-chip.is-current { border-color: var(--global-theme-color); }
.ts-chip-y { font-size: 0.8rem; font-weight: 700; color: var(--global-theme-color); font-variant-numeric: tabular-nums; }
.ts-chip-note { font-size: 0.75rem; color: var(--global-text-color-light); }
.ts-journals { columns: 2; column-gap: 2rem; padding-left: 1.1rem; margin: 0; color: var(--global-text-color); }
.ts-journals li { margin: 0 0 0.4rem; break-inside: avoid; }

.ts-panels { display: grid; grid-template-columns: repeat(3, minmax(0, 1fr)); gap: 0.9rem; margin-top: 1rem; }
.ts-panel { border: 1px solid var(--global-divider-color); border-radius: 8px; padding: 0.9rem 1rem; background: var(--global-card-bg-color); position: relative; }
.ts-panel-org { font-weight: 700; color: var(--global-text-color); }
.ts-panel-what { color: var(--global-text-color); font-size: 0.93rem; margin-top: 0.25rem; line-height: 1.45; }
.ts-panel-y { position: absolute; top: 0.9rem; right: 1rem; font-size: 0.8rem; font-weight: 700; color: var(--global-theme-color); }
.ts-panel-org { padding-right: 2.6rem; }

@media (max-width: 760px) {
  .ts-tabs { grid-template-columns: repeat(3, minmax(0, 1fr)); }
  .ts-tab:nth-child(3n) { border-right: 0; }
  .ts-tab:nth-child(-n+3) { border-bottom: 1px solid var(--global-divider-color); }
  .ts-n { font-size: 1.45rem; }
  .ts-row, .ts-row--inst, .ts-mini li { grid-template-columns: 1fr; gap: 0.25rem; }
  .ts-journals { columns: 1; }
  .ts-panels { grid-template-columns: 1fr; }
}
@media (prefers-reduced-motion: reduce) { .ts-more summary::before { transition: none; } }
</style>

<script>
(function () {
  var root = document.querySelector('.ts'); if (!root) return;
  var tabs = root.querySelectorAll('.ts-tab'), secs = root.querySelectorAll('.ts-sec');
  function pick(f) {
    tabs.forEach(function (t) { var on = t.dataset.f === f; t.classList.toggle('is-on', on); t.setAttribute('aria-pressed', on); });
    secs.forEach(function (s) { s.hidden = !(f === 'all' || s.dataset.g === f); });
    try { history.replaceState(null, '', f === 'all' ? location.pathname : '#' + f); } catch (e) {}
  }
  tabs.forEach(function (t) { t.addEventListener('click', function () { pick(t.dataset.f); }); });
  var h = location.hash.slice(1);
  if (h && root.querySelector('.ts-tab[data-f="' + h + '"]')) pick(h);
})();
</script>
