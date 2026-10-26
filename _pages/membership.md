---
layout: page
title: Mentorship
permalink: /mentorship/
nav: true
nav_order: 6
description: ""
---

{% assign m = site.data.mentorship %}
{% assign sd_students = 0 %}{% for p in m.senior_design %}{% assign sd_students = sd_students | plus: p.students.size %}{% endfor %}
{% assign n_honors = 0 %}{% for p in m.phd %}{% if p.honors %}{% assign n_honors = n_honors | plus: p.honors.size %}{% endif %}{% endfor %}
{% assign prog_people = 0 %}{% for p in m.programs %}{% if p.people %}{% assign prog_people = prog_people | plus: p.people.size %}{% endif %}{% endfor %}

<div class="mt">

  <div class="mt-tabs" role="tablist" aria-label="Filter mentees by group">
    <button class="mt-tab is-on" role="tab" aria-selected="true" data-f="all"><span class="mt-n">All</span><span class="mt-l">groups</span></button>
    <button class="mt-tab" role="tab" aria-selected="false" data-f="phd"><span class="mt-n">{{ m.phd.size }}</span><span class="mt-l">Ph.D.</span></button>
    <button class="mt-tab" role="tab" aria-selected="false" data-f="senior"><span class="mt-n">{{ sd_students }}</span><span class="mt-l">Senior Design</span></button>
    <button class="mt-tab" role="tab" aria-selected="false" data-f="ms"><span class="mt-n">{{ m.masters.size }}</span><span class="mt-l">Master's</span></button>
    <button class="mt-tab" role="tab" aria-selected="false" data-f="ug"><span class="mt-n">{{ m.undergrad.size }}</span><span class="mt-l">Undergraduate</span></button>
    <button class="mt-tab" role="tab" aria-selected="false" data-f="honors"><span class="mt-n">{{ n_honors }}</span><span class="mt-l">Student honors</span></button>
    <button class="mt-tab" role="tab" aria-selected="false" data-f="prog"><span class="mt-n">{{ prog_people }}</span><span class="mt-l">REU / RET</span></button>
  </div>

  <div class="mt-search">
    <label for="mt-q" class="mt-sr">Search mentees and topics</label>
    <input id="mt-q" type="search" placeholder="Search by name or topic" autocomplete="off">
    <span class="mt-count" aria-live="polite"></span>
  </div>

  <section class="mt-sec" data-g="phd">
    <h2 class="mt-h2">Doctoral advising</h2>
    <div class="mt-people">
      {% for p in m.phd %}
      <div class="mt-person mt-item">
        <div class="mt-avatar" aria-hidden="true">{{ p.name | slice: 0 }}</div>
        <div>
          <div class="mt-name">{{ p.name }}</div>
          <div class="mt-sub">{{ p.role }}</div>
          <div class="mt-sub2">{{ p.place }}</div>
          {% if p.honors %}<a class="mt-hbadge" href="#honors-{{ forloop.index }}">{{ p.honors.size }} honors and awards</a>{% endif %}
        </div>
      </div>
      {% endfor %}
    </div>
  </section>

  <section class="mt-sec" data-g="honors">
    <h2 class="mt-h2">Student honors and awards</h2>
    {% for p in m.phd %}{% if p.honors %}
    {% assign hs = p.honors | sort: "year" | reverse %}
    <details class="mt-honors mt-item" id="honors-{{ forloop.index }}" open>
      <summary><span class="mt-name">{{ p.name }}</span><span class="mt-hcount">{{ p.honors.size }} honors</span></summary>
      <ol class="mt-hlist">
        {% for h in hs %}{% if h.kind != "Leadership" %}
        <li><span class="mt-hy">{{ h.year }}</span><div><span class="mt-hk">{{ h.kind }}</span><div class="mt-ht">{{ h.title }}</div><div class="mt-hd">{{ h.detail }}</div></div></li>
        {% endif %}{% endfor %}
        {% for h in hs %}{% if h.kind == "Leadership" %}
        <li><span class="mt-hy">{{ h.year }}</span><div><span class="mt-hk mt-hk--lead">{{ h.kind }}</span><div class="mt-ht">{{ h.title }}</div><div class="mt-hd">{{ h.detail }}</div></div></li>
        {% endif %}{% endfor %}
      </ol>
    </details>
    {% endif %}{% endfor %}
  </section>

  <section class="mt-sec" data-g="senior">
    <h2 class="mt-h2">Senior Design projects</h2>
    {% for p in m.senior_design %}
    <article class="mt-project mt-item">
      <div class="mt-pmeta">
        <div class="mt-pprog">Senior Design</div>
        <div class="mt-sub2">{{ p.period }}</div>
        <div class="mt-sub2">Florida Atlantic University</div>
      </div>
      <div class="mt-pbody">
        {% if p.award %}<div class="mt-award"><svg viewBox="0 0 24 24" width="16" height="16" aria-hidden="true"><path fill="currentColor" d="M12 2l2.9 6.1 6.6.8-4.9 4.6 1.3 6.5L12 16.8 6.1 20l1.3-6.5L2.5 8.9l6.6-.8z"/></svg>{{ p.award }}</div>{% endif %}
        <h3 class="mt-ptitle">{{ p.title }}</h3>
        <div class="mt-students">
          {% for s in p.students %}<span class="mt-chip">{{ s }}</span>{% endfor %}
        </div>
        <details class="mt-more">
          <summary>Research area and supervision</summary>
          <dl>
            <dt>Research area</dt><dd>{{ p.area }}</dd>
            <dt>Supervision</dt><dd>{{ p.supervision }}</dd>
          </dl>
        </details>
      </div>
    </article>
    {% endfor %}
  </section>

  <section class="mt-sec" data-g="ms">
    <h2 class="mt-h2">Graduated master's thesis and project students</h2>
    <ul class="mt-list">
      {% for p in m.masters %}
      <li class="mt-item"><span class="mt-name">{{ p.name }}</span><span class="mt-topic">{{ p.topic }}</span></li>
      {% endfor %}
    </ul>
  </section>

  <section class="mt-sec" data-g="ug">
    <h2 class="mt-h2">Undergraduate researchers</h2>
    <ul class="mt-list">
      {% for p in m.undergrad %}
      <li class="mt-item"><span class="mt-name">{{ p.name }}</span><span class="mt-topic">{{ p.topic }}</span></li>
      {% endfor %}
    </ul>
  </section>

  <section class="mt-sec" data-g="prog">
    <h2 class="mt-h2">Program mentorship and community engagement</h2>
    <ul class="mt-list">
      {% for p in m.programs %}
      <li class="mt-item">
        <span class="mt-name">{{ p.title }}</span>
        <span class="mt-topic">{{ p.note }}{% if p.people %}<span class="mt-inline-people">{% for s in p.people %}<span class="mt-chip">{{ s }}</span>{% endfor %}</span>{% endif %}</span>
      </li>
      {% endfor %}
    </ul>
  </section>

  <p class="mt-empty" hidden>No mentees match that search.</p>
