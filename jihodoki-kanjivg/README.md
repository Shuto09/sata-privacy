# 字ほどき｜加工した KanjiVG データ（CC BY-SA 3.0）

iOS アプリ「字ほどき」（個人開発 さた）に同梱している、漢字の筆画と部品のデータです。KanjiVG を加工して作りました。加工したデータも、元と同じ Creative Commons 表示-継承 3.0（CC BY-SA 3.0）で提供します。

## 元のデータ

- KanjiVG（Copyright © 2009-2026 Ulrich Apel・https://kanjivg.tagaini.net ）
- 使った版: r20260714（https://github.com/KanjiVG/kanjivg/releases/tag/r20260714 の `kanjivg-20260714.xml.gz`）
- ライセンス: CC BY-SA 3.0（https://creativecommons.org/licenses/by-sa/3.0/ ）

## ファイル

| ファイル | 中身 | バイト数 | sha256 |
|---|---|---|---|
| `kanjivg_strokes.json` | 943 字ぶんの筆画・部品の木の文・答え（下の「加工したこと」） | 1,219,796 | `6c9048b9b183facaf582f58ca02c27921d647df8a63d265e5259c08029e5faaf` |
| `kanjivg_strokes.LICENSE.txt` | 表示（作者・作品名・URL・ライセンス）・改変の明示・KanjiVG の元の注記 | 1,800 | `68c38a42e49378ffd70dc533264e0462f050773787b485b9791e636cbcd33155` |

アプリ「字ほどき」1.0.0 に入っている物と同じファイルです。

## 加工したこと

1. **字を選んだ**: KanjiVG の字のうち、アプリの面に使う常用漢字 943 字だけを残しました。
2. **形式を変えた**: XML を JSON にしました。字ごとに次の 3 つを持ちます。
   - `paths`: 筆画の SVG パス（KanjiVG の `path` の `d` の文字列を書き順のまま。座標は KanjiVG と同じ 109×109）。
   - `tree`: 部品の木を 1 行の文にした物（例「分 ＝ 八 ＋ 刀」）。KanjiVG の `kvg:element` から作りました。
   - `finds`: その字の部品として入っている常用漢字と、その筆画の番号（0 から数えた `paths` の位置）。
3. **筆画をまとめ直した**: 部品が分かれて入っている所（`kvg:part` が 1・2…）は、筆画をまとめて 1 つの部品にしました。同じ字で筆画の組も同じ物が重なった時は 1 つにしました（同じ字が別の筆画にあれば別に数えます）。
4. **部品を選んだ（`finds`）**: 部品の筆画の数が、その常用漢字の総画と同じ物だけを残しました（形が変わって画数が変わる部品は外しました）。1 画の字（一・乙）は外しました。
5. **外した情報**: 筆画の種類（`kvg:type`）・要素の ID・位置などの属性、筆画の番号の表示位置は入れていません。

## ライセンス

- `kanjivg_strokes.json` と `kanjivg_strokes.LICENSE.txt` は、CC BY-SA 3.0 で提供します（https://creativecommons.org/licenses/by-sa/3.0/ ）。表示と改変の明示は `kanjivg_strokes.LICENSE.txt` と JSON の先頭の `_license` にあります。
- App Store の使用許諾（EULA）の制限は、KanjiVG に由来するこのデータには及びません。このデータを受け取った人は、CC BY-SA 3.0 の条件の範囲で使えます。
- KanjiVG とその作者は、アプリ「字ほどき」を推奨・保証するものではありません。
- このフォルダのほかのファイル（この説明・`index.html`）は、このデータの説明のための物です。

## 連絡先

さた（個人開発）: お問い合わせフォーム https://forms.gle/JyDHurfaHYLAtERG6

---

## English

Kanji stroke and component data bundled with the iOS app "字ほどき" (Jihodoki, independent developer "sata"). It was modified from KanjiVG and is distributed under the same Creative Commons Attribution-ShareAlike 3.0 (CC BY-SA 3.0).

- Original work: KanjiVG (Copyright (c) 2009-2026 Ulrich Apel, https://kanjivg.tagaini.net), release r20260714, licensed under CC BY-SA 3.0 (https://creativecommons.org/licenses/by-sa/3.0/).
- Modifications: selected the 943 Joyo kanji used in the app; converted XML to JSON (`paths` = the SVG path `d` strings in stroke order, 109x109 coordinates as in KanjiVG; `tree` = the component tree written as one line, built from `kvg:element`; `finds` = Joyo kanji found as components and their stroke indices); merged components split into parts (`kvg:part`); removed duplicate entries with the same kanji and the same strokes; kept only components whose stroke count equals the stroke count of that Joyo kanji; excluded one-stroke kanji; removed stroke types, IDs, positions and other attributes.
- Files: `kanjivg_strokes.json` (1,219,796 bytes, sha256 `6c9048b9b183facaf582f58ca02c27921d647df8a63d265e5259c08029e5faaf`) and `kanjivg_strokes.LICENSE.txt` (1,800 bytes, sha256 `68c38a42e49378ffd70dc533264e0462f050773787b485b9791e636cbcd33155`), the same files as in the app version 1.0.0.
- The restrictions of the App Store license agreement (EULA) do not apply to this data derived from KanjiVG. Recipients may use it under the terms of CC BY-SA 3.0.
- KanjiVG and its author do not endorse or warrant the app.
- Contact: https://forms.gle/JyDHurfaHYLAtERG6
