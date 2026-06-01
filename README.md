# 日本語マーケティング・広告デザイン スキルセット

日本市場・日本語・日本の広告規制（薬機法・景表法・特商法）に対応した  
マーケティング・広告制作用スキルファイル集。

英語版マーケティングスキル（[coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills)）をベースに、  
日本市場向けに全面再構成・法規制対応を追加したものです。

---

## ファイル構成

```
marketingskills_jp/
├── README.md
├── skills/
│   ├── jp-legal-ad.md             法規制（薬機法・景表法・特商法・業種別）
│   ├── jp-marketing-psychology.md 日本市場の心理・行動原則
│   ├── jp-product-marketing.md    クライアントファイルの設計ガイド
│   ├── jp-ad-creative.md          広告制作・媒体別仕様
│   ├── jp-copywriting.md          コピーライティング原則
│   ├── jp-copy-editing.md         編集・品質チェック（7スウィープ）
│   └── jp-stop-slop.md            AI文章パターンの除去
└── clients/
    ├── client-template.md         クライアント雛形（コピーして使う）
    └── client-sample-skincare.md  記入例（化粧品ECブランド）
```

---

## スキルファイル一覧

| ファイル名 | 役割 | 主な用途 |
|-----------|------|---------|
| `jp-legal-ad.md` | **法規制（基盤）** | 薬機法・景表法・特商法・ステマ規制・業種別規制。全制作物の法的チェックに使う |
| `jp-marketing-psychology.md` | **心理・行動原則** | 日本市場特有の消費者心理と説得原則。制作の判断基準として参照 |
| `jp-product-marketing.md` | **設計ガイド** | client-templateの各項目の意図・書き方の解説 |
| `jp-ad-creative.md` | **広告制作** | Google/Meta/LINE/Yahoo!/X広告のコピー生成。媒体別文字数・アングル設定 |
| `jp-copywriting.md` | **コピー作成** | LP・HP・価格ページなどのWebコピーをゼロから作成する原則 |
| `jp-copy-editing.md` | **コピー改善** | 既存コピーを7つの視点で磨く。AI生成コピーの修正に特に有効 |
| `jp-stop-slop.md` | **品質チェック** | AI文章の日本語特有パターン（過剰前置き・副詞・過剰敬語）を除去 |
| `client-template.md` | **クライアント雛形** | 案件ごとにコピーして使う。基盤スキルと組み合わせて動く |

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

## オプション：コンテキストエンジニアリングスキルの導入

以下の3ファイルは **必須ではありません** が、導入することでClaude の動作精度が向上する場面があります。  
出典：[magicalyellow2/Agent-Skills-for-Context-Engineering](https://github.com/magicalyellow2/Agent-Skills-for-Context-Engineering)

### `context-fundamentals`
**何に有効か：**  
長い会話・多数のファイルを扱うときに、Claudeがどの情報をどの優先度で参照するかの土台となる考え方を提供します。複数クライアントの案件を同一セッションで扱う場合や、スキルファイルの数が増えてきたときに、情報の混在や見落としを防ぐ効果があります。

**導入するとよい場面：**
- クライアントが3社以上になってきた
- 1回の会話で複数の制作タスクをこなすことが多い
- 私が以前の指示を忘れたり混在させたりすることが気になる

---

### `context-optimization`
**何に有効か：**  
トークン（Claudeが一度に処理できる情報量）を効率よく使うための戦略を提供します。スキルファイルとクライアントファイルが増えると、全部を読み込むとコストと処理時間が増大します。このファイルは「今のタスクに必要な情報だけを効率よく使う」ための設計指針となります。

**導入するとよい場面：**
- スキルファイル・クライアントファイルが10個以上に増えた
- 長い制作セッションで途中から回答の質が落ちてくる感覚がある
- Claude Proの使用量・コストを意識し始めた

---

### `memory-systems`
**何に有効か：**  
セッションをまたいだ記憶の設計原則を提供します。Claudeは会話が終わると記憶をリセットするため、毎回クライアント情報を渡し直す必要があります。このスキルは「何をどのように記憶させるか」の設計を体系化するもので、`clients/`フォルダの設計思想と直接つながります。

**導入するとよい場面：**
- クライアントファイルの構成をさらに洗練させたい
- 過去の制作物・NGになった表現・承認済みの表現を蓄積・管理したい
- 将来的にClaude Codeなどのエージェント環境での活用を検討している

---

### オプションスキルのアップロード順序

コンテキストエンジニアリングスキルを追加する場合は、**このスキルセットより前に**アップロードしてください。

```
【任意・先行してアップロード】
1. context-fundamentals
2. context-optimization（任意）
3. memory-systems（任意）

【このスキルセット・後にアップロード】
4. 以降のStep 1〜3（下記参照）
```

---

## ナレッジファイルのアップロード順序

Claudeのプロジェクトナレッジにアップロードする場合の推奨順序です。  
**依存関係の順（参照される側が先）** に従っています。

### Step 0（任意）：コンテキストエンジニアリング基盤
> 長期・大量案件での精度向上を目的とする場合のみ

0-1. `context-fundamentals`  
0-2. `context-optimization`（任意）  
0-3. `memory-systems`（任意）  

### Step 1：法規制・心理・設計ガイド（基盤スキル）
> 制作スキルが参照するため、必ず先にアップロード

1-1. `jp-legal-ad.md` — 全制作物の法的判断基準  
1-2. `jp-marketing-psychology.md` — 全制作物の心理的判断基準  
1-3. `jp-product-marketing.md` — クライアントファイルの設計ガイド  

### Step 2：制作スキル
> 基盤スキルを参照するため、Step 1の後にアップロード

2-1. `jp-ad-creative.md`  
2-2. `jp-copywriting.md`  
2-3. `jp-copy-editing.md`  
2-4. `jp-stop-slop.md`  

### Step 3：クライアント管理
> 制作スキルの前提となる情報を持つ。案件が増えるたびに追加

3-1. `client-template.md`  
3-2. `clients/クライアント名.md`（案件ごとに追加）  

---

**順序の理由：**
- Step 0は「Claudeがスキルファイルをどう扱うか」の土台。あれば最初に読まれるべき
- Step 1の法規制・心理原則は、Step 2の制作スキルが内部で参照している
- Step 3のクライアントファイルは制作時に毎回最初に読まれるが、制作スキルの後にあることで「何のためのクライアント情報か」が明確になる

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
ベース：[coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills)  
オプション参照：[magicalyellow2/Agent-Skills-for-Context-Engineering](https://github.com/magicalyellow2/Agent-Skills-for-Context-Engineering)