</div>

<style>
.mt [hidden] { display: none !important; }
.mt { max-width: 980px; margin: 0 auto; }
.mt-sr { position: absolute; width: 1px; height: 1px; overflow: hidden; clip: rect(0 0 0 0); }

/* Group counts that double as filters */
.mt-tabs { display: grid; grid-template-columns: repeat(7, minmax(0, 1fr)); border-top: 2px solid var(--global-text-color); border-bottom: 1px solid var(--global-divider-color); margin-bottom: 1.25rem; }
.mt-tab { all: unset; cursor: pointer; padding: 1rem 0.8rem 0.9rem; display: flex; flex-direction: column; gap: 0.15rem; border-right: 1px solid var(--global-divider-color); position: relative; }
.mt-tab:last-child { border-right: 0; }
.mt-tab .mt-n { font-size: 1.9rem; font-weight: 700; line-height: 1.1; color: var(--global-text-color); font-variant-numeric: tabular-nums; }
.mt-tab .mt-l { font-size: 0.85rem; color: var(--global-text-color-light); font-weight: 600; }
.mt-tab:hover .mt-n { color: var(--global-theme-color); }
.mt-tab.is-on::after { content: ""; position: absolute; left: 0; right: 0; bottom: -1px; height: 3px; background: var(--global-theme-color); }
.mt-tab.is-on .mt-n, .mt-tab.is-on .mt-l { color: var(--global-theme-color); }
.mt-tab:focus-visible { outline: 2px solid var(--global-theme-color); outline-offset: -2px; }

