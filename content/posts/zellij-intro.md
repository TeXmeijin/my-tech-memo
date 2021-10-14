---
title: Rust製Tmux代替のZellijに入門
date: 2021-10-14T00:00:00+09:00
tags: ['shell','zellij']
---

Macにtmuxを入れたくなったけど、もうこのご時世だしRust製の類似品が誰かによって作られているのではと思ったらあった。

## インストール

cargoで入れることができる。cargoが古いと入らないので、その場合はcargo自体を入れ直すとよい

## 基本操作

- c-p でペインモード。操作法は画面下部に出てくる。同じくc-pで編集モードに戻れることに注意
- キーバインドは~/.config/zellij/config.yamlに掻き集めて編集する。Ctrl-rが取られていたのでそこの設定を書き換えた。c-zにしてある
- c-t でタブモードらしいがまだ使っていない

## 公式Doc
https://zellij.dev/documentation/commands.html

## 記事
https://zenn.dev/gosarami/articles/4becaa18273216fec5ee