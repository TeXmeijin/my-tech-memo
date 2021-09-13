---
tags: jest, javascript
---

# jestで各テストケースの前にかならずモックをクリアする

https://jestjs.io/ja/docs/configuration#clearmocks-boolean

jest.config.jsに

```json
clearMocks: true
```

を書き足す