.mt-search { display: flex; align-items: center; gap: 1rem; margin-bottom: 0.5rem; }
.mt-search input { flex: 1; max-width: 420px; padding: 0.6rem 0.9rem; border: 1px solid var(--global-divider-color); border-radius: 6px; background: var(--global-bg-color); color: var(--global-text-color); font: inherit; font-size: 0.95rem; }
.mt-search input:focus { outline: 2px solid var(--global-theme-color); outline-offset: 1px; border-color: transparent; }
.mt-count { font-size: 0.88rem; color: var(--global-text-color-light); }

.mt-sec { padding-top: 1.6rem; }
.mt-h2 { font-size: 1.35rem; font-weight: 700; margin: 0 0 0.4rem; padding-bottom: 0.7rem; border-bottom: 1px solid var(--global-text-color); }

.mt-name { font-weight: 700; color: var(--global-text-color); }
.mt-sub { font-size: 0.9rem; color: var(--global-theme-color); font-weight: 600; }
.mt-sub2 { font-size: 0.85rem; color: var(--global-text-color-light); }

.mt-hbadge { display: inline-block; margin-top: 0.45rem; font-size: 0.78rem; font-weight: 700; color: #a16207 !important; background: rgba(234,179,8,0.13); border: 1px solid rgba(202,138,4,0.35); border-radius: 999px; padding: 0.12rem 0.6rem; }
.mt-hbadge::before { content: "★ "; }
html[data-theme="dark"] .mt-hbadge { color: #facc15 !important; }
.mt-honors { border-bottom: 1px solid var(--global-divider-color); padding: 0.4rem 0 0.8rem; }
.mt-honors summary { cursor: pointer; list-style: none; display: flex; align-items: baseline; gap: 0.7rem; padding: 0.7rem 0; }
.mt-honors summary::-webkit-details-marker { display: none; }
.mt-honors summary::before { content: ""; align-self: center; width: 0.45rem; height: 0.45rem; border-right: 2px solid var(--global-theme-color); border-bottom: 2px solid var(--global-theme-color); transform: rotate(-45deg); transition: transform 0.2s ease; }
.mt-honors[open] summary::before { transform: rotate(45deg); }
.mt-honors summary:focus-visible, .mt-hbadge:focus-visible { outline: 2px solid var(--global-theme-color); outline-offset: 3px; border-radius: 2px; }
.mt-hcount { font-size: 0.82rem; font-weight: 700; color: var(--global-text-color-light); }
.mt-hlist { list-style: none; padding: 0; margin: 0 0 0 1.15rem; border-left: 2px solid var(--global-divider-color); }
.mt-hlist li { position: relative; display: grid; grid-template-columns: 56px minmax(0, 1fr); gap: 0.9rem; padding: 0.7rem 0 0.7rem 1.1rem; }
.mt-hlist li::before { content: ""; position: absolute; left: -6px; top: 1.05rem; width: 10px; height: 10px; border-radius: 50%; background: #eab308; border: 2px solid var(--global-bg-color); }
.mt-hy { font-weight: 700; color: var(--global-theme-color); font-variant-numeric: tabular-nums; padding-top: 0.1rem; }
.mt-hk { display: inline-block; font-size: 0.72rem; font-weight: 700; color: #a16207; border: 1px solid rgba(202,138,4,0.45); border-radius: 4px; padding: 0.02rem 0.45rem; margin-bottom: 0.3rem; }
.mt-hk--lead { color: var(--global-text-color-light); border-color: var(--global-divider-color); }
html[data-theme="dark"] .mt-hk:not(.mt-hk--lead) { color: #facc15; }
.mt-ht { font-weight: 700; color: var(--global-text-color); line-height: 1.4; }
.mt-hd { font-size: 0.92rem; color: var(--global-text-color); line-height: 1.55; margin-top: 0.15rem; max-width: 70ch; }
.mt-people { display: grid; grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 0; }
.mt-person { display: flex; gap: 0.9rem; align-items: flex-start; padding: 1.1rem 0; border-bottom: 1px solid var(--global-divider-color); }
.mt-person:nth-child(odd) { padding-right: 1.5rem; }
.mt-avatar { flex: none; width: 42px; height: 42px; border-radius: 50%; display: grid; place-items: center; font-weight: 700; color: var(--global-theme-color); border: 1.5px solid var(--global-theme-color); }

.mt-project { display: grid; grid-template-columns: 200px minmax(0, 1fr); gap: 2rem; padding: 1.5rem 0; border-bottom: 1px solid var(--global-divider-color); }
.mt-pprog { font-weight: 700; color: var(--global-text-color); margin-bottom: 0.2rem; }
.mt-award { display: inline-flex; align-items: flex-start; gap: 0.45rem; font-size: 0.86rem; font-weight: 700; color: #a16207; background: rgba(234,179,8,0.12); border: 1px solid rgba(202,138,4,0.35); border-radius: 6px; padding: 0.35rem 0.7rem; margin-bottom: 0.75rem; line-height: 1.4; }
.mt-award svg { flex: none; margin-top: 2px; }
html[data-theme="dark"] .mt-award { color: #facc15; }
.mt-ptitle { font-size: 1.12rem; font-weight: 700; line-height: 1.4; margin: 0 0 0.7rem; color: var(--global-text-color); }
.mt-students { display: flex; flex-wrap: wrap; gap: 0.4rem; }
.mt-chip { font-size: 0.84rem; padding: 0.2rem 0.6rem; border: 1px solid var(--global-divider-color); border-radius: 999px; color: var(--global-text-color); white-space: nowrap; }
.mt-more { margin-top: 0.9rem; }
.mt-more summary { cursor: pointer; font-size: 0.9rem; font-weight: 600; color: var(--global-theme-color); list-style: none; display: inline-flex; align-items: center; gap: 0.4rem; }
.mt-more summary::-webkit-details-marker { display: none; }
.mt-more summary::before { content: ""; width: 0.45rem; height: 0.45rem; border-right: 2px solid currentColor; border-bottom: 2px solid currentColor; transform: rotate(-45deg); transition: transform 0.2s ease; }
.mt-more[open] summary::before { transform: rotate(45deg); }
.mt-more summary:focus-visible { outline: 2px solid var(--global-theme-color); outline-offset: 3px; border-radius: 2px; }
.mt-more dl { margin: 0.8rem 0 0; }
.mt-more dt { font-size: 0.82rem; font-weight: 700; color: var(--global-text-color-light); margin-top: 0.6rem; }
.mt-more dd { margin: 0.15rem 0 0; line-height: 1.6; color: var(--global-text-color); max-width: 68ch; }

.mt-list { list-style: none; padding: 0; margin: 0; }
.mt-list li { display: grid; grid-template-columns: 260px minmax(0, 1fr); gap: 1.5rem; padding: 0.85rem 0; border-bottom: 1px solid var(--global-divider-color); }
.mt-topic { color: var(--global-text-color); line-height: 1.5; }
.mt-inline-people { display: flex; flex-wrap: wrap; gap: 0.4rem; margin-top: 0.45rem; }

.mt mark { background: rgba(250,204,21,0.35); color: inherit; padding: 0 1px; border-radius: 2px; }
.mt-empty { padding: 2rem 0; color: var(--global-text-color-light); }

@media (max-width: 760px) {
  .mt-tabs { grid-template-columns: repeat(3, minmax(0, 1fr)); }
  .mt-tab:nth-child(3n) { border-right: 0; }
  .mt-tab { border-bottom: 1px solid var(--global-divider-color); }
  .mt-tab .mt-n { font-size: 1.5rem; }
  .mt-people { grid-template-columns: 1fr; }
  .mt-person:nth-child(odd) { padding-right: 0; }
  .mt-project { grid-template-columns: 1fr; gap: 0.6rem; }
  .mt-list li { grid-template-columns: 1fr; gap: 0.2rem; }
}
@media (prefers-reduced-motion: reduce) { .mt-more summary::before { transition: none; } }
</style>

<script>
(function () {
  var root = document.querySelector('.mt'); if (!root) return;
  var tabs = root.querySelectorAll('.mt-tab'), secs = root.querySelectorAll('.mt-sec');
  var q = root.querySelector('#mt-q'), count = root.querySelector('.mt-count'), empty = root.querySelector('.mt-empty');
  var group = 'all';
  // remember original text so search highlighting can be undone
  root.querySelectorAll('.mt-item .mt-name, .mt-item .mt-topic, .mt-item .mt-ptitle, .mt-item .mt-chip').forEach(function (el) { el.dataset.orig = el.innerHTML; });

  function esc(s) { return s.replace(/[.*+?^${}()|[\]\\]/g, '\\$&'); }
  function apply() {
    var term = (q.value || '').trim().toLowerCase(), shown = 0;
    secs.forEach(function (sec) {
      var inGroup = group === 'all' || sec.dataset.g === group, any = false;
      sec.querySelectorAll('.mt-item').forEach(function (it) {
        it.querySelectorAll('[data-orig]').forEach(function (el) { el.innerHTML = el.dataset.orig; });
        var hit = !term || it.textContent.toLowerCase().indexOf(term) > -1;
        it.hidden = !(inGroup && hit);
        if (!it.hidden) {
          any = true; shown++;
          if (term) it.querySelectorAll('[data-orig]').forEach(function (el) {
            if (el.children.length && !el.classList.contains('mt-topic')) return;
            el.innerHTML = el.innerHTML.replace(new RegExp('(' + esc(term) + ')(?![^<]*>)', 'ig'), '<mark>$1</mark>');
          });
        }
      });
      sec.hidden = !any;
    });
    count.textContent = term ? shown + (shown === 1 ? ' match' : ' matches') : '';
    empty.hidden = shown > 0;
  }
  tabs.forEach(function (t) {
    t.addEventListener('click', function () {
      group = t.dataset.f;
      tabs.forEach(function (x) { var on = x === t; x.classList.toggle('is-on', on); x.setAttribute('aria-selected', on); });
      try { history.replaceState(null, '', group === 'all' ? location.pathname : '#' + group); } catch (e) {}
      apply();
    });
  });
  q.addEventListener('input', apply);
  root.querySelectorAll('.mt-hbadge').forEach(function (b) {
    b.addEventListener('click', function (e) {
      e.preventDefault();
      var t = root.querySelector('.mt-tab[data-f="honors"]'); if (t) t.click();
      var d = root.querySelector(b.getAttribute('href')); if (d) { d.open = true; d.scrollIntoView({ behavior: 'smooth', block: 'start' }); }
    });
  });
  var h = location.hash.slice(1);
  var start = Array.prototype.find.call(tabs, function (t) { return t.dataset.f === h; });
  if (start) start.click();
})();
</script>
