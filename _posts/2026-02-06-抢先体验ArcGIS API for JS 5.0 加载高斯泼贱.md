---
layout: single
title: 抢先体验 ArcGIS API for JS 5.0 加载高斯高斯泼贱
date: 2026-02-06 15:26:45 +0800
categories: jekyll update
permalink: /zh/r&d/gis/
---

截止2026年2月6日，官方尚未正式发布 ArcGIS API for JavaScript 5.0 版本，但我们可以通过 `next` 预发布版本提前体验。

> 注：官方此前表示计划在今年2月份发布正式版，笔者实在按捺不住好奇心，决定先体验一番。

## 安装 next 版本

通过 npm 安装开发版本：

```bash
npm i @arcgis/core@next
```

安装完成后，可以查看版本号：

```javascript
import * as esriNS from "@arcgis/core/kernel.js";
console.log(esriNS.version); // 输出：5.1
```

目前开发版本已经来到 5.1。

![image1.png]({{ site.baseurl }}/assets/images/image1.png "高斯泼溅图层类")
可以看到高斯泼溅图层类已经加入到 5.0 版本中。

## 加载高斯泼溅图层

使用方式与其他图层类似，引入 `GaussianSplatLayer` 类即可：

```javascript
import GaussianSplatLayer from "@arcgis/core/layers/GaussianSplatLayer.js";

const gaussianSplatLayer = new GaussianSplatLayer({
  url: "https://tiles.arcgis.com/tiles/z2tnIkrLQ2BRzr6P/arcgis/rest/services/Portcoast/3DTilesServer/tileset.json",
});

map.add(gaussianSplatLayer);
```

## 效果展示

下图是高斯泼溅模型效果，模型精细度很高，尤其是栏杆等管状物体的表现：

![image2.png]({{ site.baseurl }}/assets/images/image2.png "模型精细度展示")

对烟雾效果的还原也相当出色：

![image3.png]({{ site.baseurl }}/assets/images/image3.png "烟雾效果展示")
