# Ordo Forma Est: 関係基底の存在論と一般モデリング手法の圏論的定式化
**（Relation-Based Ontology and a Category-Theoretic Formalization of General Modeling Methodologies）**

- Date : 2026/11/16
- Version : 1.0.0

[English](README.md) | [日本語](README.ja.md)

本リポジトリは、日常的な言語理解から自然科学の理論構築、さらには概念情報モデリングに至るまで、人間が世界を分節化し把握するための「一般的なモデル化技法」の共通基盤を、**圏論（Category Theory）**によって統一的に定式化する研究プロジェクト（全5部作）のアーカイブである。

---

## 1. 研究の背景と全体構想（Research Vision）

従来の言語哲学および一般的なモデリング手法の多くは、「対象（モノ）」を基底とし、関係をその間に付随する二次的な属性とみなす「対象基底（Object-Based）」のパラダイムに立脚してきた。しかし、この枠組みでは言語の多義性による意味の崩壊や、異なる文脈（意味の場）間の構造変換、さらには「なぜ人間は有限の思考から厳密なモデルへ到達しうるのか」という根本問題を統一的に説明できなかった。

本研究プログラムでは、**「関係（スパン構造）こそが実在の主題である」**という関係基底の存在論を出発点とし、以下の5段階（**Paper 0 〜 Paper 4**）を通じて、存在論・認識論から静的・動的モデリングの数学的基礎、そして創発の哲学に至る一貫した理論体系を構築することを目的とする。

