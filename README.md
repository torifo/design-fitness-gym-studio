# fitness-gym / studio — ATELIER FIT

架空のフィットネス × コワーキングブランド **ATELIER FIT** のトップページ実装。
`fitness-gym` シリーズの "studio" ペルソナ担当リポジトリ。

> **コンセプト**
> 「ジムにラウンジが付いている」のではなく、
> **「コワーキングにジムが内蔵されている」**。
> 働く・鍛える・休むを 1 フロアで往復する、東京の旗艦スタジオ。

---

## Live

- **Production:** <https://design.fitness-gym-studio.riumu.net/>（HTTPS 強制 ON、Let's Encrypt 証明書 approved）
- **Repo:** <https://github.com/torifo/design-fitness-gym-studio>
- ホスティング: GitHub Pages（CNAME / .nojekyll 同梱）

---

## ファイル構成

```text
.
├── index.html             メイン実装（hero / benefits / floor / facilities / day / plans / access）
├── spec.md                仕様書（Approved）
├── README.md              本ファイル
├── DESIGN_LEARNINGS.md    実装知見
├── CNAME                  GitHub Pages 用カスタムドメイン
└── .nojekyll              Jekyll 無効化
```

---

## デザイン要点

| 項目 | 採用 |
|------|------|
| 配色 | サンドベージュ `#f4efe6` + コンクリグレー + 苔グリーン `#4f6b4a` + 墨黒 `#1a1a1a` + テラコッタ `#c4533a` |
| 書体 | Inter Tight（見出し）/ Inter（本文）/ Noto Sans JP（和文）/ JetBrains Mono（時刻）|
| 中核 | SVG フロアマップ（Work / Train / Recover の 3 ゾーン）+ 1 日タイムライン |
| CTA | "Book a Tour" 固定（"Join Now" は使わない・会員制） |
| ブレイクポイント | 1024px（2 カラム → 1 カラム）/ 780px（補助）/ 640px（タイムライン圧縮）|

---

## 実装上の遵守事項

- 本文は font-weight 400 以上（Light は飾り見出しのみ／モバイルは 400 昇格）
- 時刻 `08:00` 等は `tabular-nums` + `JetBrains Mono`
- 「ATELIER FIT」「Work × Train × Repeat.」「価格」「CTA」は `white-space: nowrap`
- 見出し `text-wrap: balance` / 本文 `text-wrap: pretty`
- `focus-visible` はテラコッタの outline
- `prefers-reduced-motion` でアニメーション抑制
- 全画像 Unsplash 外部 URL + `loading="lazy"` + 意味のある alt
- 「24h アクセス + 会員面談制」を矛盾なく説明する文言を明記

---

## License / Disclaimer

- 架空ブランド。実在の事業者・施設とは一切無関係です。
- 写真はすべて Unsplash の外部リンク。クレジット表記は Unsplash 利用規約に準拠。
- デザイン学習・ポートフォリオ目的の制作物です。


## Install as a skill / スキルとして導入

This repo ships a cross-agent **`SKILL.md`** (open standard) usable by both Claude Code and Codex CLI as a design-reference skill. Link the repo into the agent's skills directory:

このリポジトリは Claude Code / Codex CLI 共通の **`SKILL.md`**（オープン標準）を同梱し、デザイン参照スキルとして使えます。

```bash
# Claude Code
ln -s "$(pwd)" ~/.claude/skills/design-fitness-gym-studio
# Codex CLI
ln -s "$(pwd)" ~/.codex/skills/design-fitness-gym-studio
```

Restart the agent; it is matched automatically by the skill's `description` (skill name: `design-fitness-gym-studio`). / エージェント再起動後、`description` に基づき自動マッチします。
