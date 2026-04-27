---
title: Haptic Avatar
summary: 身体の「質感」がアバタに応じて変わる ― ISMAR 2025発表
tags:
- research
date: "2025-09-14T00:00:00Z"

# プロジェクトの外部URL（プロジェクト詳細ページの代わりに使用）
external_link: ""
featured: true
draft: false

image:
  caption: 
  focal_point: Smart

# スライド（オプション）
#   このプロジェクトに関連するMarkdownスライドを指定
#   拡張子なしでスライドデッキのファイル名を入力
#   例：`slides = "example-slides"`は`content/slides/example-slides.md`を参照
#   スライドがない場合は`slides = ""`と設定
---

# 関連論文
本プロジェクトの成果は、ISMAR 2025 で発表されました。

> **[Move Like an Ammonite: Personalizing Force Feedback for Avatar Embodiment in Virtual Reality](https://doi.org/10.1109/ISMAR67309.2025.00098)**
> Shun Kondoh, Takeru Hashimoto, Takuji Narumi
> *2025 IEEE International Symposium on Mixed and Augmented Reality (ISMAR), pp. 899–909*

# コンセプト：力覚アバター
力覚提示技術の進歩により、物体に触れる感覚や道具を握る感覚などの力覚体験をバーチャルリアリティで表現することが可能になりました。これまで力覚技術は、人間と物理世界との相互作用のシミュレーションに広く用いられてきました。

一方で、VR技術により、自分とは異なる特徴をもつアバターを自身の身体として操作することが可能になりつつあります。アバターの外見だけでなく、固有受容感覚（内部的な身体感覚）まで変化させることで、まったく新しい身体への変容感を生み出すことができるのではないでしょうか？

私たちの目標は、人間の物理的な身体の限界を超えた体験を作り出すことです。

# 身体運動再構成 ― 「アンモナイトのように動く」
ISMAR 2025 で発表した本研究では、ユーザがアンモナイトのように人間とは大きく異なる体型のアバターに変身したときに、その身体らしい運動感覚を生み出す力覚フィードバックの設計を行いました。

実験では、人間の身体構造から徐々に離れていく **4種類のアバター** （通常の人型 → ロボット型 → 異形型 → アンモナイト型）を用意し、それぞれの身体性に応じた力覚フィードバックを設計しました。
{{<figure src="4avatars.png" id="4avatars" caption="実験で用いた4つのアバター。人間の身体構造から徐々に離れていく順に並んでいる。">}}

ユーザーの動きに戦略的なタイミングで力覚を介入させることで、外部から力を加えられているのではなく「自身の身体の物理特性が変わった」という感覚を引き起こします。私たちはこの身体感覚と運動感覚の関係の変化を **身体運動再構成（Body Movement Reconstruction）** と呼んでいます。実装には、物体の静的特性を力情報として表現するインピーダンス制御を応用しました。

さらに本論文では、各ユーザにとって最適な没入体験となるよう、ベイズ最適化により力覚パラメータを個別にチューニングする手法（Personalized Force Feedback）を提案しました。これにより、人とは異なる身体への所有感（sense of body ownership）をより強く生起させることができます。
{{<figure src="media/img/somatoshift/heavy_light.png" id="heavy_light">}}

# ハードウェア
使用している身体装着型の力提示装置については、以下のページで紹介しています。
