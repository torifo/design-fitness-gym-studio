# ATELIER FIT — fitness-gym/studio Spec

**Status:** Approved
**Author:** torifo
**Created:** 2026-05-24
**Updated:** 2026-05-24

---

## 1. Overview

### Problem Statement
リモートワーク層は「集中できる仕事場」と「鍛える場所」を別々に確保しており、移動と切り替えにコストがかかる。既存のフィットネスジムは「運動施設にラウンジが付属する」構成で、終日滞在する仕事の動線は想定されていない。逆にコワーキングは運動・シャワー・着替えの体験が薄い。「働く・鍛える・休む」を1フロア内で行き来する設計、つまり studio（work studio × training studio）の世界観をWebで表現した例は国内に少ない。

### Goal
架空ブランド「ATELIER FIT」を、コワーキングにジムが内蔵された会員制フレキシブル拠点として実装する。北欧モダン（コンクリ+木+植物+自然光、アースカラー）のトーンで、「ジムにラウンジが付いている」ではなく「コワーキングにジムが内蔵されている」ことが一目で伝わるトップページを作る。WeWork の機能カード／Life Time Work の "Work + Fitness 同時提供" の動線を、Equinox 系の上質な施設写真トーンと統合する。

### Non-Goals
- 入会フォーム / 決済 / 個人ダッシュボード
- パーソナルトレーニング予約システム
- 会議室予約 / デスク空席リアルタイム表示
- 多言語対応 / ブログ / イベント一覧
- 多店舗ロケーション切替（単一旗艦店として描く）

---

## 2. User Stories

| ID | Persona | Want to | So that |
|----|---------|---------|---------|
| US-01 | 30代リモートワーカー（IT） | 朝の会議の前後に汗をかきたい | 通勤せずに集中とリフレッシュを切り替えられる |
| US-02 | 20代後半クリエイター | デスク・Wi-Fi・電源と、シャワーが同じフロアにある場所を探したい | 1日の作業効率を最大化できる |
| US-03 | 出張中のフリーランス | ドロップインで作業しつつ運動もしたい | ホテル＋ジム＋カフェの分散を1拠点にまとめられる |
| US-04 | 40代スタートアップCEO | 商談前にシャワーを浴び、着替え、ラウンジに戻れる動線を確認したい | 1日の予定を本拠地として組み立てられる |

---

## 3. Functional Requirements

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-01 | アースカラー（コンクリ・木・苔・サンドベージュ）の配色トークン化 | P0 |
| FR-02 | ヒーローはコピー左 / 縦長施設写真右 の2カラム。コピーは「Work. Train. Repeat.」系の短い英文＋日本語サブ | P0 |
| FR-03 | フロアマップ（SVGまたは平面図風セクション）。Work / Train / Recover の3ゾーンを色で区別 | P0 |
| FR-04 | 設備カード 6 件（Desk / Meeting Pod / Gym Floor / Studio / Shower & Locker / Cafe & Bar）。各カードに1枚の写真比率・短文 | P0 |
| FR-05 | "Work × Train" を訴えるベネフィット帯（3項目：Wi-Fi 1Gbps / 24h Shower / Espresso Bar） | P0 |
| FR-06 | 1日の使い方（タイムライン）セクション。08:00 朝筋トレ → 10:00 会議 → 13:00 昼ラン → 16:00 集中作業 → 19:00 サウナ の流れを縦に並べる | P1 |
| FR-07 | 料金プラン 3 段（Drop-in / Flex / Resident）をカードで横並び、Flex を強調 | P0 |
| FR-08 | アクセス・営業時間・会員制であることの明記（24h アクセス可、入会面談制）| P1 |
| FR-09 | 1024px 以下で 2 カラム→1 カラム、フロアマップは縦積み | P0 |
| FR-10 | スクロール時のヘッダーは透過→白に変化（最小限の演出）| P1 |

---

## 4. Key Design Decisions

