---
title: "jestで各テストケースの前にかならずモックをクリアする"
date: 2021-09-14T22:08:15+09:00
tags: [jest, javascript]
---

https://jestjs.io/ja/docs/configuration#clearmocks-boolean

jest.config.jsに

```json
clearMocks: true
```

を書き足す

