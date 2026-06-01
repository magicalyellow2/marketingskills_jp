# 日本語マーケティング・広告デザイン スキルセット

元ファイル（英語版）をベースに、日本市場・日本語・日本の広告規制に対応した
マーケティングスキルファイル集。

---

## ファイル構成と役割

```
【基盤レイヤー】← 一度作れば全クライアントで使い回し
├── jp-legal-ad.md             法規制（薬機法・景表法・特商法・業種別）
├── jp-ad-creative.md          広告制作・媒体別仕様・法的チェック
├── jp-copywriting.md          コピーライティング原則
├── jp-copy-editing.md         編集・品質チェック（7スウィープ）
├── jp-marketing-psychology.md 日本市場の心理・行動原則
├── jp-stop-slop.md            AI文章パターンの除去
└── jp-product-marketing.md    クライアントファイルの設計ガイド（参照用）

【クライアントレイヤー】← 案件ごとに作る
└── clients/
    ├── client-template.md     雛形（これをコピーして使う）
    ├── client-A.md            実クライアントA
    └── client-B.md            実クライアントB
```

---

## スキルファイル一覧

| ファイル名 | 役割 | 主な用途 |
|-----------|------|---------|
| `jp-legal-ad.md` | **法規制（基盤）** | 薬機法・景表法・特商法・ステマ規制・業種別規制。全制作物のチェックに使う |
| `jp-ad-creative.md` | **広告制作** | Google/Meta/LINE/Yahoo!/X広告のコピー生成。媒体別文字数・アングル設定・法的チェック |
| `jp-copywriting.md` | **コピー作成** | LP・HP・価格ページなどのWebコピーをゼロから作成する原則 |
| `jp-copy-editing.md` | **コピー改善** | 既存コピーを7つの視点で磨く。AI生成コピーの修正に特に有効 |
| `jp-marketing-psychology.md` | **心理・行動原則** | 日本市場特有の消費者心理と説得原則。制作の判断基準として参照 |
| `jp-stop-slop.md` | **品質チェック** | AI文章の日本語特有パターンを除去するチェックリスト |
| `jp-product-marketing.md` | **設計ガイド** | client-templateの各項目の意図・書き方の解説。実制作ではclientsを使う |
| `client-template.md` | **雛形** | クライアントごとにコピーして使う。基盤スキルと組み合わせて動く |

---

## スキル間の参照関係

```
clients/クライアント名.md
    ↓ 業種・制約・顧客の言葉を供給
    ↓
jp-legal-ad.md ──────────────────────────────┐
    ↓ 適用法規制・NG表現・代替表現を供給        │
    ↓                                        │
jp-marketing-psychology.md                   │
    ↓ 心理原則・訴求軸を供給                   │
    ↓                                        ↓
jp-ad-creative.md ←──── jp-copywriting.md    │
    ↓                         ↓              │
    └─────────────────────────┘              │
                  ↓                          │
         jp-copy-editing.md ←───────────────┘
                  ↓
         jp-stop-slop.md（最終チェック）
```

---

## 推奨ワークフロー

### 新規クライアント開始時

```
1. jp-product-marketing.md を読んで各項目の意図を把握する
2. client-template.md をコピーして clients/クライアント名.md を作成する
3. jp-legal-ad.md の規制適用マップで適用法規制を確認し、
   クライアントファイルの「法的チェック事項」セクションに転記する
```

### 広告コピー制作

```
1. clients/クライアント名.md を読む（製品・ターゲット・禁止表現を把握）
2. jp-legal-ad.md で該当業種の規制を確認する
3. jp-marketing-psychology.md でターゲットの心理・訴求軸を決める
4. jp-ad-creative.md でアングル設定→コピー生成→法的チェック
5. jp-stop-slop.md で最終チェック
```

### LP・Webコピー制作

```
1. clients/クライアント名.md を読む
2. jp-legal-ad.md で該当業種の規制を確認する
3. jp-copywriting.md でページ構造・ヘッドライン・CTAを作成する
4. jp-copy-editing.md の7スウィープで品質チェック
5. jp-stop-slop.md で最終チェック
```

### 既存コピーの改善

```
1. clients/クライアント名.md を読む
2. jp-legal-ad.md で法的リスクを先に確認する
3. jp-copy-editing.md の7スウィープで問題を特定・修正する
4. jp-stop-slop.md でAI文章パターンを除去する
```

---

## Claudeへの指示テンプレート

### 広告コピー生成

```
以下のファイルを参照してください：
- jp-legal-ad.md
- jp-ad-creative.md
- clients/[クライアント名].md

タスク：[媒体]の広告コピーを[本数]案作成
訴求：[何を伝えたいか]
その他：[締切・特記事項]
```

### LP制作

```
以下のファイルを参照してください：
- jp-legal-ad.md
- jp-copywriting.md
- clients/[クライアント名].md

タスク：[サービス名]のLPコピーを作成
流入：[広告媒体・検索キーワードなど]
ゴール：[無料相談・購入・資料請求など]
```

### コピー改善

```
以下のファイルを参照してください：
- jp-legal-ad.md
- jp-copy-editing.md
- clients/[クライアント名].md

タスク：以下のコピーを改善してください
[コピーを貼り付け]
```

---

## ナレッジファイルのアップロード順序

Claudeのプロジェクトナレッジにアップロードする場合の推奨順序：

**Step 1（基盤・最初にアップロード）**
1. `jp-legal-ad.md` — すべての制作物の法的判断基準
2. `jp-marketing-psychology.md` — すべての制作物の心理的判断基準
3. `jp-product-marketing.md` — クライアントファイルの設計ガイド

**Step 2（制作スキル）**
4. `jp-ad-creative.md`
5. `jp-copywriting.md`
6. `jp-copy-editing.md`
7. `jp-stop-slop.md`

**Step 3（クライアント管理）**
8. `client-template.md`
9. `clients/クライアント名.md`（案件ごとに追加）

**理由：**
- 法規制・心理原則は制作スキルが参照するため先に読み込まれている必要がある
- クライアントファイルは最後に追加し、基盤スキルと組み合わせて動かす
- 新しいクライアントが増えるたびにStep 3のみ追加すればよい

---

## 英語版スキルとの対応関係

| 英語版スキル | 日本語版スキル | 主な変更点 |
|-------------|--------------|-----------|
| `ad-creative` | `jp-ad-creative` | 日本媒体仕様・景表法・薬機法チェック追加 |
| `copywriting` | `jp-copywriting` | 日本語の説得構造・間接表現・感情共鳴を反映 |
| `copy-editing` | `jp-copy-editing` | 過剰敬語・カタカナ語など日本語固有の問題を追加 |
| `marketing-psychology` | `jp-marketing-psychology` | 集団志向・もったいない意識など日本固有の心理を中心に再構成 |
| `stop-slop` | `jp-stop-slop` | 日本語AI文章特有のパターンに特化 |
| `product-marketing` | `jp-product-marketing` + `client-template` | 設計ガイドとクライアント雛形に分離 |
| （新規）| `jp-legal-ad` | 薬機法・景表法・特商法・ステマ規制を実務レベルで整理 |

---

作成：日本市場向けマーケティング・広告デザイン用
ベース：英語版マーケティングスキルファイル集
