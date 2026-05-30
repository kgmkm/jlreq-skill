# jlreq-skill

W3C [Requirements for Japanese Text Layout（日本語組版処理の要件）](https://www.w3.org/TR/jlreq/) をAIエージェントが実務で使えるよう構造化したリファレンスです。

原文は約300ページ・図版多数。本スキルは **章ごとにreferences/に分割** し、各ルールを簡潔にまとめています。

## 特徴

- **章単位で読める** — 必要な章だけ `skill_view` で読み込める。全文一括読込不要
- **CSS対応表付き** — 各ルールに対応するCSSプロパティを明記
- **文字クラス一覧** — JLREQの30クラス（cl-01〜cl-30）を一覧化
- **用語集** — 日本語組版の専門用語を40語以上収録

## 対象読者

- CSS/HTMLで日本語電子書籍を組版するAIエージェント（Hermes Agent等）
- EPUB/PDF生成ツールの開発者
- 日本語テキスト処理を行うプログラマー
- Vivliostyle CLI・WeasyPrint等の組版エンジン利用者

## ファイル構成

```
jlreq-skill/
├── SKILL.md                            ← AIエージェント向け（自動読み込み）
├── README.md                           ← このファイル（人間向け）
└── references/                         ← 章ごとのリファレンス
    ├── ch01-introduction.md            ← 第1章 序論（目的・用語）
    ├── ch02-basics.md                  ← 第2章 日本語組版の基本（版面・縦横組・柱ノンブル）
    ├── ch03-line-composition.md        ← 第3章 行の組版処理（約物・禁則・ルビ・縦中横・行調整）
    ├── ch04-positioning.md             ← 第4章 見出し・注・図版・表・段落の配置
    ├── appendix-character-classes.md   ← 附属書A 文字クラス一覧（cl-01〜cl-30）
    ├── appendix-spacing.md             ← 附属書B-E 文字間の空き量・分割可否・行調整
    └── appendix-terminology.md         ← 附属書G 用語集
```

## よく使うルール

### 行頭字下げ禁止（§3.1.5）

行頭に「始め括弧類（「『（等）」が来た場合、字下げを省略する。

### 縦中横（§3.2.5）

縦組で半角アラビア数字1〜2桁を横倒しにする。CSS: `text-combine-upright: all`

### ルビ（§3.3）

モノルビ・グループルビ・熟語ルビの3種類。親文字に対してルビがはみ出した場合の処理ルールがある。

### 行の調整処理（§3.8）

行末をそろえるための字間詰め・空けの優先順位を定義。

## 導入

Hermes Agentにスキルとしてインストール:

```
以下のGitHubリポジトリをスキルとしてインストールしてください：
https://github.com/kgmkm/jlreq-skill
```

## 関連スキル

- [novel2epub-jp](https://github.com/kgmkm/novel2epub-jp) — Markdown小説 → A6縦書きPDF/EPUB変換。JLREQルールを実装した組版ツール
- [novel2hermes_jp](https://github.com/kgmkm/novel2hermes_jp) — 日本語小説執筆スキル（企画・執筆・推敲）

## 使い方（AIエージェント向け）

```python
# 縦書きの行頭字下げルールを確認したい場合
skill_view(name='jlreq-skill', file_path='references/ch03-line-composition.md')

# 文字クラスの振る舞いを確認したい場合
skill_view(name='jlreq-skill', file_path='references/appendix-character-classes.md')

# 用語の意味を確認したい場合
skill_view(name='jlreq-skill', file_path='references/appendix-terminology.md')
```

## ライセンス

- **本スキル（構造化・要約）**: MIT License
- **原文（W3C JLREQ）**: [W3C Permissive Document License](https://www.w3.org/copyright/document-license-2023/)
