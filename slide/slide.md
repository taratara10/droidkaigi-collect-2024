---
marp: true
theme: detekt
title: detekt カスタムルールでコーディング規約を運用する
paginate: true
---
<!-- 
class: title
 -->

# detekt カスタムルールで<br>コーディング規約を運用する

<div class="split_content">
<div class="half">

<br></br>
2024.11.8
DroidKaigi.collect { #13@Tokyo }
kabos(@chronotrg)
</div> 

<div class="half"> 

<img src="./slide_qr.png" style="padding-top: 50px;">
</div> 

</div> 

---

# About Me

<div class="split_content">
<div class="half">

- kabos(@chronotrg)
- Androidエンジニア_4年目
- Github: https://github.com/taratara10
- 好きなもの
    - Vim
    - KMP
    - WearOS
</div> 

<div class="half"> 

![height:300](./icon_2.jpg)
</div> 

</div> 

---

# 今回伝えたいこと

<div class="keynote">

detektカスタムルールの存在を広めたい！
</div>

<!-- detektでカスタムルールを作ることは、コードレビューの手間を省き、生産性を上げる強力なツールとなります -->
<!-- 詳しい実装は記事を書いているので、このLTでぜひ興味をもって今後の選択肢として考慮してもらいたい -->

---

<!-- _class: single-message -->
 # コーディングルールを<br>守るのは難しい😔
<!-- 私がlinterでカスタムルールを作ろうと思ったモチベーションはこれが発端です -->

---
# 開発が進んできたプロジェクト😀
- コード量が増えてきた
- メンバー毎に書き方が違う
- 命名を揃えたい
- これ以上多様化するとメンテが大変になりそう
<!-- よくある話 -->
<!-- コードの複雑化に関する課題が出てきます -->

---
<!-- _class: single-message -->
<h1 style="font-size:70px"> コードに統一感を持たせたい💭 </h1>

<!-- というモチベーションが湧いてきます -->

---
<!-- _class: single-message -->
# コーディング規約を作るぞ💪

<div style="text-align: center;padding-top: 80px;font-size: 40px;color: gray;">

☺＜️これで解決。平和はもたらされた
</div>

<!-- という解決策をとりがちです。ルールを作れたので満足した気に慣れますね -->

---
# 6か月後🫨

- コーディング規約作ったけど、今は忙しいから後で対応しよう
- コードレビューの時間がない...
- 動くからとりあえずマージしてヨシ！👉
<!-- 時は流れて、開発は忙しくなり、目の前のタスクをこなすことが最優先になります-->
<!-- コーディング規約は頭の片隅にありますが、最優先事項ではありません-->

---
# 1年後😨

- 暫定対応のコードがコピペされて蔓延
- コーディング規約...そんなのもあったね...
- カオス！

---
<!-- _class: single-message -->
# こんなはずでは...🫠

---

# コーディング規約の運用を阻害する要因
- ルールが厳密に明文化されていない
- 長い文章を読んでも内容が理解しにくいし、覚えられない
- メンバーが変化して運用されなくなった
- etc...

<!-- ふわふわルールだとRevで指摘しても認識があわず、Revコストが大きくなる -->
<!-- メンバーの努力によって運用することは非常に難しく、継続させるのは困難です -->

---
<!-- _class: single-message -->
# 重要で大変なことは<br>自動化しよう✨
<!-- エンジニアの思考で-->

---
<!-- _class: single-message -->
<h1 style="font-size:68px">CIと連携しやすくて<br>
プロジェクトの独自ルールを作れる<br>Linterさえあれば...🤔
</h1>
 
---
<!-- _class: code -->
![bg fit](./detekt_logo.png)

---

# detekt

- Kotlin向けの静的コード解析ツール
- DroidKaigi/conference-app-2024でも採用
- 標準ルールセットが豊富で柔軟にカスタマイズできる

<!-- 標準ルールが豊富という印象が多いのではないでしょうか -->
---

![bg fit](./detekt_heigh_light.png)

---

<!-- _class: single-message -->
# Easy to Extend !
<div style="text-align: center;">手軽にカスタムルールがつくれるよ！</div>

<!-- カスタムしやすいというのがdetektの大きなメリットがあります -->
---
# カスタムルールを作ってみる

<h2 style="color: #FF5555;font-weight: bold;">「Repositoryが公開するメソッドはsuspendであること」</div>

<!-- ここからはざっくりとしたカスタムルールのイメージを説明します -->
---
<!-- _class: code -->
![bg fit vertical](./gradle_1.png)

---
<!-- _class: code -->
#### Repositoryが公開するメソッドはsuspendであること
![](./repository_visit.png)
<!-- visitXXXという解析のためのinterfaceが提供されます -->

---
<!-- _class: code -->
#### Repositoryが公開するメソッドはsuspendであること
![](./repository_0.png)

---
<!-- _class: code -->
#### Repositoryが公開するメソッドはsuspendであること
![](./repository_1.png)

---
<!-- _class: code -->
#### Repositoryが公開するメソッドはsuspendであること
![](./repository_2.png)

---
<!-- _class: code -->
#### Repositoryが公開するメソッドはsuspendであること
![](./repository_3.png)

---
<!-- _class: code -->
#### Repositoryが公開するメソッドはsuspendであること

<!-- ![](./repository_3.png) -->
<img src="./repository_4.png" style="height: 100%;">

---
<!-- _class: single-message -->
# 直感的に書けそう！🚀

---

# 詳しい実装方法はこちら
<div style="padding-left: 20px;">

https://zenn.dev/kabos/articles/d31c27cb473fba

![](./detekt_custome_rule_article.png) ![](./article_qr.png)

</div>

---
<!-- _class: single-message -->
# detektカスタムルールで<br>生産性を爆上げしよう🚀

---
<!-- _class: single-message -->
<h1 style="font-size:70px"> ご清聴ありがとうございました！
