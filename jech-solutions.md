---
layout: default
title: "Suggested Solutions to Jech's Set Theory"
permalink: /jech-solutions/
---

<div class="solutions-container">
  
  <div class="solutions-intro-bar">
    <p class="solutions-intro">
      I spent most of my summer break before the start of my PhD doing exercises in Jech's book. Here are my suggested solutions.
    </p>
    <button class="readme-trigger-btn" id="open-readme-btn">
      <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle><line x1="12" y1="16" x2="12" y2="12"></line><line x1="12" y1="8" x2="12.01" y2="8"></line></svg>
      Readme and Credits
    </button>
  </div>

  <div class="chapters-list">
    {% for post in site.posts reversed %}
      {% if post.category == "solution" %}
        {% assign chapter_parts = post.chapter | split: ") " %}
        {% assign ch_number = chapter_parts[0] | strip %}
        {% assign ch_title = chapter_parts[1] %}

        {% assign missing = "" %}
        {% if ch_number == "7" %}
          {% assign missing = "Ex. 7.31" %}
        {% elsif ch_number == "15" %}
          {% assign missing = "Ex. 15.11, 15.27" %}
        {% elsif ch_number == "16" %}
          {% assign missing = "Ex. 16.4, 16.18" %}
        {% elsif ch_number == "19" %}
          {% assign missing = "Ex. 19.12" %}
        {% elsif ch_number == "20" %}
          {% assign missing = "Ex. 20.9, 20.20" %}
        {% elsif ch_number == "24" %}
          {% assign missing = "Ex. 24.10" %}
        {% endif %}

        <div class="chapter-item">
          <div class="chapter-badge">Ch {{ ch_number }}</div>
          <div class="chapter-main">
            <a href="{{ post.url }}" class="chapter-link">{{ ch_title }}</a>
            {% if missing != "" %}
              <span class="missing-tag">Missing: {{ missing }}</span>
            {% endif %}
          </div>
          <div class="chapter-action">
            <a href="{{ post.url }}" class="view-btn" aria-label="View Solutions for Chapter {{ ch_number }}">
              View
              <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><line x1="5" y1="12" x2="19" y2="12"></line><polyline points="12 5 19 12 12 5"></polyline></svg>
            </a>
          </div>
        </div>
      {% endif %}
    {% endfor %}
  </div>

</div>

<template id="jech-readme-template">
  <p>I completed almost every exercise from Chapter 1 to Chapter 24, except 7.31, 15.11, 15.27, 16.4, 16.18, 19.12, 20.9, 20.20, and 24.10. Currently, I do not plan to do any further exercises.</p>
  
  <p>While I try my best to do all the exercises myself, I do not take full credit for all the solutions. Several external sources that I frequently consulted include the <a href="https://math.stackexchange.com/" target="_blank">Math StackExchange</a> network, the <a href="https://mathoverflow.net/" target="_blank">MathOverflow</a> network, <a href="https://frederic-wang.fr/mathematics/set-theory/jech/" target="_blank">a partial suggested solution manual written by Frederic Wang</a> (no longer available), and <a href="http://euclid.colorado.edu/~monkd/jech.pdf" target="_blank">notes written by J. D. Monk</a>.</p>
  
  <p>I also repeatedly referred to the books <em>The Higher Infinite</em> (2003) by Akihiro Kanamori, <em>Set Theory</em> (2011) by Kenneth Kunen, and occasionally <em>Combinatorial Set Theory: With a Gentle Introduction to Forcing</em> (2018) by Lorenz J. Halbeisen. For exercises related to Boolean algebras, I also referred to <em>Introduction to Boolean Algebras</em> (2009) by Steven Givant and Paul Halmos. Sometimes an exercise is adapted from a theorem proved in a paper cited in the <em>Historical Notes</em> section at the end of each chapter. I also referred to those papers if I was stuck and could not find help in the sources listed above.</p>
  
  <p>I do not claim that my solutions are fully correct. I attempted these exercises to better understand the concepts in the same chapter, so I do not verify the correctness of most solutions here. There may be grammatical errors in my solution, as English is not my native language, and I was not meticulous in my writing. If you spot any errors or typos or have any queries in general, please feel free to drop me an email.</p>
</template>

