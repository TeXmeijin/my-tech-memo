---
title: React NativeでWebviewを使った際にユーザーのアクションでリロードさせる
date: 2021-09-15T12:03:00+09:00
tags: ["react native"]
---

`ref`を使って、onReloadといった任意のイベントハンドラで`current!.reload()`させると手動でリロードが出来ます。
普通は`pullToRefreshEnabled`を使えば対応できると思いますが、こういう方法もあるということで。

```typescript
import { View } from "../components/Themed";

import { WebView } from "react-native-webview";
import { Fab, Icon } from "native-base";
import { AntDesign } from "@expo/vector-icons";

export default function WebviewScreen() {
  const webview = useRef<WebView>(null)
  const onReload = () => {
    webview.current!.reload()
  }

  return (
    <View style={styles.container}>
      <WebView
        ref={webview}
        pullToRefreshEnabled={true}
        source={{
          uri: "https://expo.dev",
        }}
      />
      <Fab
        right={30}
        bottom={60}
        icon={
          <Icon color={"white"} as={<AntDesign name={"heart"}/>} />
        }
        onTouchEnd={onReload}
      />
    </View>
  );
}
```
