---
layout: ../../layouts/MarkdownPostLayout.astro
title: '【Astro】Marqueeコンポーネントを実装する'
pubDate: 2023-05-08
description: 'Astroにおいて、Marqueeコンポーネントを実装します。'
author: '玖堂いのは'
tags: ["Astro", "CSS"]
---

# 【Astro】Marqueeコンポーネントを実装する
Astroにおいて、Marqueeコンポーネントを実装します。

## 手順
./src/componentsにMarquee.astroというファイルを作成し、以下のように編集する。
```
---
const { message, duration } = Astro.props;
---

<style define:vars={{ duration }}>
  .marquee {
    overflow: hidden;
  }

  .marquee p {
    display: inline-block;
    margin: 0;
    padding-left: 100%;
    white-space: nowrap;
    animation: marquee var(--duration) linear infinite;
  }

  @keyframes marquee {
    from {
      transform: translate(0%);
    }
    to {
      transform: translate(-100%);
    }
  }
</style>

<div class="marquee">
  <p>{message}</p>
</div>
```

以下のようにインポートすることで、Marqueeコンポーネントを使用することができる。
```
---
import Marquee from "../components/Marquee.astro";
---

<style>
  .dotted-border {
    width: 640px;
    padding: 5px 0;
    border: dotted 4px;
    color: #0088ff;
  }
</style>

<div class="dotted-border">
  <Marquee message="今年度も頑張りましょう!" duration="15s" />
</div>
```
