# ダッシュボードデザインレビュー

**ダッシュボードデザインレビュー** は、デジタル庁の「[ダッシュボードデザインの実践ガイドブック](https://www.digital.go.jp/resources/dashboard-guidebook)」とanemoの「[ダッシュボードUIデザインガイドライン](https://note.com/kw_design/n/n085a9349b242)」に基づいて、ダッシュボードのデザインを自動レビューする [Claude Code](https://claude.ai/code) スキルです。

## 使い方

画像・スクリーンショットを貼り付けるか、公開URL（Looker Studio・Tableau Public・Metabase等）を貼るだけでレビューします。

```
このダッシュボードをレビューしてください
```

URLを貼る場合:

```
https://example.com/dashboard このダッシュボードをレビューしてください
```

URLの場合はブラウザで自動的に開いてキャプチャした上でレビューします（ログイン不要の公開ページのみ対応）。

## インストール

### Claude Code

```
/plugin marketplace add Shakshi3104/dashboard-design-review-skill
/plugin install dashboard-design-review-skill
```

### Vercel Skills CLI

```bash
npx skills add Shakshi3104/dashboard-design-review-skill --global
```

## 参照ガイドライン

| ガイドライン | 概要 |
|------------|------|
| [デジタル庁 ダッシュボードデザインの実践ガイドブック](https://www.digital.go.jp/resources/dashboard-guidebook) | 要件整理・プロトタイピング・グラフ設計・チェックリスト |
| [anemo ダッシュボードUIデザインガイドライン](https://note.com/kw_design/n/n085a9349b242) | 視認性・一貫性・慣用性の3指針 |

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

## ライセンス

MIT License
