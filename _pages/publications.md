---
layout: page
permalink: /publications/
title: Recent Publications
description: ""
nav: true
nav_order: 2
---

<div class="pb-tools" hidden>
  <div class="pb-kinds" role="group" aria-label="Filter by publication type">
    <button class="pb-kind is-on" data-k="all" aria-pressed="true"><span class="pb-n"></span><span class="pb-l">All publications</span></button>
    <button class="pb-kind" data-k="conference" aria-pressed="false"><span class="pb-n"></span><span class="pb-l">Conference</span></button>
    <button class="pb-kind" data-k="journal" aria-pressed="false"><span class="pb-n"></span><span class="pb-l">Journal</span></button>
    <button class="pb-kind" data-k="workshop" aria-pressed="false"><span class="pb-n"></span><span class="pb-l">Workshop</span></button>
    <button class="pb-kind" data-k="other" aria-pressed="false"><span class="pb-n"></span><span class="pb-l">Preprint &amp; chapter</span></button>
  </div>

  <div class="pb-row">
    <div class="pb-years" role="group" aria-label="Filter by year"></div>
  </div>

  <div class="pb-row">
    <label for="pb-q" class="pb-sr">Search publications</label>
    <input id="pb-q" type="search" placeholder="Search titles, authors or venues" autocomplete="off">
    <span class="pb-status" aria-live="polite"></span>
    <button class="pb-reset" type="button" hidden>Clear filters</button>
  </div>
</div>

<div class="publications">

{% bibliography %}

</div>

<p class="pb-empty" hidden>No publications match these filters.</p>

<style>
.pb-tools [hidden], .pb-empty[hidden], .publications [hidden] { display: none !important; }
.pb-sr { position: absolute; width: 1px; height: 1px; overflow: hidden; clip: rect(0 0 0 0); }

/* Type filters, with counts */
.pb-kinds { display: grid; grid-template-columns: repeat(5, minmax(0, 1fr)); border-top: 2px solid var(--global-text-color); border-bottom: 1px solid var(--global-divider-color); }
.pb-kind { all: unset; cursor: pointer; padding: 1rem 0.85rem 0.9rem; border-right: 1px solid var(--global-divider-color); display: flex; flex-direction: column; gap: 0.15rem; position: relative; }
.pb-kind:last-child { border-right: 0; }
.pb-kind .pb-n { font-size: 1.9rem; font-weight: 700; line-height: 1.1; color: var(--global-text-color); font-variant-numeric: tabular-nums; }
.pb-kind .pb-l { font-size: 0.85rem; font-weight: 600; color: var(--global-text-color-light); }
.pb-kind:hover .pb-n { color: var(--global-theme-color); }
.pb-kind.is-on::after { content: ""; position: absolute; left: 0; right: 0; bottom: -1px; height: 3px; background: var(--global-theme-color); }
.pb-kind.is-on .pb-n, .pb-kind.is-on .pb-l { color: var(--global-theme-color); }
.pb-kind:focus-visible { outline: 2px solid var(--global-theme-color); outline-offset: -2px; }
.pb-kind[disabled] { opacity: 0.4; cursor: default; }