<style>
  .solutions-container {
    max-width: 800px;
    margin: 0 auto;
    padding: 10px 0;
  }

  .solutions-intro-bar {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    gap: 30px;
    margin-bottom: 35px;
    border-bottom: 1px solid var(--border-color);
    padding-bottom: 20px;
  }

  .solutions-intro {
    font-size: 16px;
    line-height: 1.6;
    color: var(--text-main);
    margin: 0;
    flex: 1;
  }

  .readme-trigger-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(148, 163, 184, 0.08);
    color: var(--text-muted);
    border: 1px solid var(--border-color);
    padding: 7px 14px;
    border-radius: 6px;
    font-size: 13px;
    font-weight: 600;
    cursor: pointer;
    white-space: nowrap;
    transition: background-color 0.15s ease, color 0.15s ease;
  }

  .readme-trigger-btn:hover {
    background: var(--text-title);
    color: #ffffff;
    border-color: var(--text-title);
  }

  .chapters-list {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  .chapter-item {
    display: flex;
    align-items: center;
    background: rgba(148, 163, 184, 0.03);
    border: 1px solid var(--border-color);
    padding: 12px 16px;
    border-radius: 8px;
    gap: 16px;
    transition: transform 0.15s ease, box-shadow 0.15s ease;
  }

  .chapter-item:hover {
    transform: translateY(-1px);
    box-shadow: 0 4px 12px rgba(0,0,0,0.04);
  }

  .chapter-badge {
    font-size: 12px;
    font-weight: 700;
    background: rgba(30, 64, 175, 0.08);
    color: var(--text-title);
    padding: 4px 0;
    width: 54px;
    display: inline-flex;
    justify-content: center;
    border-radius: 6px;
    white-space: nowrap;
    text-transform: uppercase;
    letter-spacing: 0.2px;
    flex-shrink: 0;
  }

  html[data-theme="dark"] .chapter-badge {
    background: rgba(56, 189, 248, 0.12);
  }

  .chapter-main {
    flex: 1;
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    gap: 12px;
  }

  .chapter-link {
    font-size: 16px;
    font-weight: 600;
    color: var(--text-main);
    text-decoration: none !important;
    line-height: 1.4;
  }

  .chapter-item:hover .chapter-link {
    color: var(--text-title);
  }

  .missing-tag {
    font-size: 11px;
    background: rgba(185, 28, 28, 0.06);
    color: #b91c1c;
    padding: 2px 8px;
    border-radius: 4px;
    font-weight: 500;
    border: 1px solid rgba(185, 28, 28, 0.15);
  }

  html[data-theme="dark"] .missing-tag {
    background: rgba(248, 113, 113, 0.07);
    color: #f87171;
    border: 1px solid rgba(248, 113, 113, 0.18);
  }

  .chapter-action {
    flex-shrink: 0;
  }

  .chapter-item:hover .view-btn {
    background: rgba(30, 64, 175, 0.06);
    color: var(--text-title);
  }

  html[data-theme="dark"] .chapter-item:hover .view-btn {
    background: rgba(56, 189, 248, 0.08);
  }

  @media (max-width: 600px) {
    .solutions-intro-bar { flex-direction: column; gap: 16px; }
    .readme-trigger-btn { width: 100%; justify-content: center; }
    .chapter-item { flex-direction: column; align-items: flex-start; gap: 12px; padding: 16px; }
    .chapter-main { flex-direction: column; align-items: flex-start; gap: 6px; }
    .chapter-action { width: 100%; border-top: 1px solid var(--border-color); padding-top: 10px; }
    .view-btn { width: 100%; justify-content: space-between; padding: 6px 0; }
  }
</style>

<script>
  (function() {
    function initModalTrigger() {
      const triggerBtn = document.getElementById('open-readme-btn');
      const templateContent = document.getElementById('jech-readme-template');

      if (triggerBtn && templateContent) {
        triggerBtn.addEventListener('click', function() {
          if (typeof window.openSiteModal === 'function') {
            window.openSiteModal('Readme and Credits', templateContent.innerHTML);
          } else {
            console.error('Global modal engine function is missing.');
          }
        });
      }
    }

    if (document.readyState === 'loading') {
      document.addEventListener('DOMContentLoaded', initModalTrigger);
    } else {
      initModalTrigger();
    }
  })();
</script>