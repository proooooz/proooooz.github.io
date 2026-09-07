---
layout: page
title: 学习资源
permalink: /resources/
nav: true
nav_order: 4
---

<style>
  .resource-category-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(16rem, 1fr));
    gap: 1rem;
    margin-top: 1.5rem;
  }

  .resource-category-card,
  .resource-category-card:hover,
  .resource-category-card:focus {
    color: var(--global-text-color);
    text-decoration: none;
  }

  .resource-category-card {
    display: block;
    padding: 1.5rem;
    border: 1px solid var(--global-divider-color, #dddddd);
    border-radius: 0.5rem;
    background: var(--global-card-bg-color, transparent);
    transition:
      border-color 0.2s ease,
      transform 0.2s ease;
  }

  .resource-category-card:hover,
  .resource-category-card:focus {
    border-color: var(--global-theme-color, #2698ba);
    transform: translateY(-2px);
  }

  .resource-category-card h2 {
    margin-top: 0;
    margin-bottom: 0.5rem;
  }

  .resource-category-card p {
    margin-bottom: 1rem;
  }

  .resource-category-card span {
    color: var(--global-theme-color, #2698ba);
    font-weight: 500;
  }
</style>

请选择学习资源类别。进入分类页面后，可以直接访问课程、学者主页和会议网站。

<div class="resource-category-grid">
  <a class="resource-category-card" href="{{ '/resources/qse/' | relative_url }}">
    <h2>QSE 模型</h2>
    <p>数量空间经济学、城市经济学与空间经济学课程。</p>
    <span>查看资源 →</span>
  </a>

  <a class="resource-category-card" href="{{ '/resources/econometrics/' | relative_url }}">
    <h2>计量经济学</h2>
    <p>本科计量经济学课程、讲义与配套资料。</p>
    <span>查看资源 →</span>
  </a>

  <a class="resource-category-card" href="{{ '/resources/advanced-macro/' | relative_url }}">
    <h2>高级宏观经济学</h2>
    <p>高级宏观理论、动态规划与 QuantEcon 课程。</p>
    <span>查看资源 →</span>
  </a>

  <a class="resource-category-card" href="{{ '/resources/hank/' | relative_url }}">
    <h2>HANK</h2>
    <p>异质性代理人宏观、财政货币政策与计算方法。</p>
    <span>查看资源 →</span>
  </a>

  <a class="resource-category-card" href="{{ '/resources/economists/' | relative_url }}">
    <h2>经济学家</h2>
    <p>经济学、政治经济学与量化历史研究学者主页。</p>
    <span>查看学者 →</span>
  </a>

  <a class="resource-category-card" href="{{ '/resources/conferences/' | relative_url }}">
    <h2>会议</h2>
    <p>经济学研究机构、学会与重要学术会议。</p>
    <span>查看会议 →</span>
  </a>

  <a class="resource-category-card" href="{{ '/resources/mathematics/' | relative_url }}">
    <h2>数学</h2>
    <p>实分析、泛函分析、统计学与多元统计分析。</p>
    <span>查看资源 →</span>
  </a>
</div>
