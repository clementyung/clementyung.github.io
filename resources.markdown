---
layout: default
title: "Resources"
permalink: /resources/
---

<div class="resources-container">
  
  <div class="resources-list">
    {% for post in site.posts %}
      {% if post.category == "resource" %}
        <div class="resource-card">
          
          <div class="resource-item-row">
            <div class="resource-main">
              <a href="{{ post.url }}" class="resource-link">{{ post.title }}</a>
            </div>
            <div class="resource-action">
              <a href="{{ post.url }}" class="view-btn" aria-label="View {{ post.title }}">
                View
                <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><line x1="5" y1="12" x2="19" y2="12"></line><polyline points="12 5 19 12 12 5"></polyline></svg>
              </a>
            </div>
          </div>

          <div class="resource-summary-box">
            {% if post.summary and post.summary != "" %}
              {{ post.summary }}
            {% else %}
              <p>Placeholder summary</p>
            {% endif %}
          </div>

        </div>
      {% endif %}
    {% endfor %}
  </div>

</div>

<style>
  .resources-container {
    max-width: 800px;
    margin: 0 auto;
    padding: 10px 0;
  }

  .resources-list {
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .resource-card {
    display: flex;
    flex-direction: column;
    background: rgba(148, 163, 184, 0.03);
    border: 1px solid var(--border-color);
    border-radius: 8px;
    overflow: hidden;
    transition: transform 0.15s ease, box-shadow 0.15s ease;
  }

  .resource-card:hover {
    transform: translateY(-1px);
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.04);
  }

  .resource-item-row {
    display: flex;
    align-items: center;
    padding: 14px 16px 10px 16px;
    gap: 16px;
  }

  .resource-main {
    flex: 1;
    display: flex;
    align-items: center;
  }

  .resource-link {
    font-size: 16px;
    font-weight: 600;
    color: var(--text-main);
    text-decoration: none !important;
    line-height: 1.4;
  }

  .resource-card:hover .resource-link {
    color: var(--text-title);
  }

  .resource-action {
    flex-shrink: 0;
  }

  .resource-card:hover .view-btn {
    background: rgba(30, 64, 175, 0.06);
    color: var(--text-title);
  }

  html[data-theme="dark"] .resource-card:hover .view-btn {
    background: rgba(56, 189, 248, 0.08);
  }

  .resource-summary-box {
    font-size: 14px;
    line-height: 1.5;
    color: var(--text-muted);
    padding: 0 16px 14px 16px;
  }

  .resource-summary-box p {
    margin: 0;
  }

  @media (max-width: 600px) {
    .resource-item-row { flex-direction: column; align-items: flex-start; gap: 12px; padding: 16px 16px 8px 16px; }
    .resource-action { width: 100%; border-top: 1px solid var(--border-color); padding-top: 10px; }
    .view-btn { width: 100%; justify-content: space-between; padding: 6px 0; }
    .resource-summary-box { padding: 0 16px 16px 16px; }
  }
</style>