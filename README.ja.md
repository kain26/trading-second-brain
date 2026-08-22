<div align="center">

# 🧠 Trading Second Brain

### チャート、取引、失敗、PDF、スライド、手書きメモを、再利用できるトレーディング記憶へ。

トレーダーのためのマルチモーダル AI ナレッジシステム。

[English](./README.md) · [简体中文](./README.zh-CN.md) · **日本語** · [한국어](./README.ko.md)

**Fork して取引履歴を蓄積し、過去の取引を次の意思決定に活かす。**

</div>

---

## なぜこのプロジェクトなのか

多くのトレーダーはすでに「第二の脳」を持っています。ただし、その情報はバラバラです。

TradingView のスクリーンショット、ブローカーの CSV、PDF リサーチ、Notion、SNS の保存投稿、PowerPoint、手書きノート、日々のレビュー。それらは保存されても、次の取引で再利用されることはほとんどありません。

**Trading Second Brain は、それらを AI Agent が検索・比較・更新できる構造化された取引記憶に変えます。**

> より多く保存することが目的ではありません。  
> 必要な瞬間に、過去の情報を使えるようにすることが目的です。

---

## 通常のトレード日誌との違い

| 通常の日誌 | Trading Second Brain |
|---|---|
| 今日の出来事を記録 | 今日の経験を将来の判断につなげる |
| 主にテキスト | テキスト + 画像 + PDF + PPT + 手書き + CSV |
| 1日単位のレビュー | 複数日のパターン検出 |
| ノートが重複しやすい | 既存トピックを優先的に更新 |
| ルールの理由を忘れる | 変更理由を Decision Log に保存 |
| AI は現在の質問だけを見る | AI が過去の取引履歴を検索できる |

---

## コアループ

```text
画像 / PDF / PPT / 手書き / CSV / メモ
                 ↓
               inbox/
                 ↓
              AI 認識
                 ↓
          抽出 / 分類 / 検証
                 ↓
 knowledge / strategies / journal / trades
                 ↓
            LEARNINGS.md
                 ↓
            decisions.md
                 ↓
              MEMORY.md
                 ↓
               AI Agent
                 ↓
              次の取引日
```

**すべての取引が、次の取引をより賢くする。**

---

## マルチモーダル前提の設計

このシステムには次のような資料を投入できます。

- 📈 TradingView / ブローカーのスクリーンショット
- 🧱 GEX・Dealer Gamma・Option Wall チャート
- 📄 PDF 論文・レポート
- 🖥️ PowerPoint / スライド
- ✍️ 手書きノートの写真
- 📊 取引 CSV
- 📝 日次レビュー・戦略メモ

Agent は **事実を先に抽出し、その後に解釈** します。元データを保持し、既存の知識と照合して適切なファイルへ整理します。

---

## リポジトリ構成

```text
trading-second-brain/
├── CLAUDE.md       # AI Agent の運用ルール
├── MEMORY.md       # 長期的コンテキストとハードルール
├── LEARNINGS.md    # 繰り返し確認された学び
├── decisions.md    # ルール変更の理由
├── knowledge/      # 市場知識
├── strategies/     # 実行可能な戦略
├── journal/        # 日次レビュー
├── trades/         # 構造化された取引記録
├── screenshots/    # チャート・執行証拠
├── research/       # PDF / PPT 原本
├── inbox/          # 未処理資料
├── templates/      # テンプレート
└── prompts/        # AI ワークフロー
```

---

## 5分で開始

1. この Repository を Fork します。
2. `MEMORY.md` に市場、取引スタイル、リスク上限、繰り返す弱点など長期的な情報だけを記入します。
3. スクリーンショット、PDF、PPT、手書き画像、CSV を `inbox/` に入れます。
4. `prompts/inbox-triage.md` をマルチモーダル Agent で実行します。
5. 引け後に `prompts/daily-review.md`、週末に `prompts/weekly-review.md` を実行します。

---

## One Topic = One Maintainable File

大量の `notes-final-v2.md` を作るのではなく、独立して理解・更新できる知識単位ごとにファイルを管理します。

```text
knowledge/
├── dealer-gamma.md
├── gamma-flip.md
├── put-wall.md
├── call-wall.md
├── vwap.md
└── 0dte-gamma.md
```

---

## Memory への昇格は段階的に

```text
raw source
   ↓
journal / knowledge
   ↓
repeated evidence
   ↓
LEARNINGS.md
   ↓
decisions.md
   ↓
MEMORY.md
```

1回の損失や感情的な経験だけで永久ルールを作らないための仕組みです。

---

## 重要な4ファイル

**`CLAUDE.md`** — Agent が何を読み、どこを検索し、画像や文書をどう処理するかを定義します。

**`MEMORY.md`** — 市場、スタイル、リスク制限、繰り返す行動パターンなど長期的情報を保存します。

**`LEARNINGS.md`** — 複数の取引から支持された、まだ修正可能な学びです。

**`decisions.md`** — ルールが「なぜ」変更されたのかを証拠とともに残します。

---

## 用意されている Prompt

| Prompt | 用途 |
|---|---|
| `inbox-triage.md` | マルチモーダル資料の整理 |
| `screenshot-analysis.md` | チャート画像の分析 |
| `research-extraction.md` | PDF / PPT から知識を抽出 |
| `handwritten-notes.md` | 手書きノートを認識・分類 |
| `daily-review.md` | 日次レビュー |
| `weekly-review.md` | 週次パターン分析 |

---

## データが蓄積するとできる質問

- どの時間帯で最も損失が大きいか？
- 2連勝した後の次の取引成績はどうか？
- Positive Gamma / Negative Gamma で最も相性の良い戦略は？
- 同じストップルールを破った取引をすべて表示して。
- 負けトレードの画像に共通する Price Action はあるか？
- このルールを最初に作ったのはいつで、なぜか？

---

## Public と Private を分ける

```text
Public Repo  = OS / Template / Prompt
Private Repo = 実際の Trading Brain
```

口座番号、API Key、Broker Statement、非公開 PnL などを Public Repo にコミットしないでください。

---

## Disclaimer

本プロジェクトはトレーディング知識管理のためのフレームワークです。投資助言・金融助言・自動売買推奨ではありません。市場取引には大きなリスクがあります。

<div align="center">

**スクリーンショットもデータ。失敗もデータ。ルールもデータ。**

**検索可能にし、再利用可能にする。**

</div>