| Decision | Chosen | Rationale | Rejected |
|----------|--------|-----------|----------|
| 配色 | サンドベージュ + コンクリグレー + 苔グリーン + 墨黒 | 北欧モダン・素材感のあるアースカラー。コンクリと木と植物のリアリティ | ネオン青系（24hジム的）/ ピンク（女性向け感） |
| 書体（欧文）| Inter Tight（見出し）/ Inter（本文） | 機能的でモダン。WeWork系の中立感を踏襲しつつ Equinox 的な硬さも出る | Playfair（装飾的すぎる）/ Bebas（スポーティすぎる）|
| 書体（和文）| Noto Sans JP（300/500/700） | 欧文と並べて破綻しない。本文の300/500運用で軽さを出す | 明朝（書店的になる）|
| 写真トーン | 自然光・低彩度・コンクリ+木+グリーンが画角に入るもの | 「働く場 × 鍛える場」が同一空間にあることを1枚で伝える | スタジオ撮影風・ジム機器のクローズアップ |
| 装飾 | 1px 罫線・大きな余白・微細なノイズテクスチャ | 素材感を演出。装飾より素材で語る | グラデーション・ドロップシャドウ・絵文字アイコン |
| 動線表現 | 横長タイムライン＋フロアマップの2軸 | "ジムにも仕事場がある" ではなく "1日の使い方" として時間軸で見せる | 単なる施設一覧 |
| 強調コピー | 英語短文 + 日本語の補足 1 行 | コワーキングの国際感とジムの身体性を同居させる | 全文日本語 / 全文英語 |
| CTA | "Book a Tour"（見学予約）固定。"Join Now" は使わない | 会員制プロ拠点としての敷居の高さを演出 | 即入会導線 |

---

## 5. Design System

```css
/* Color tokens */
--bg:        #f4efe6;  /* sand / paper */
--surface:   #ffffff;
--ink:       #1a1a1a;  /* 墨黒 */
--ink-2:     #5a5650;  /* 本文の柔らかい墨 */
--muted:     #8a857c;
--line:      #d8d2c4;  /* 1px 罫線 */
--concrete:  #c8c2b6;  /* コンクリ */
--wood:      #8b6a48;  /* 木材 */
--moss:      #4f6b4a;  /* 苔・植物（差し色）*/
--accent:    #c4533a;  /* 銅・テラコッタ（ボタン強調）*/

/* Typography */
--font-en:   'Inter Tight', 'Inter', system-ui, sans-serif;
--font-jp:   'Noto Sans JP', sans-serif;
--font-mono: 'JetBrains Mono', ui-monospace, monospace;  /* タイムラインの時刻表示 */

/* Spacing & layout */
--max-w:     1240px;
--gutter:    clamp(20px, 4vw, 56px);
--radius:    2px;       /* 角丸はほぼ無し（素材感重視）*/
--radius-lg: 14px;      /* カード写真のみ */

/* Type scale */
--fs-hero:   clamp(44px, 7vw, 96px);
--fs-h2:     clamp(28px, 3.4vw, 44px);
--fs-h3:     20px;
--fs-body:   16px;
--fs-small:  13px;
--lh-tight:  1.05;
--lh-body:   1.7;

/* Motion */
--ease:      cubic-bezier(0.2, 0.7, 0.2, 1);
--dur:       280ms;
```

### Layout Architecture

```text
index.html
├── header.mast            (透過→白の追従ヘッダー)
├── section.hero           (左コピー / 右縦長写真)
├── section.benefits       (Wi-Fi 1Gbps / 24h Shower / Espresso Bar の3帯)
├── section.floor          (フロアマップ：Work / Train / Recover)
├── section.facilities     (6施設カード)
├── section.day            (1日タイムライン 08:00 → 21:00)
├── section.plans          (Drop-in / Flex / Resident)
├── section.access         (営業時間・住所・会員制ノート)
└── footer
```

---

## 6. References

### 実サイト調査
- [Life Time Work](https://work.lifetime.life/) — "Big endorphins mean better productivity at work" のコピー戦略、Work + Athletic Club の動線統合
- [WeWork](https://www.wework.com/) — Private Office / Coworking / Meeting Rooms の3カード構成、ニュートラル背景・写真ドリブン
- [Equinox Hudson Yards](https://www.equinox.com/clubs/new-york/hudson-yards) — 上質ジムのラウンジ・スパ表現
- [TOKYU SPORTS OASIS](https://www.sportsoasis.co.jp/) — 国内会員制ジムの平面構成・施設写真の見せ方

### Fonts
- [Inter Tight](https://fonts.google.com/specimen/Inter+Tight) — 見出し
- [Inter](https://fonts.google.com/specimen/Inter) — 本文（欧文）
- [Noto Sans JP](https://fonts.google.com/noto/specimen/Noto+Sans+JP) — 本文（和文）
- [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) — タイムラインの時刻

### 同シリーズ参考
- `../../stationery/mono/spec.md` — 配色を1軸に絞る思想
- `../../seasidebookshop/fuyunagi/spec.md` — 「土地・素材で語る」セクション設計
