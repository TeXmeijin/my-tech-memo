---
title: Notionに無課金でGoogle Analyticsを設定する方法
date: 2021-09-17T00:00:00+09:00
tags: [googleanalytics, notion]
---

Notion本体にGoogle Analyticsを埋め込める機能はなく、以下のようにカスタムドメインなども設定できる外部サービスでならGoogle Analyticsが設定できるものと思っていた。

- https://wraptas.com/manual#block-ee356f6cd6f543a4920292cfd5c4ce97
- https://super.so/guides/google-analytics

ところが、Google Analyticsを埋めたいだけならEmbed機能を使って実現できることを知ったのでやってみたメモ

- https://apption.co/apps/2

この機能を使うだけ。

`https://notion-ga.astrocket.vercel.app`というどこの誰が作っているのかわからないドメインなので、動作の安定を取りたいなら前述のサービスを使うのがいいが、取れたら良いな〜くらいの温度感だとこっちを使うほうが手軽でよいなと思った。

ちなみにこの方法はGA4には対応していないので、該当するプロパティを作るときはユニバーサルアナリティクスで作成しないといけないので注意。