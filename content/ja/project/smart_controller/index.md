---
title: スマートコントローラー
summary: メッセンジャーアプリケーションから操作できるスマートホームコントローラー
tags:
- IoT
- other
date : 2018-03-28T12:35:52+09:00

# プロジェクトの外部URL（プロジェクト詳細ページの代わりに使用）
external_link: ""

image:
  caption: 
  focal_point: Smart

# スライド（オプション）
#   このプロジェクトに関連するMarkdownスライドを指定
#   拡張子なしでスライドデッキのファイル名を入力
#   例：`slides = "example-slides"`は`content/slides/example-slides.md`を参照
#   スライドがない場合は`slides = ""`と設定
---

# 概要
[<font color = "green">LINE</font>](https://line.me/ja/)（日本の有名なメッセンジャーアプリ）を使用して、どこからでも家電を制御できるシステムです。

# システム
詳細については以下の2つの記事（日本語）をご覧ください。

[<font color='blue'>RaspberryPiで自宅のシーリングライトに目覚まし機能をつけてみた</font>](https://qiita.com/AceZeami/items/6099d3ace9ec3e26d571)

[<font color='blue'>Bottle.pyでRaspberry PiをWebサーバにしてLINEと連携させてみた</font>](https://qiita.com/AceZeami/items/41eb122dcb0feda0eae7)

## Raspberry Piから家電を操作
赤外線受信機を使用して、RaspberryPiに家電のリモコンの信号を記憶させました。

RaspberryPiのGPIOを使用して、赤外線LEDを制御し、学習した信号を送信して家電を操作できます。
![image.png](https://qiita-image-store.s3.amazonaws.com/0/340630/ee003708-e39b-3bf7-df78-3144582400a8.png)

## LINEボット
LINE Messaging APIを使用して、ユーザーのメッセージに応答するボットを作成しました。

このボットを通じてRaspberry Piを操作できます。

## LINEからRaspberry Piを制御
- PythonのWebサーバー構築フレームワークであるBottleを使用して、RaspberryPi上にWebサーバーを構築
  - ngrokというサービスを使用して、自宅のLAN外からWebサーバーにアクセス可能
- Raspberry Pi上に、httpリクエストに応じてRaspberry Piから家電に信号を送信するWebアプリケーションを作成・実装
  - LINE Messaging APIからのWebhookで送信されるhttpリクエストを処理
- LINE Messaging APIを使用して、ユーザーのメッセージに応答するボットを作成
  - このボットを通じてRaspberry Piを制御可能

<div align="center">
<img src="https://qiita-image-store.s3.amazonaws.com/0/340630/6500d2ae-021f-10ff-bea6-a262de4dd930.gif" width="200">
</div>
