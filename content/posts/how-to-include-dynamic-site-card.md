---
title: どうやってZennは本文中のURLを動的にOGP画像つきのCardにしているのか
date: 2021-09-16T10:03:00+09:00
tags: [frontend, javascript]
---

Zennの記事では、本文中のURLがカードとして表示される。

https://zenn.dev/meijin/articles/linaria-class-name-config

これは初期ロード時はPlaceholderが掛かっているため、フロントエンドで動的に表示できていると推測できる。

この仕組みを少しだけ調査したのでメモ。

Zenn本体のソースは公開されていないはずだが、CLIのソースは公開されているため、ほぼ同様の技術とみなして調査できる。

markdownをHTMLにパースするときに、URLを見つけたらiframeに変換している。

https://github.dev/zenn-dev/zenn-editor/blob/43d8da8b77456c72f3b820f6e5df4ccf69d14ea9/packages/zenn-markdown-html/src/utils/md-linkify-to-card.ts

```typescript
    // 以下の2つをどちらも満たした場合にリンク化
    // 1. パラグラフ先頭 もしくは リンクの前が br
    // 2. パラグラフの末尾 もしくは リンクの後が br

    const shouldConvertToCard =
      (isStartOfLine || isPrevBr) && (isEndOfLine || isNextBr);

    if (!shouldConvertToCard) {
      newTokens.push(token); // 変換は行わずに出力結果に含める
      return;
    }

    // 埋め込み用のHTMLを生成
    const embedToken = new Token('html_inline', '', 0);
    if (isTweetUrl(url)) {
      embedToken.content = generateTweetHtml(url);
    } else if (isYoutubeUrl(url)) {
      embedToken.content = generateYoutubeHtmlFromUrl(url);
    } else {
      embedToken.content = generateCardHtml(url);
    }
    // a要素自体はカードにより不要になるため非表示に
    linkOpenToken.attrJoin('style', 'display: none');
```

```typescript
export function generateCardHtml(url: string) {
  return `<div class="embed-zenn-link"><iframe src="https://card.zenn.dev/?url=${encodeURIComponent(
    url
  )}" frameborder="0" scrolling="no" loading="lazy"></iframe></div>`;
}
```

`card.zenn.dev`はURLを受け取って、カードを描画する専用のサイトらしい。iframe埋め込み用で、VercelにホスティングされているらしいことまではHeaderから推測できる。

![スクリーンショット 2021-09-16 10 48 42](https://user-images.githubusercontent.com/7464929/133536190-b9af9145-42ee-4c35-b1ff-471ec02c8bee.png)

つまるところ、ざっくりいえば以下の手順でこの実装が実現できるはず。

- iframe用の専用のサイトを立ち上げて公開、iframe埋め込みは許可する（https://developer.mozilla.org/ja/docs/Web/HTTP/Headers/X-Frame-Options）
- markdownのパーサーでURLのパースをカードに切り替える
