# 附属書G: 用語集 — 日本語組版用語

出典: W3C JLREQ (Requirements for Japanese Text Layout)
https://www.w3.org/TR/jlreq/

本文書で使用する主要な用語を定義する。

---

## 版面・ページ関連

### 基本版面 (kihon-hanmen)
ページ上の文字や図版を配置する基本領域。版面のサイズは、行長×行数×行送りで決まる。

### 版面 (hanmen)
基本版面と同じ。文字や図版を配置する実際の領域。

### 行長 (line length / gyōchō)
一行に配置する文字の長さ。基本版面の幅方向の寸法。縦組みでは版面の高さ、横組みでは版面の幅。

### 行数 (number of lines / gyōsū)
基本版面に配置する行の数。

### 行送り (line pitch / gyōokuri)
隣接する行の基準線間の距離。文字サイズにアキを加えた値。

### 行間 (line gap / gyōkan)
行送りから文字サイズを引いた値。行と行の間のアキ部分。

### ノド (nodo / gutter)
見開きページの内側の余白。製本で綴じる側。

### 小口 (koguchi / fore-edge)
見開きページの外側の余白。ノドの反対側。

### 天 (ten / top margin)
ページ上部の余白。

### 地 (chi / bottom margin)
ページ下部の余白。

### 柱 (running head / hashira)
ページ上部または下部に配置する書名・章名・節名などの見出し文字列。

### ノンブル (page number / nonburu)
ページ番号。通常は小口側に配置。

---

## 方向・配置関連

### 字詰め方向 (jizume方向 / inline direction)
一行の文字を配置する方向。縦組みでは上から下、横組みでは左から右。

### 行送り方向 (gyōokuri方向 / block direction)
行を積み重ねる方向。縦組みでは右から左、横組みでは上から下。

### 縦組み (tate-gumi / vertical setting)
字詰め方向が上から下、行送り方向が右から左の組版方式。

### 横組み (yoko-gumi / horizontal setting)
字詰め方向が左から右、行送り方向が上から下の組版方式。

### 縦中横 (tate-chu-yoko / inline horizontal in vertical)
縦組みの中で一部の文字（主に数字や欧字）を横向きに配置する技法。2文字分を1行内に横向きで収める。

### 横中縦 (yoko-chū-tate / inline vertical in horizontal)
横組みの中で一部の文字を縦向きに配置する技法。

---

## 文字・約物関連

### 約物 (yakumono / punctuation marks)
句読点・括弧類・記号など、活字の大きさが規則的な記号類の総称。附属書Aのcl-01〜cl-07が該当。

### 和字 (waji / Japanese character)
日本語組版で使う文字。漢字・ひらがな・カタカナなど。

### 和字間隔 (waji-kankaku / ideographic space)
和文組版で使う基本的な文字間隔。全角幅（1em）。

### 欧字 (ōji / Latin letter)
ラテンアルファベット。

### 欧文間隔 (ōbun-kankaku / Western character spacing)
欧文組版で使う文字間隔。和字間隔より狭い。

### 和欧文間 (wa-ōbun-kan / space between Japanese and Western text)
和文文字と欧文文字の間に挿入するアキ。通常は1/4em程度。

### ぶら下げ (burasage / hanging punctuation)
句読点を版面の外にはみ出させて配置する技法。行末揃えの改善に有効。

---

## ルビ・圏点・割注関連

### ルビ (ruby)
親文字（本文文字）の脇に付ける小さな文字。読み方や意味を示す。縦組みでは右側、横組みでは上側に配置。

### 傍注 (bōchū / side notes)
本文の脇に配置する注釈。ルビと異なり独立した注釈テキスト。

### 圏点 (kenten / emphasis dots)
文字の脇に付ける点（﹅・●等）で、強調を示す。縦組みでは文字の右側、横組みでは下側に配置。

### 割注 (warichu / split notes)
本文中の注釈を、2行に分けて1文字幅に収める技法。主に縦組みで使用。

---

## 処理・調整関連

### 禁則処理 (kinsoku shori / line breaking rules)
行頭・行末に配置してはいけない文字の処理。附属書Aの各クラスの振る舞いに基づく。

### 行調整 (gyōchōsei / line adjustment)
行末を揃えるための処理。文字間のアキを詰めたり空けたりする。

### ジャスティフィケーション (justification)
行末を揃える処理全体。行調整とも。

### 字幅 (jihaba / character width)
文字の幅。全角（1em）、半角（1/2em）、プロポーショナルなど。

### ベタ組み (beta-gumi / no spacing)
文字間に一切のアキを入れない組み方。

### アキ (aki / space)
文字間の空白部分。詰め・空けの調整対象。

---

## その他の重要用語

### 原稿 (genkō / manuscript)
組版の元となるテキスト。

### 校正 (kōsei / proofreading)
組版結果を確認・修正する作業。

### 活字 (katsuji / type)
金属活字時代の文字ブロック。デジタル時代でも文字サイズの単位として使用。

### 紙面 (shimen / paper surface)
用紙の印刷面。版面を配置する対象。

### 見開き (mihiraki / spread)
左右の2ページを並べた状態。

### 丁 (chō / signature/leaf)
本の1葉（見開きの2ページ分）。