### 理論的出発点（Conceptual Foundation）
本研究プログラムは、実践的・体系的な概念モデリングの原則をまとめた『[*Conceptual Modeling Principle*](https://github.com/kae-made/conceptual-modeling-articles/blob/main/Conceptual-Modeling-Principle.pdf)』をベースとし、そこで提示された諸原理を圏論によって数学的に厳密化・基礎づけることを目的としている。

---

## 2. 論文シリーズ構成・刊行ロードマップ（Paper 0 – Paper 4）

本研究は、厳密な数理的・工学的定式化（**Paper 0〜3**）と、そこから導かれる哲学的・宇宙論的帰結（**Paper 4**）の二層構造で順次公開する。

### 【Paper 0】基礎存在論・認識論（公開済み / Published — 2026年11月16日）
* **タイトル：** 関係基底の存在論と意味の場の圏論的定式化：言語的多義性による構造崩壊とユニバースの内包としての現象
  （*Relation-Based Ontology and a Category-Theoretic Formalization of Fields of Sense: Structural Collapse via Linguistic Polysemy and Phenomena as the Intension of a Universe*）
* **DOI：** [`10.5281/zenodo.24267213`](https://doi.org/10.5281/zenodo.24267213)（英語版初版 v1.0.0：[`10.5281/zenodo.24267213`](https://doi.org/10.5281/zenodo.24267213)）
* **ファイル：**
  * 英語版： `papers/RelationBasedOntology-and-a-CategoryTheoreticFormalization-of-FieldsOfSense.pdf`
  * 日本語版： `papers/RelationBasedOntology-and-a-CategoryTheoreticFormalization-of-FieldsOfSense.jp.pdf`
* **概要：** 関係（スパン構造）こそが意味成立の本質であることを示し、言語の多義性によって意味が恒等射へ縮退・崩壊するメカニズムを定式化する。この崩壊を回避するために、世界がスキーマ圏に基づく複数の「意味の場（Fields of Sense）」と、モノ・特徴値のみを結ぶ「ブリッジ」からなる「ユニバース $\mathcal{U}$」として構成されることを示し、私たちが観測する現象（ユニバースの内包）のみから全体構造を一意に逆算することは原理的に不可能であることを証明する。

### 【Paper 1】静的モデリング論：単一の意味の場の厳密性と漸近的接近（公開済み / Published - 2026年11月19日）
* **タイトル：** 概念情報モデリングの圏論的基礎：厳密なスキーマ表現、同型性、および思考の有限性のもとでの漸近的接近
  （*Category-Theoretic Foundations of Conceptual Information Modeling: Rigorous Schema Representation, Isomorphism, and Asymptotic Refinement under Cognitive Finitude*）
* **DOI:** [`10.5281/zenodo.24359112`](https://doi.org/10.5281/zenodo.24359112) (英語版 v1.0.1: [`10.5281/zenodo.24359112`](https://doi.org/10.5281/zenodo.24359112))
* **ファイル:**
 * 英語版: `papers/CategoryTheoreticFoundationsOfCIM.pdf`
 * 日本語版: `papers/CategoryTheoreticFoundationsOfCIM.ja.pdf`
* **概要：** Paper 0 のユニバースを成立させる必要条件として、任意の意味の場のスキーマ（関手意味論の構文圏）を厳密に記述する体系を導出する。データ型、単一・複合識別子（モニック射）、参照特徴値（可換図式）、両辺にフレーズと多重度を持つスパンリレーション、関連クラス（多脚スパン）の厳密な定義を与え、モデリングとは「曖昧化」ではなく「具体的かつ厳密な構造の確定」であることを示す。さらに、同一の意味の場に対する充足的モデルはすべて圏同型に帰着すること、および有限の人間がサブクラス化や関連クラス化を通じて `0..1` や `Nullable` といった未分化な曖昧さを削ぎ落とし、真のスキーマへ漸近していくプロセスを定式化する。

### 【Paper 2】動的プロセス論：状態モデル・データフロー型アクションとモノイド圏（予定 / Planned）
* **タイトル：** 動的モデリングの圏論的基礎：状態遷移、データフロー型アクション、普遍的実行セマンティクス、および物理理論との同型性
  （*Category-Theoretic Foundations of Structural Transformation: Bridges as Fields of Sense, Boundary Conditions via Aspectual Fields of Sense, and Isomorphism with Green's Functions*）
* **DOI:** [`10.5281/zenodo.24430915`](https://doi.org/10.5281/zenodo.24430915) (英語版 v1.0.0: [`10.5281/zenodo.24430915`](https://doi.org/10.5281/zenodo.24430915))
* **ファイル:**
 * 英語版: `papers/CategoryTheoriticFondationsOfDynamicModeling.pdf`
 * 日本語版: `papers/CategoryTheoriticFondationsOfDynamicModeling.ja.pdf`
* **概要：** 外部エンティティとの接点である「境界条件（事前・事後条件）」と、Paper 1 で定義したデータ型上の「演算子（データフロー）」を導入し、状態モデル（状態ごとのアスペクト的意味の場）とアクションモデル（状態遷移）を統合する。厳密な境界条件のもとで状態と変化の全体が「モノイド圏（Monoidal Category）」を形成することを保証し、離散的な状態遷移モデルでありながら、閾値（境界条件）を介した相転移と内部パラメータ軌道によって連続的な変化を矛盾なく描写できることを示す。

### 【Paper 3】構造変換論：異なる意味の場とアスペクト間の Transformation（予定 / Planned）
* **タイトル：** 構造変換の圏論的基礎：意味の場としてのブリッジ、アスペクト的意味の場による境界条件、およびグリーン関数との同型性
  （*Category-Theoretic Foundations of Structural Transformation: Bridges as Fields of Sense, Boundary Conditions via Aspectual Fields of Sense, and Isomorphism with Green's Functions*）
* **DOI:** [`10.5281/zenodo.24431232`](https://doi.org/10.5281/zenodo.24431232) (英語版 v1.0.0: [`10.5281/zenodo.24431232`](https://doi.org/10.5281/zenodo.24431232))
* **ファイル:**
 * 英語版: `papers/CategoryTheoriticFondationsOfStructuralTransformationTheory.pdf`
 * 日本語版: `papers/CategoryTheoriticFondationsOfStructuralTransformationTheory.ja.pdf`
* **概要：** 単一の意味の場の内部（Paper 1・2）から、異なるスキーマ（意味の場）およびアスペクト間の構造変換（Transformation）へと議論を拡張する。ブリッジを介した変換が成立するための厳密な境界条件と、変換に伴う情報保存・情報損失のメカニズムを圏論的に定式化する。

### 【Paper 4】創発と宇宙論的射程：ホログラフィー原理との相関（構想中 / Conceptual）
* **仮題：** 創発としての構造変換：ホログラフィー的境界条件と意味の場の自律的生成
  （*Transformation as Emergence: Holographic Boundary Conditions and the Autonomous Genesis of Fields of Sense*）
* **概要：** Paper 0〜3 で確立された数理的・モデリング的基盤から導かれる哲学的・存在論的帰結を論じる。「ある意味の場から別の場への Transformation（構造変換）そのものが創発（Emergence）である」という視座を提示し、物理学におけるホログラフィー原理（境界上の情報への符号化）との構造的相関を考察する。境界条件が成立する場においては、既存の枠組みを超えて新たな Transformation や意味の場が自律的に立ち上がり得るという存在論的ビジョンを提示する。

---

## 3. 著者・連絡先（Author）

* **太田 寛（Hiroshi Ota）** — Knowledge & Experience / 独立研究者
* **Homepage:** https://kae-made.jp
* **Research Notes:** https://note.com
* **Ongoing Discussions & Thought Process (Membership):** https://note.com/kae_made/membership *(Sharing the ongoing development of ideas and open discussions)*
* **Research Ecosystem (Reference Toolset — COGITO):** https://github.com/kae-made/cogito *(Conceptual Modeling and Translative Generation Integrated Toolset)*
* **Contact:** master@kae-made.jp
