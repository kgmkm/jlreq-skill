---
name: jlreq
description: W3C JLREQ（日本語組版処理の要件）のAIエージェント向けリファレンス。縦書き・横組の行組版、約物配置、ルビ・圏点、見出し処理、図版配置等の日本語組版ルールを網羅。
version: 1.0.0
tags: [jlreq, japanese, typesetting, css, epub, pdf, w3c, layout]
---

# JLREQ — 日本語組版処理の要件（AIエージェント向けリファレンス）

## 概要

W3C勧告 [Requirements for Japanese Text Layout（日本語組版処理の要件）](https://www.w3.org/TR/jlreq/) をAIエージェントが実務で使えるよう構造化したリファレンスです。

原文は約300ページ・図版多数のため、**章ごとにreferences/に分割**し、各ルールを簡潔にまとめています。

## 対象読者

- CSS/HTMLで日本語電子書籍を組版するAIエージェント
- EPUB/PDF生成ツールの開発者
- 日本語テキスト処理を行うプログラマー

## 参照ファイル

| ファイル | 章 | 主な内容 |
|---------|-----|---------|
| [ch01-introduction.md](references/ch01-introduction.md) | 1. 序論 | 目的・作成方針・用語 |
| [ch02-basics.md](references/ch02-basics.md) | 2. 日本語組版の基本 | 基本版面・縦組横組・柱ノンブル |
| [ch03-line-composition.md](references/ch03-line-composition.md) | 3. 行の組版処理 | 約物・禁則・ルビ・縦中横・行調整・文字クラス |
| [ch04-positioning.md](references/ch04-positioning.md) | 4. 見出し・注・図版・表・段落の配置 | 見出し処理・注注処理・図版配置・表処理 |
| [appendix-character-classes.md](references/appendix-character-classes.md) | 附属書A | 文字クラス一覧（cl-01〜cl-30） |
| [appendix-spacing.md](references/appendix-spacing.md) | 附属書B-E | 文字間の空き量・分割可否・行調整 |
| [appendix-terminology.md](references/appendix-terminology.md) | 附属書G | 用語集 |

## よく使うルール（クイックリファレンス）

### 行頭字下げ禁止（3.1.5）

行頭に「始め括弧類」が来た場合、字下げを省略する。

```css
/* CSS実装例 */
p:has(> :first-child) { text-indent: 1em; }
/* 行頭が括弧の場合はtext-indentを0にする処理が必要 */
```

### 縦中横（3.2.5）

縦組で半角アラビア数字1〜2桁を横倒しにする。

```css
.tcy { text-combine-upright: all; }
```

### ルビ（3.3）

モノルビ・グループルビ・熟語ルビの3種類。親文字に対してルビがはみ出した場合の処理ルールあり。

### 行の調整処理（3.8）

行末をそろえるための字間詰め・空けの優先順位。

## 注意事項

- 本スキルはW3C JLREQの**要約・構造化**です。原文の完全な複製ではありません
- 原文の図版は含まれません。図版が必要な場合は[原文](https://www.w3.org/TR/jlreq/)を参照
- CSS実装例は参考です。実際の実装は使用するツール（Vivliostyle、WeasyPrint等）に依存します

## ライセンス

原文: W3C Permissive Document License
