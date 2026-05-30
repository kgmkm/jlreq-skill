---
name: jlreq-skill
description: W3C JLREQ（日本語組版処理の要件）のAIエージェント向けリファレンス。縦書き・横組の行組版、約物配置、ルビ・圏点、見出し処理、図版配置等の日本語組版ルールを網羅。章ごとにreferencesに分割し、必要な章だけ読める。
version: 1.0.1
tags: [jlreq, japanese, typesetting, css, epub, pdf, w3c, layout]
---

# JLREQ — 日本語組版処理の要件（AIエージェント向けリファレンス）

## 概要

W3C JLREQ（日本語組版処理の要件）をAIエージェントが実務で使えるよう構造化したリファレンスです。原文は約300ページ・図版多数のため、**章ごとにreferences/に分割**し、各ルールを簡潔にまとめています。

**原文**: https://www.w3.org/TR/jlreq/

## いつこのスキルを読み込むか

- 日本語の縦書き・横組レイアウトを実装するとき
- CSS `writing-mode`, `text-combine-upright`, `ruby-position` 等の組版プロパティを使うとき
- EPUB/PDFで日本語組版ルール（行頭禁則・縦中横・ルビ処理等）を適用するとき
- 約物（句読点・括弧類）の配置ルールに迷ったとき
- 文字間の空き量・行調整の優先順位を確認したいとき

## 参照ファイル（章単位で読める）

| ファイル | 章 | 主な内容 | 読み込むタイミング |
|---------|-----|---------|-------------------|
| [ch01-introduction.md](references/ch01-introduction.md) | 1. 序論 | 目的・作成方針・用語 | 初回参照時 |
| [ch02-basics.md](references/ch02-basics.md) | 2. 日本語組版の基本 | 基本版面・縦組横組・柱ノンブル | ページレイアウト設計時 |
| [ch03-line-composition.md](references/ch03-line-composition.md) | 3. 行の組版処理 | 約物・禁則・ルビ・縦中横・行調整・文字クラス | **最もよく使う。行組版で迷ったらまずこれ** |
| [ch04-positioning.md](references/ch04-positioning.md) | 4. 見出し・注・図版・表・段落の配置 | 見出し処理・注理・注処理・図版配置・表処理 | 見出し・図版・表の配置時 |
| [appendix-character-classes.md](references/appendix-character-classes.md) | 附属書A | 文字クラス一覧（cl-01〜cl-30） | 特定文字の振る舞いを確認するとき |
| [appendix-spacing.md](references/appendix-spacing.md) | 附属書B-E | 文字間の空き量・分割可否・行調整 | 行調整の詰め・空けを実装するとき |
| [appendix-terminology.md](references/appendix-terminology.md) | 附属書G | 用語集 | 用語の意味が不明なとき |

## よく使うルール（クイックリファレンス）

### 行頭字下げ禁止（§3.1.5）

行頭に「始め括弧類（「『（【等）」が来た場合、字下げを省略する。

```css
/* 行頭が括弧の場合、text-indentを0にする */
/* 実装方法はツール依存。jlreq_postprocess.pyではno-indentクラスを付与 */
```

### 縦中横（§3.2.5）

縦組で半角アラビア数字1〜2桁を横倒しにする。

```css
.tcy { text-combine-upright: all; }
```

### ルビ（§3.3）

モノルビ・グループルビ・熟語ルビの3種類。親文字に対してルビがはみ出した場合の処理ルールあり。詳細は ch03-line-composition.md §3.3 を参照。

### 行の調整処理（§3.8）

行末をそろえるための字間詰め・空けの優先順位。詳細は ch03-line-composition.md §3.8 を参照。

### 文字クラス（§3.9 + 附属書A）

日本語組版の文字を30クラス（cl-01〜cl-30）に分類。各クラスの振る舞い（空き量・禁則・分割可否）を規定。詳細は appendix-character-classes.md を参照。

## 注意事項

- 本スキルはW3C JLREQの**要約・構造化**です。原文の完全な複製ではありません
- 原文の図版は含まれません。図版が必要な場合は[原文](https://www.w3.org/TR/jlreq/)を参照
- CSS実装例は参考です。実際の実装は使用するツール（Vivliostyle、WeasyPrint等）に依存します

## ライセンス

- **本スキル（構造化・要約）**: MIT License
- **原文（W3C JLREQ）**: W3C Permissive Document License
