---
layout: ../../../layouts/MarkdownPostLayout.astro
title: '【Node.js】現在時刻を文字列として取得する'
pubDate: 2023-05-10
description: '現在時刻を文字列として取得するgetNowDate関数を実装します。JavaScriptの日時操作ライブラリ「date-fns」を使用します。TypeScriptの使用を前提としています。'
author: '玖堂いのは'
tags: ["Node.js", "TypeScript"]
---

# 【Node.js】現在時刻を文字列として取得する
現在時刻を文字列として取得するgetNowDate関数を実装します。  
JavaScriptの日時操作ライブラリ「date-fns」を使用します。  
TypeScriptの使用を前提としています。

## 手順
以下のコマンドを実行して、必要なパッケージをインストールする。
```
npm install date-fns date-fns-tz
```

以下のように編集する。
```
import * as dateFns from 'date-fns';
import { utcToZonedTime } from 'date-fns-tz';

const getNowDate = (fmt = 'yyyyMMddHHmmss', tz = 'Asia/Tokyo') => {
  const utcDate = new Date();
  const tzDate = utcToZonedTime(utcDate, tz);
  return dateFns.format(tzDate, fmt);
};

const nowDate = getNowDate();
console.log('nowDate:', nowDate);
```

現在時刻が「2023年1月1日0時0分0秒」の場合、実行すると以下のように出力される。
```
nowDate: 20230101000000
```

## 参考
- date-fns - modern JavaScript date utility library  
  https://date-fns.org/
