---
title: トランスカリバー / Transcalibur
summary: VRで様々な形状の物体を持っている感覚を再現する変形インターフェース
tags:
- research
date: "2019-05-27T00:00:00Z"

# プロジェクトの外部URL（プロジェクト詳細ページの代わりに使用）
external_link: ""
featured: true

image:
  caption: 
  focal_point: Smart

# スライド（オプション）
#   このプロジェクトに関連するMarkdownスライドを指定
#   拡張子なしでスライドデッキのファイル名を入力
#   例：`slides = "example-slides"`は`content/slides/example-slides.md`を参照
#   スライドがない場合は`slides = ""`と設定
---

# コンセプト
人間が知覚する把持物体の形状は、物体の慣性モーメントと見た目に影響されます。このプロジェクトでは、2つの重りの位置を動かすことで、様々なバーチャル物体を持っている感覚を再現できる手持ちVRコントローラー「トランスカリバー / Transcalibur」を開発しました。

重りの位置とデバイスの知覚される形状の関係は、データ駆動型の手法で定式化され、与えられた仮想オブジェクトの見た目に対してデバイスの重りの位置を最適化します。

# 動画
{{<youtube OiSbn6D5kwA>}}

# ハードウェア
Transcaliburは、2次元平面上で2つの重り付きモジュールを極座標で動かすことで、自身の慣性モーメントを変化させます。
{{<figure src="/img/transform.gif">}} 

# 計算論的知覚モデル
仮想環境で様々なオブジェクトのリアルな感覚を生成するためには、「重りの位置」と「人間が実際に知覚する形状」の関係を知る必要があります。
しかし、この関係は理論として確立されていませんでした。

そこで、Transcaliburの「重りの位置」に対する「実際の人間の形状知覚」のペアデータを大量に収集し、重回帰分析を行うことで、人間の形状知覚の数理モデルを定式化しました。

{{<figure src="/img/approach.png">}} 


# 受賞歴
CHI2019で**Honorable Mention**を受賞

# メディア
[<font color="blue">『ブルーサーマル』的VR超初心者入門漫画 その3＞＞「で、結局のところVRの正体ってなんですか？」</font>](https://cgworld.jp/feature/201810-thermal-03.html) CGWORLD.jp 2018.10
