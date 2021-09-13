###### tags: `CSS`

# アニメーションの動きをベジエ曲線にする

ease-in-outみたいなデフォルトの動きでは満足しなくなってきたときに使える。

```css=
    animation-timing-function: cubic-bezier(0.71, 0.35, 1, -0.6);
```

こちらのサイトでシミュレーションできる

https://cubic-bezier.com/#.17,.67,.83,.67