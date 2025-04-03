---
title: Selfrionette / セルフリオネット
summary: 最小限の動作で”全身”を動かし，多様な触感を感じる
tags:
- research
date: "2024-09-27T00:00:00Z"
# Optional external URL for project (replaces project detail page).
external_link: ""
featured: true

image:
  caption: 
  focal_point: Smart

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
---

# 30秒のプロジェクト高速紹介動画
{{<youtube ZPZmRLOwJy0>}}

{{% callout note %}}
この動画を見て興味を持った方は、ぜひ下の詳細な背景をご覧ください。
{{% /callout %}}

# Selfrionette: 指先の力で全身アバターを操作する新しいVRコントローラ

## 概要
**Selfrionette**は、指先の力入力を用いてVR空間内で全身アバターを操作可能にする革新的なコントローラです。このシステムは、物理的および空間的な制約を克服し、多様で広いレンジのな触覚インタラクションを実現します。

{{<figure src="media/img/selfrionette/omosa.gif">}}
<!-- {{<figure src="media/img/selfrionette/yawara.gif">}} -->

*Selfrionetteを用いてVR環境内のオブジェクトとインタラクションする様子*

---

## 主な特徴
### 1. 指先の力入力
Selfrionetteは、**片手で7つのシングルビームロードセル**を使用して指先の力を測定します。このセンサーは球形の筐体に組み込まれており、自然な手の姿勢で操作が可能です。各ロードセルは最大**20kgの力**を検出でき、HX711チップを用いて**80Hz**でデジタル信号に変換し、マイクロコントローラで読み取っています。

#### 自由度（DoF）:
- **親指と人差し指**: 各3自由度（上下、前後、左右）。それぞれ足と手の動作に対応。
- **小指**: 1自由度（押し込み）。 ものの把持に対応

両手を使用することで、最大14自由度で全身の操作が可能です。  

{{<figure src="media/img/selfrionette/device.png" caption="デバイス外観">}}


### 2. 力から運動への変換
指先で測定した力をVR空間内のアバターの動きに変換します。この変換は**逆運動学（IK）**を用いてリアルタイムで実行されます。

#### アバター運動生成の方程式
以下の式でアバターの動きが記述されます：

{{< math >}}$$
F_v = \alpha F_l \quad \text{および} \quad m_v \ddot{x} + c \dot{x} + k(x - x_0) = F_v
$$ {{< /math >}}

- {{< math >}}$F_l${{< /math >}}: ロードセルに加えた力  
- {{< math >}}$F_v${{< /math >}}: 仮想空間内の目標点（四肢のエンドポイント）に作用する力 
- {{< math >}}$m_v${{< /math >}}: 仮想質量
- {{< math >}}$c, k${{< /math >}}: ダンパーとばねの定数
- {{< math >}}$x_0${{< /math >}}: アバターの手足の基準位置  

このモデルにより、指先の力入力に基づく直感的で応答性の高い制御を実現します。

### 3. 触感の表現
Selfrionetteでは、単なる力入力による運動生成だけでなく、触覚特性（重さ、摩擦、弾性など）を表現するための追加の力もシミュレーションに内包できます。この手法により、バーチャル物体の物理的特性をよりリアルに体感できます。

#### 触覚の追加力
触覚フィードバックを生成するための運動方程式は、以下のように表現されます：

{{< math >}}$$
m_v \ddot{x} + c \dot{x} + k(x - x_0) = F_v + f_m
$$ {{< /math >}}

- {{< math >}}$f_m${{< /math >}}: 触覚特性を表現する追加の力。

各触覚特性は以下のように実現されています：

##### 1. 重さ (Weight)
物体の重さを表現するためには、加速度と重力の効果を加えます：

{{< math >}}$$
f_m = -m \ddot{x} - m g
$$ {{< /math >}}

- {{< math >}}$m${{< /math >}}: 仮想物体の質量  
- {{< math >}}$g${{< /math >}}: 重力加速度  

##### 2. 摩擦 (Friction)
表面間の摩擦力を以下でモデル化します：

{{< math >}}$$
f_m =
\begin{cases}
-f_p, & |f_p| \leq \mu |f_n| \ (\text{静止摩擦}) \\
-\mu' |f_n| \cdot \text{dir}(f_p), & |f_p| > \mu |f_n| \ (\text{動摩擦})
\end{cases}
$$ {{< /math >}}

- {{< math >}}$f_p${{< /math >}}: 平行方向の力  
- {{< math >}}$f_n${{< /math >}}: 垂直方向の力  
- {{< math >}}$\mu, \mu'${{< /math >}}: 静止摩擦係数、動摩擦係数  

##### 3. 弾性 (Compliance)
弾性を表現するためにばねの特性を使用します：

{{< math >}}$$
f_m = -k (x - x_c)
$$ {{< /math >}}

- {{< math >}}$x_c${{< /math >}}: 接触点の位置  
- {{< math >}}$k${{< /math >}}: ばね定数

これにより、柔らかいオブジェクトを掴む感覚や弾性体に触れる感覚を再現します。

---

## 論文情報
### UIST 2024  
- **タイトル**:Selfrionette: A Fingertip Force-Input Controller for Continuous Full-Body Avatar Manipulation and Diverse Haptic Interactions
- **著者**: Takeru Hashimoto, Yutaro Hirao  
- [論文URL](https://doi.org/10.1145/3654777.3676409)

### VRSJ 2024  
- **タイトル**:セルフリオネット：指先力入力システムによる全身アバタ操作と多様な触覚インタラクションの実現
- **著者**: 平尾悠太朗、橋本健 
- [論文URL](https://conference.vrsj.org/ac2024/program/doc/3G-22.pdf)

--- 

## メディア、取材

### 電波新聞
[【「五感」を創る コンテンツ制作の今】　指先だけでアバター操作、触覚も再現　「セルフリオネット」で新たなVR体験提供へ](https://dempa-digital.com/article/607509)

### 日刊工業新聞
[指だけでアバター操作　奈良先端大とソニーCSL、コントローラー開発](https://www.nikkan.co.jp/articles/view/00733970)


### DC EXPO 2024 有野いくさん体験レポート
{{<youtube PcH3ritX4tM>}}


--- 

## Demonstrations
[Maker Faire Kyoto 2024](https://makezine.jp/event/makers-mfk2024/m0101/
)
