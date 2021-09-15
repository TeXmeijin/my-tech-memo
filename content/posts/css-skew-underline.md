---
title: "文字列に平行四辺形の下線を引く"
date: 2021-09-14T22:01:53+09:00
tags: [CSS]
---
ざっと以下のようなコンポーネントを実装するといい。

```jsx
import { css } from 'linaria';
import { ReactNode } from 'react';

type Props = {
  children: ReactNode;
};

const style = css`
  display: flex;
  padding: 4px 0;
  margin-left: 8px;
  position: relative;
  white-space: nowrap;
  z-index: 1;

  &:after {
    content: '';
    position: absolute;
    top: 12px;
    left: -6px;
    width: calc(100% + 6px);
    height: 12px;
    background: #fdfdfd;
    transform: skewX(-20deg);
    z-index: -1;
  }
`;

export const Underlined = ({ children }: Props) => {
  return <span className={style}>{children}</span>;
};
```

## ポイント

### skew

```css=
    transform: skewX(-20deg);
```

これで右方向に少し歪んだ図形が作れる。

### z-index

あまり好ましい書き方ではないが、自分の考案した方法ではz-indexを使うほかなかった。他にいい方法があれば知りたい。
