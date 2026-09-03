---
layout: page
title: 数据
permalink: /data/
nav: true
nav_order: 5
---

<style>
  .data-category-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(16rem, 1fr));
    gap: 1rem;
    margin-top: 1.5rem;
  }

  .data-category-card,
  .data-category-card:hover,
  .data-category-card:focus {
    color: var(--global-text-color);
    text-decoration: none;
  }

  .data-category-card {
    display: block;
    padding: 1.5rem;
    border: 1px solid var(--global-divider-color, #dddddd);
    border-radius: 0.5rem;
    background: var(--global-card-bg-color, transparent);
    transition:
      border-color 0.2s ease,
      transform 0.2s ease;
  }

  .data-category-card:hover,
  .data-category-card:focus {
    border-color: var(--global-theme-color, #2698ba);
    transform: translateY(-2px);
  }

  .data-category-card h2 {
    margin-top: 0;
    margin-bottom: 0.5rem;
  }

  .data-category-card p {
    margin-bottom: 1rem;
  }

  .data-category-card span {
    color: var(--global-theme-color, #2698ba);
    font-weight: 500;
  }
</style>

请选择数据类别。进入分类页面后，可以展开各数据库的详细介绍，并直接访问官方网站。

<div class="data-category-grid">
  <a class="data-category-card" href="{{ '/data/geospatial/' | relative_url }}">
    <h2>地理遥感数据</h2>
    <p>水文、流域、河流网络、湖泊及其他地理空间数据。</p>
    <span>查看数据 →</span>
  </a>

  <a class="data-category-card" href="{{ '/data/international-trade/' | relative_url }}">
    <h2>国际贸易数据</h2>
    <p>贸易、投资、企业、制度、供应链、地缘政治与创新数据。</p>
    <span>查看数据 →</span>
  </a>

  <a class="data-category-card" href="{{ '/data/how-to-use/' | relative_url }}">
    <h2>如何使用</h2>
    <p>数据访问、下载、整理、引用与复现的基本说明。</p>
    <span>查看说明 →</span>
  </a>

  <a class="data-category-card" href="{{ '/data/references/' | relative_url }}">
    <h2>相关文献</h2>
    <p>整理使用相关数据库的代表性论文与研究资料。</p>
    <span>查看文献 →</span>
  </a>
</div>
