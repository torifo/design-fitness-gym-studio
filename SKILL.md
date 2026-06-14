---
name: design-fitness-gym-studio
description: "fitness gym / studio landing-page design study — 'studio' theme/persona (pure HTML/CSS/JS, no build). Use when designing a 'studio'-style fitness gym / studio site aesthetic. コンセプト. fitness gym / studioの「studio」テーマLPのデザイン参照スキル。"
---

# design-fitness-gym-studio

A landing-page **design study** for a fictional **studio**-theme fitness gym / studio (pure HTML + CSS + vanilla JS, no build, GitHub-Pages ready). Use this as a **style / design-system reference** when building a similar aesthetic.

架空の「studio」テーマのfitness gym / studio LP デザイン研究。同種の世界観を作るときの**スタイル／デザインシステム参照**として使う。

## When to use / 使いどころ
- **EN:** designing a 'studio'-style fitness gym / studio site — match its palette, typography and layout discipline.
- **JP:** 「studio」系のfitness gym / studioサイトを設計するとき。配色・タイポ・レイアウト規律を流用。

## Bundled assets / 同梱アセット
This skill folder is the reference implementation — start from these files:
- `index.html` — full page markup
- `style.css` — design tokens (CSS custom properties) + layout
- `script.js` — vanilla JS (if present)
- `README.md` — full bilingual doc, brand context and series links

## Design reference / デザイン参照
_Lifted from the repo README — see README.md for the complete, bilingual version._

### デザイン要点
| 項目 | 採用 |
|------|------|
| 配色 | サンドベージュ `#f4efe6` + コンクリグレー + 苔グリーン `#4f6b4a` + 墨黒 `#1a1a1a` + テラコッタ `#c4533a` |
| 書体 | Inter Tight（見出し）/ Inter（本文）/ Noto Sans JP（和文）/ JetBrains Mono（時刻）|
| 中核 | SVG フロアマップ（Work / Train / Recover の 3 ゾーン）+ 1 日タイムライン |
| CTA | "Book a Tour" 固定（"Join Now" は使わない・会員制） |
| ブレイクポイント | 1024px（2 カラム → 1 カラム）/ 780px（補助）/ 640px（タイムライン圧縮）|

---

## How to apply / 適用方法
1. Reuse `style.css` custom properties (color / type / spacing tokens) as the design-system base.
2. Copy `index.html` layout as the starting structure, then swap brand name and content.
3. Keep the palette, font pairing and layout discipline described above.

---
> The brand is fictional (design study) — replace all brand/content. Full context: see **`README.md`**.
