---
layout: ../../layouts/MarkdownPostLayout.astro
title: '【Astro】Marqueeコンポーネントを実装する'
pubDate: 2023-05-09
description: 'AstroのMarkdownページでは、リンクをクリックすると(外部リンクであるかに関わらず)同じタブで開いてしまいます。そこで、外部リンクであるかを判定し、target属性に_blankを設定することで、新しいタブで開くようにします。'
author: '玖堂いのは'
tags: ["Astro", "JavaScript"]
---

# 【Astro】外部リンクを新しいタブで開くようにする
AstroのMarkdownページでは、リンクをクリックすると(外部リンクであるかに関わらず)同じタブで開いてしまいます。  
そこで、外部リンクであるかを判定し、target属性に_blankを設定することで、新しいタブで開くようにします。

## 手順
./src/scriptsにlink.jsというファイルを作成し、以下のように編集する。
```
const isExternalLink = (link) => {
  return link.hostname !== location.hostname;
}

const links = document.getElementsByTagName('a');
for (const link of links) {
  if (isExternalLink(link)) {
    link.setAttribute('target', '_blank');
    link.setAttribute('rel', 'noopener noreferrer');
  }
}
```

以下のようなコンポーネントをMarkdownページのレイアウトとして使用している場合、  
以下のようにlink.jsをインポートすることで、外部リンクを新しいタブで開くようになる。
```
---
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
<script>
  import '../scripts/link.js';
</script>
</body>
</html>
```