.pb-row { display: flex; flex-wrap: wrap; align-items: center; gap: 0.6rem 1rem; margin-top: 1rem; }
.pb-years { display: flex; flex-wrap: wrap; gap: 0.4rem; flex: 1; }
.pb-year { all: unset; cursor: pointer; font-size: 0.88rem; font-weight: 600; font-variant-numeric: tabular-nums; padding: 0.3rem 0.75rem; border: 1px solid var(--global-divider-color); border-radius: 999px; color: var(--global-text-color); }
.pb-year:hover { border-color: var(--global-theme-color); color: var(--global-theme-color); }
.pb-year[aria-pressed="true"] { background: var(--global-theme-color); border-color: var(--global-theme-color); color: #fff; }
.pb-year:focus-visible, .pb-reset:focus-visible { outline: 2px solid var(--global-theme-color); outline-offset: 2px; }
.pb-sel { display: inline-flex; align-items: center; gap: 0.45rem; font-size: 0.9rem; font-weight: 600; cursor: pointer; margin: 0; color: var(--global-text-color); }
.pb-sel input { accent-color: var(--global-theme-color); width: 1rem; height: 1rem; }
#pb-q { flex: 1; max-width: 460px; padding: 0.6rem 0.9rem; border: 1px solid var(--global-divider-color); border-radius: 6px; background: var(--global-bg-color); color: var(--global-text-color); font: inherit; font-size: 0.95rem; }
#pb-q:focus { outline: 2px solid var(--global-theme-color); outline-offset: 1px; border-color: transparent; }
.pb-status { font-size: 0.88rem; color: var(--global-text-color-light); }
.pb-reset { all: unset; cursor: pointer; font-size: 0.88rem; font-weight: 600; color: var(--global-theme-color); text-decoration: underline; text-underline-offset: 3px; }
.pb-empty { padding: 2rem 0; color: var(--global-text-color-light); }

/* Year headings and entries */
.publications h2.bibliography { font-size: 1.35rem; font-weight: 700; text-align: left; color: var(--global-text-color); border-top: 0; border-bottom: 1px solid var(--global-text-color); padding: 0 0 0.6rem; margin: 2.2rem 0 0; }
.publications ol.bibliography li { padding: 1.35rem 0; margin: 0; border-bottom: 1px solid var(--global-divider-color); }
.publications ol.bibliography li:last-child { border-bottom: 0; }
.publications .title { font-size: 1.04rem; line-height: 1.45; margin-bottom: 0.25rem; }
.publications .author { font-size: 0.93rem; line-height: 1.5; color: var(--global-text-color); }
.publications .periodical { font-size: 0.9rem; color: var(--global-text-color-light); line-height: 1.5; }
.publications .pub-notes { display: flex; flex-wrap: wrap; gap: 0.35rem; margin-top: 0.4rem; }
.publications .pub-note { font-size: 0.78rem; font-weight: 700; color: var(--global-theme-color); border: 1px solid var(--global-theme-color); border-radius: 4px; padding: 0.05rem 0.45rem; }
.publications .links { margin-top: 0.55rem; }
.publications .links .btn { font-size: 0.78rem; font-weight: 600; padding: 0.2rem 0.65rem; border-radius: 4px; }
.publications abbr.badge { font-size: 0.74rem; font-weight: 700; padding: 0.3rem 0.35rem; border-radius: 4px !important; }
.publications .preview { border-radius: 6px !important; box-shadow: none !important; border: 1px solid var(--global-divider-color); }
.publications mark { background: rgba(250,204,21,0.35); color: inherit; padding: 0 1px; border-radius: 2px; }
.pub-ph { width: 100%; aspect-ratio: 16 / 9; margin-top: 0.4rem; border: 1px dashed var(--global-divider-color); border-radius: 6px; display: grid; place-items: center; color: var(--global-text-color-light); opacity: 0.7; }
.pub-sel-flag { display: inline-block; margin-left: 0.5rem; vertical-align: 2px; font-size: 0.7rem; font-weight: 700; color: #a16207; background: rgba(234,179,8,0.14); border: 1px solid rgba(202,138,4,0.35); border-radius: 4px; padding: 0 0.4rem; }
html[data-theme="dark"] .pub-sel-flag { color: #facc15; }

@media (max-width: 760px) {
  .pb-kinds { grid-template-columns: repeat(3, minmax(0, 1fr)); }
  .pb-kind { border-bottom: 1px solid var(--global-divider-color); }
  .pb-kind:nth-child(3n) { border-right: 0; }
  .pb-kind .pb-n { font-size: 1.45rem; }
  #pb-q { max-width: none; flex-basis: 100%; }
}
</style>

<script>
(function () {
  var tools = document.querySelector('.pb-tools'), list = document.querySelector('.publications');
  if (!tools || !list) return;
  var items = Array.prototype.slice.call(list.querySelectorAll('ol.bibliography > li'));
  var kindOf = function (li) { var k = (li.querySelector('.pub-entry') || {}).dataset; k = k ? k.kind : 'conference'; return (k === 'preprint' || k === 'chapter') ? 'other' : k; };
  var yearOf = function (li) { var e = li.querySelector('.pub-entry'); return e ? e.dataset.year : ''; };
  var selOf = function (li) { var e = li.querySelector('.pub-entry'); return e && e.dataset.selected === '1'; };
  var state = { kind: 'all', year: '', sel: false, q: '' };

  // counts on the type filters
  var counts = { all: items.length, conference: 0, journal: 0, workshop: 0, other: 0 };
  items.forEach(function (li) { counts[kindOf(li)]++; });
  tools.querySelectorAll('.pb-kind').forEach(function (b) {
    b.querySelector('.pb-n').textContent = counts[b.dataset.k];
    if (!counts[b.dataset.k]) b.disabled = true;
  });

  // year chips
  var years = [];
  items.forEach(function (li) { var y = yearOf(li); if (y && years.indexOf(y) < 0) years.push(y); });
  years.sort(function (a, b) { return b - a; });
  var yBox = tools.querySelector('.pb-years');
  years.forEach(function (y) {
    var b = document.createElement('button'); b.className = 'pb-year'; b.type = 'button';
    b.textContent = y; b.dataset.y = y; b.setAttribute('aria-pressed', 'false'); yBox.appendChild(b);
  });

  // mark selected papers
  items.forEach(function (li) {
    li.querySelectorAll('.title, .author, .periodical').forEach(function (el) { el.dataset.orig = el.innerHTML; });
  });

  var status = tools.querySelector('.pb-status'), reset = tools.querySelector('.pb-reset'), empty = document.querySelector('.pb-empty');
  function esc(s) { return s.replace(/[.*+?^${}()|[\]\\]/g, '\\$&'); }
  function apply() {
    var shown = 0, term = state.q.toLowerCase();
    items.forEach(function (li) {
      li.querySelectorAll('[data-orig]').forEach(function (el) { el.innerHTML = el.dataset.orig; });
      var ok = (state.kind === 'all' || kindOf(li) === state.kind) && (!state.year || yearOf(li) === state.year) && (!state.sel || selOf(li));
      if (ok && term) ok = li.textContent.toLowerCase().indexOf(term) > -1;
      li.hidden = !ok;
      if (ok) {
        shown++;
        if (term) li.querySelectorAll('[data-orig]').forEach(function (el) {
          el.innerHTML = el.innerHTML.replace(new RegExp('(' + esc(state.q) + ')(?![^<]*>)', 'ig'), '<mark>$1</mark>');
        });
      }
    });
    list.querySelectorAll('h2.bibliography').forEach(function (h) {
      var ol = h.nextElementSibling; var any = ol && ol.querySelector('li:not([hidden])');
      h.hidden = !any; if (ol) ol.hidden = !any;
    });
    var filtered = state.kind !== 'all' || state.year || state.sel || term;
    status.textContent = filtered ? 'Showing ' + shown + ' of ' + items.length : '';
    reset.hidden = !filtered; empty.hidden = shown > 0;
  }

  tools.querySelectorAll('.pb-kind').forEach(function (b) {
    b.addEventListener('click', function () {
      state.kind = b.dataset.k;
      tools.querySelectorAll('.pb-kind').forEach(function (x) { var on = x === b; x.classList.toggle('is-on', on); x.setAttribute('aria-pressed', on); });
      apply();
    });
  });
  yBox.addEventListener('click', function (e) {
    var b = e.target.closest('.pb-year'); if (!b) return;
    state.year = state.year === b.dataset.y ? '' : b.dataset.y;
    yBox.querySelectorAll('.pb-year').forEach(function (x) { x.setAttribute('aria-pressed', x.dataset.y === state.year); });
    apply();
  });
  tools.querySelector('#pb-q').addEventListener('input', function (e) { state.q = e.target.value.trim(); apply(); });
  reset.addEventListener('click', function () {
    state = { kind: 'all', year: '', sel: false, q: '' };
    tools.querySelector('#pb-q').value = '';
    tools.querySelector('.pb-kind[data-k="all"]').click();
    yBox.querySelectorAll('.pb-year').forEach(function (x) { x.setAttribute('aria-pressed', 'false'); });
    apply();
  });

  tools.hidden = false;
  apply();
})();
</script>
