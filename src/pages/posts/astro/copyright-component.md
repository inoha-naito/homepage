---
layout: ../../../layouts/MarkdownPostLayout.astro
title: '【Astro】Copyrightコンポーネントを実装する'
pubDate: 2023-05-09
description: 'Astroにおいて、Copyrightコンポーネントを実装します。'
author: '玖堂いのは'
tags: ["Astro", "JavaScript"]
---

# 【Astro】Copyrightコンポーネントを実装する
Astroにおいて、Copyrightコンポーネントを実装します。

## 手順
./src/componentsにCopyright.astroというファイルを作成し、以下のように編集する。
```
---
const { publishedYear, owner } = Astro.props;
const today = new Date();
const currentYear = today.getFullYear().toString();
---

<style>
  p {
    margin: 0;
  }
</style>

<p>&copy; {publishedYear >= currentYear ? publishedYear : `${publishedYear}-${currentYear}`} {owner}</p>
```

以下のようにインポートすることで、Copyrightコンポーネントを使用することができる。
```
---
import Copyright from '../components/Copyright.astro';
const { pageTitle } = Astro.props;
---

<html lang="ja">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width" />
  <meta name="generator" content={Astro.generator} />
  <title>{pageTitle}</title>
</head>
<body>
<slot />
<Copyright publishedYear="2023" owner="miraiportal"/>
</body>
</html>
```
