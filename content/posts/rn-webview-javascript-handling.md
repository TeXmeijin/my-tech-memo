---
title: React Native Webviewでページ内のJavaScriptイベントをアプリ側でハンドリングする
date: 2021-09-16T00:00:00+09:00
tags: ['react native']
---

こちらに書いてあるまんまなんだけど。

https://github.com/react-native-webview/react-native-webview/blob/master/docs/Guide.md#communicating-between-js-and-native

## React Native側

```typescript
onMessage={(event) => {
    alert(event.nativeEvent.data);
}}
```

## Webview側

```typescript
// @ts-ignore
window.ReactNativeWebView.postMessage({
    status: 'completed'
})
```

---

`window`に`ReactNativeWebView`というのが生えるのでそれを使って通信するとハンドリングできる。iframeみたい。