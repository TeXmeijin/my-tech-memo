---
title: "CSSアニメーションの動きをベジエ曲線にする"
date: 2021-09-14T21:51:18+09:00
tags: [CSS]
---

ease-in-outみたいなデフォルトの動きでは満足しなくなってきたときに使える。

```css=
    animation-timing-function: cubic-bezier(0.71, 0.35, 1, -0.6);
```

こちらのサイトでシミュレーションできる

https://cubic-bezier.com/#.17,.67,.83,.67
