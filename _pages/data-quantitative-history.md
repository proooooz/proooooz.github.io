---
layout: page
title: 量化历史经济数据
permalink: /data/quantitative-history/
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

1. [**_China Historical Geographic Information System_（CHGIS，中国历史地理信息系统）**](https://chgis.fas.harvard.edu/data/chgis/v6/)

   <details class="resource-details">
     <summary>详细介绍</summary>
     <p><em>China Historical Geographic Information System</em>（CHGIS）数据库提供中国历史时期地名、行政区划、行政隶属关系及地理空间位置等信息，主要用于刻画中国历代行政建制及历史地名在时间和空间维度上的动态变化。该项目由哈佛大学与复旦大学合作建设，形成了一套面向中国历史行政地理研究的标准化历史地理信息系统。CHGIS 的主体数据覆盖自公元前 221 年至 1911 年的中国历代行政地理变化，并提供 1820 年和 1911 年等全国性历史行政区划时间截面数据；所涉及的行政单位包括省（Province）、路或道等中间层级（Circuit）、府州等府级单位（Prefecture）以及县（County）等，可用于重建不同历史时期的行政区划体系。最新版主体数据为 2016 年发布的 CHGIS Version 6，其中进一步更新了县级和府级行政单位的时间序列数据。</p>
     <p>与一般仅记录“地名—经纬度”对应关系的现代地名数据库不同，CHGIS 的核心特点是将<strong>时间属性直接纳入地名及行政单位的定义之中</strong>。数据库以“Historical Instance（历史实例）”作为基本记录单位：当某一地名的名称、行政级别以及与之关联的空间对象在一段时期内保持不变时，该时期被定义为一个独立的历史实例，并记录其开始和结束年份；一旦发生改名、行政建制调整、行政级别改变、治所迁移或相关空间对象变化，数据库便建立新的历史实例。因此，CHGIS 中的同一个历史地区并非对应一个永久不变的地理编码，而是可以随时间形成多个彼此衔接的历史记录。这种数据结构能够较为准确地处理中国历史上频繁发生的废置、复置、改名、升格、降格、分置、合并和治所迁徙等行政沿革，使研究者能够回答“某一地区在某一年叫什么名称、属于何种行政级别、隶属于哪个上级行政单位以及其治所位于何处”等具有明确时间约束的历史地理问题。</p>
     <p>在具体的数据结构上，CHGIS 以 <strong>Main Table（Historical Instance Table）</strong>为核心，并通过多个关联表构成关系型历史地理数据库。主表记录历史行政单位的地名、有效起止时间以及相应的历史实例信息；<strong>Part Of Table</strong> 专门记录行政单位之间随时间变化的上下级隶属关系，即通过 CHILD 与 PARENT 的关系描述某一县、州、府等单位在特定时期隶属于哪个上一级行政单位。例如，同一个县在自身名称和行政级别没有发生变化的情况下，其上级府州仍可能发生数次调整，因此 CHGIS 将这种隶属关系单独赋予有效时间，而不是简单地把一个固定的“所属府州”字段附加在地名后面。这种设计能够重建某一历史年份完整的“县—府州—省”等纵向行政层级关系，也可以追踪一个行政单位在较长时期内隶属体系的变化。</p>
     <p>与此同时，CHGIS 将历史行政实体与具体的 GIS 空间对象相连接。数据库中的 <strong>GIS Info Table</strong> 保存点或面空间对象的坐标、GIS 图层、底图来源、对象类型及相关编辑信息，并通过 <code>pt_id</code> 和 <code>bou_id</code> 等标识符与历史实例相连接。其中，点对象通常用于表示县治、府治、州治以及其他历史聚落或行政中心的位置，而面对象则用于表示能够被重建的历史行政区边界。因此，CHGIS 在概念上明确区分了“行政单位本身”与“行政机构所在地”：一个县的县治可以发生迁移，而其行政区域未必同步变化；反之，行政辖区也可能发生扩张或缩小，而治所位置保持不变。通过将历史实体、行政关系以及点状或面状空间对象分别储存并相互关联，CHGIS 可以比简单的历史地图更精确地表达行政区划随时间发生的复杂变化。</p>
     <p>在地名标准化方面，CHGIS 还建立了相应的<strong>异名与名称变体体系</strong>。除主表中的标准地名外，数据库利用 Alt Name Table 保存同一历史地点可能出现的不同拼写、罗马化形式以及名称变体，从而避免因为拼音、威妥玛拼音或其他历史转写方式不同而把同一地点错误识别为多个不同实体。与此同时，<strong>Source Notes Table</strong> 保存时间序列记录所依据的历史资料出处、相关引文及编辑者的考证说明，使数据库中的历史地名和行政沿革不仅具有空间定位信息，也保留一定程度的史料依据和历史考证信息。CHGIS 因而并非单纯将《中国历史地图集》等历史地图进行数字化，而是把历史地名考证、行政沿革、时间信息和 GIS 空间对象整合到统一的关系型数据框架之中。</p>
     <p>从数据组织形式看，CHGIS 可以进一步区分为 <strong>Time Series（时间序列）</strong>和 <strong>Time Slice（时间截面）</strong>两类数据。Time Series 数据关注同一个行政单位在长期历史过程中的连续变化，可以用于追踪县、府、州、省等行政实体的设立、废止、名称变化、隶属调整和空间变迁；Time Slice 数据则以某一个具体年份为基准，重建该时点全国或较大区域的行政区划状态。CHGIS 提供的 1820 年和 1911 年全国性数据就是典型的时间截面数据，而从公元前 221 年至 1911 年的历代行政单位变化则构成其历史时间序列的重要基础。因此，研究者既可以利用 CHGIS 制作某一时期的历史行政区划地图，也可以利用其时间属性构建跨朝代或跨时期的历史地理面板数据。</p>
     <p>CHGIS 的另一重要用途是作为历史资料的<strong>标准化地理编码系统（historical geocoding system）</strong>。研究者可以首先将地方志、人口册、科举名录、税收资料、粮价资料、战争记录、灾害记录、商业活动或其他历史文献中的府、州、县等地名与 CHGIS 中的历史地名进行匹配，再根据对应历史年份确定正确的行政实例及地理坐标，从而把原本仅以文字地名记录的历史信息转化为空间数据。在此基础上，可以进一步与河流、海岸线、地形、高程、气候、交通路线、运河、驿站、城市、港口以及现代行政区划等 GIS 数据进行空间叠加和距离计算，为历史经济学、经济史、政治经济学、历史人口学以及数字人文研究提供基础性的空间匹配框架。哈佛大学目前也将 CHGIS 描述为一套有关中国历史行政地理的综合数据集，并通过 Temporal Gazetteer（TGAZ）等工具进一步支持历史地名的机器检索以及与其他数字人文系统的数据关联。</p>
     <p>需要注意的是，CHGIS 所提供的空间信息在不同历史时期、不同地区和不同行政级别之间并不具有完全一致的精度。对于史料能够较可靠确定的历史行政实体，可以提供治所点位甚至行政区边界；而对于缺乏足够历史资料的地区，往往只能较可靠地确定行政中心位置，而无法精确恢复历史辖区边界。因此，在实证研究中，应区分<strong>历史地名识别、行政隶属关系、治所坐标和历史行政边界</strong>四种不同层次的信息，尤其不能简单把历史县治坐标理解为整个历史县域的空间范围。总体而言，CHGIS 最重要的价值在于将中国历史上不断变化的行政单位转化为带有<strong>唯一识别、有效时间、行政层级和空间位置</strong>的标准化历史地理实体，从而为历史文献的地名标准化、历史数据的空间化以及跨时期历史地理数据匹配提供统一基础。</p>
   </details>

   <figure class="resource-figure">
     <img src="{{ '/assets/img/data/chgis-historical-map.png' | relative_url }}" alt="中国历史地图中的山川、道路与聚落示意图" loading="lazy" decoding="async">
   </figure>
