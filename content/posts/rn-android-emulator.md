---
title: React Native開発用Android Emulatorセットアップ
date: 2021-09-17T00:00:00+09:00
tags: [reactnative]
---

メモ風に書いておく。

https://docs.expo.dev/workflow/android-studio-emulator/

これを見ながら環境のセットアップをする。ゴールとしては`adb`コマンドがローカルで動いていたらOK。

そのままAndroid Studioを起動して、AVD Managerから任意の端末を再生ボタンで起動する。

起動が終わったら、`expo start`しているターミナルにて`a`を押せばAndroidエミュレータ内でアプリが起動する。

---

アプリ内に最初は画像やファイルがまったくないが、

- 画像はカメラアプリから撮影すると入る
- ファイルは、自分のPCからドラッグアンドドロップするとDownloadsフォルダに入る

ので、これでテストができる。