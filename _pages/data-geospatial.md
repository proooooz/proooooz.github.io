---
layout: page
title: 地理遥感数据
permalink: /data/geospatial/
nav: false
---

<style>
  .post article a,
  .post article a:hover,
  .post article a:focus {
    color: var(--global-text-color);
  }

  .resource-details {
    margin-top: 0.5rem;
  }

  .resource-details summary {
    cursor: pointer;
    font-weight: 500;
  }

  .resource-details p {
    margin-top: 0.75rem;
  }

  .resource-figure {
    margin: 1.5rem 0 2rem;
  }

  .resource-figure img {
    display: block;
    width: 100%;
    height: auto;
    border: 1px solid var(--global-divider-color, #dddddd);
    border-radius: 0.5rem;
  }
</style>

<p><a href="{{ '/data/' | relative_url }}">← 返回数据分类</a></p>

1. [**_HydroSHEDS_** 数据库](https://www.hydrosheds.org/)

   <details class="resource-details">
     <summary>详细介绍</summary>
     <p><strong><em>HydroSHEDS</em></strong> 数据库提供一系列全球数字数据层，支持全球水文生态研究和应用。其丰富的水文数据产品包括流域边界、河流网络和湖泊，涵盖多种分辨率和尺度。HydroSHEDS 数据以标准 GIS 格式免费提供，并构成广泛评估的地理空间框架，这些评估涵盖水文、环境、保护、社会经济和人类健康等领域。</p>
   </details>

   <figure class="resource-figure">
     <img src="{{ '/assets/img/data/hydrosheds-data-products.png' | relative_url }}" alt="HydroSHEDS 河流网络、人工修正与自然洼地数据示意图" loading="lazy" decoding="async">
   </figure>

2. [**_中国城市洪涝事件（2003—2022）_ 数据集**](https://zenodo.org/records/17775123)

   <details class="resource-details">
     <summary>详细介绍</summary>
     <p><strong><em>中国城市洪涝事件（2003—2022）</em></strong> 数据集整理了中国 285 个地级市政府工作报告中识别出的城市洪涝事件，并提供这些城市的行政边界数据。其城市—年份面板覆盖 2003—2022 年，共包含 5,700 条记录；其中 <code>count</code> 变量表示某城市当年政府工作报告中识别出的洪涝事件次数，数值为 0 表示报告中未提及洪涝事件，数值不小于 1 表示识别到洪涝事件。</p>
     <p>数据文件包括 UTF-8 编码的 <code>Urban_Flood_Counts_2003_2022.csv</code>，以及包含 285 个城市空间边界文件的 <code>City_Boundaries_GPKG.zip</code>。边界数据采用 GeoPackage 格式与 WGS84 坐标参考系统（EPSG:4326），文件名可与 CSV 中的城市名称对应。该数据集由 ZHU, Honglin 发布于 Zenodo，版本为 v1，DOI 为 <a href="https://doi.org/10.5281/zenodo.17775123">10.5281/zenodo.17775123</a>，适用于城市洪涝风险、区域灾害差异、气候适应与空间面板分析等研究。</p>
   </details>
