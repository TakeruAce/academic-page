---
title: Flying at Your Fingertips
summary: 指先の力入力で空を飛ぶ ― AHs 2026発表
tags:
- research
date: "2026-03-16T00:00:00Z"

external_link: ""
featured: true
draft: false

image:
  caption: "Fingertip force-based 4DoF locomotion (YUBI)"
  focal_point: Smart
---

# 関連論文
本プロジェクトは、Augmented Humans 2026 (AHs 2026, 沖縄) で発表されました。

> **[Flying at Your Fingertips: Input Mapping Strategies for Fingertip Force-Based 3D Locomotion](https://doi.org/10.1145/3795011.3795047)**
> Shun Kondoh, Takeru Hashimoto, Yutaro Hirao, Takuji Narumi
> *The Augmented Humans International Conference 2026 (AHs 2026), Okinawa, Japan, March 16–19, 2026*
> [📄 PDF](paper.pdf)

# 概要
3次元空間を自在に移動する操作は、VR内のロコモーション、ドローン遠隔操作、ロボット遠隔操縦など、ますます多くの応用で重要になりつつあります。一方、ジョイスティック操作は習熟に時間がかかり、全身ジェスチャでの操作は疲労や空間制約を伴います。

本研究では、指先で加える「力」を入力として用いる **Fingertip Force Input** に着目し、変位の少ない小さな動作で高次元の操作を実現する道を探ります。

# YUBI：指先力入力による 4DoF ロコモーション
両親指で加える力の方向と大きさを 3次元並進＋ヨー回転 (4DoF) の入力に変換するシステム **YUBI** を構築し、トンネル通過課題を用いた評価実験を行いました。

5種類の入力マッピング戦略を比較した結果:

- ジョイスティックの変位ベース・マッピングをそのまま力入力デバイスに移植すると、軸間の干渉によって性能が大きく低下する
- 提案する **「ハンドル状」 の冗長マッピング** ― 両親指の 6DoF 力入力を統合する設計 ― は、ゲームパッドと同等の操作精度を達成しつつ、**直感性 (intuitiveness)** と **身体性 (embodiment)** の評価でゲームパッドを上回りました

# 設計指針
力入力インタフェースは、変位ベースのコントローラの操作体系をそのまま模倣するのではなく、**冗長性** と **実世界のメタファ** を活用することで、精度・直感性・身体的負荷のバランスをうまく取ることができます。本研究の知見は、ドローン操縦インタフェースや VR ロコモーション、テレプレゼンス・ロボティクスなど、身体内蔵の制御感覚を活かす次世代ヒューマンインタフェース設計への手がかりを提供します。

{{<figure src="featured.png" id="teaser" caption="左: 指先力入力デバイス YUBI / 右: トンネル通過評価課題">}}
