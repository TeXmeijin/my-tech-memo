---
title: "固定ヘッダーを利用しているときに、scrollIntoViewでスクロールした先が隠れてしまう問題を解消する"
date: 2021-09-14T22:03:50+09:00
tags: [CSS]
---

```css
  scroll-margin-top: 70px;
```

これで解決できます。

`scroll into view fixed header`でググりました。

https://www.bram.us/2020/03/01/prevent-content-from-being-hidden-underneath-a-fixed-header-by-using-scroll-margin-top/

https://stackoverflow.com/questions/13614112/using-scrollintoview-with-a-fixed-position-header

---

と思いきや、2021年9月現在Safariで動作しないので、以下の記事のように力技で対応する必要がある。辛い。

https://zenn.dev/catnose99/articles/75d3c69bf71bad
