# Dashboard Design Review Skill

[Claude Code](https://claude.ai/code) 向けのダッシュボードデザインレビュースキルです。

デジタル庁の「ダッシュボードデザインの実践ガイドブック」とanemoのダッシュボードUIデザインガイドラインに基づいて、ダッシュボードのデザインを自動レビューします。

---

## このスキルでできること

ダッシュボードの画像やスクリーンショットを見せるだけで、以下の観点からレビューします：

- **利用者の体験**: 必要な情報が伝わるか、操作が直感的か
- **グラフ・表のデザイン**: 適切なグラフ選択、色数、タイトル表記
- **データ設計**: 目的に合ったデータか、比較値があるか
- **アクセシビリティ**: 色覚多様性への対応
- **視認性・一貫性・慣用性**（anemo基準）

---

## インストール方法

### Claude Code

```bash
/plugin marketplace add [your-github-username]/dashboard-design-review-skill
/plugin install dashboard-design-review-skill
```

### 手動インストール

```bash
# スキルディレクトリにコピーする
cp -r skills/review-dashboard-design ~/.claude/skills/
```

---

## 使い方

インストール後は、Claude Codeにダッシュボードの画像を貼り付けて話しかけるだけです。

```
このダッシュボードをレビューしてください
```

```
このダッシュボードの改善点を教えてください
```

スキルが自動的に起動し、ガイドラインに基づいた詳細なレビューを返します。

### 出力例

```
## ダッシュボードレビュー結果

### 概要
売上管理用の提示型ダッシュボードと判断します。

### 良い点
- KPI指標が左上に大きく配置されており、視線の流れに沿っている
- グラフタイトルに「（月次推移）」などデータ種別が明記されている

### 改善点

#### 優先度: 高
1. **グラフ原点** 棒グラフの縦軸が2,000から始まっており、差が誇張されて見える
   - 現状: y軸の最小値が2,000
   - 改善案: y軸の最小値を0にする
   - 根拠: デジタル庁ガイドブック「表現を歪曲しない」原則

...

### チェックリスト結果
| カテゴリ | 項目 | 評価 |
|---------|------|------|
| 利用者体験 | 必要な情報が提供できているか | ○ |
| グラフデザイン | 棒グラフの原点は0か | × |
...
```

---

## 参照ガイドライン

| ガイドライン | 概要 |
|------------|------|
| [デジタル庁 ダッシュボードデザインの実践ガイドブック](https://www.digital.go.jp/assets/contents/node/basic_page/field_ref_resources/1948e3cd-736a-4378-9e31-039b08d11106/) | 要件整理・プロトタイピング・グラフ設計・チェックリスト |
| [anemo ダッシュボードUIデザインガイドライン](https://note.com/kw_design/n/n085a9349b242) | 視認性・一貫性・慣用性の3指針 |

---

## ファイル構成

```
skills/
└── review-dashboard-design/
    ├── SKILL.md                          # スキル定義
    └── references/
        ├── digital-agency-guidelines.md  # デジタル庁ガイドライン詳細
        ├── anemo-guidelines.md           # anemoガイドライン詳細
        └── checklist.md                  # 総合チェックリスト（27項目）
```

---

## Agent Skills 仕様

このスキルは [Agent Skills 仕様](https://agentskills.io/specification) に準拠しており、Claude Code 以外のAIエージェントでも利用可能です。

```bash
# Vercel Skills CLI でインストール
npx skills add [your-github-username]/dashboard-design-review-skill --global
```

---

## ライセンス

MIT License
