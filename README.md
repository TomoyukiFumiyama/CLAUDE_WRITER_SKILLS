# article-writing plugin

Cowork向けの記事執筆プラグインです。記事企画からリサーチ、構成、本文執筆、SEO最適化、校正までをスキル分割して実行できます。

## ディレクトリ構成

```text
CLAUDE_WRITER_SKILLS/
├── .claude-plugin/
│   └── plugin.json
├── .mcp.json
├── skills/
│   ├── research/
│   │   └── SKILL.md
│   ├── outline-comparison/
│   │   └── SKILL.md
│   ├── outline-review/
│   │   └── SKILL.md
│   ├── outline-best-practices/
│   │   └── SKILL.md
│   ├── drafting-comparison/
│   │   ├── SKILL.md
│   │   └── references/
│   │       └── tone-guide.md
│   ├── drafting-review/
│   │   ├── SKILL.md
│   │   └── references/
│   │       └── tone-guide.md
│   ├── drafting-best-practices/
│   │   ├── SKILL.md
│   │   └── references/
│   │       └── tone-guide.md
│   ├── seo/
│   │   └── SKILL.md
│   └── editing/
│       └── SKILL.md
└── README.md
```

## plugin.json

```json
{
  "name": "article-writing",
  "description": "記事の企画・リサーチ・執筆・SEO最適化・校正までを一貫して行うプラグイン",
  "version": "1.0.0",
  "author": "tomoyuki"
}
```

## 記事種別ごとのエージェント分離

- 比較記事: `outline-comparison` → `drafting-comparison`
- レビュー記事: `outline-review` → `drafting-review`
- ベストプラクティス記事: `outline-best-practices` → `drafting-best-practices`

各スキルには「最適化プロンプト」を記述してあり、記事種別に応じて構成と本文の生成方針を切り替えられます。

## GitHub管理 → ローカル運用の流れ

```bash
# 1. GitHubからclone
git clone https://github.com/your-username/article-writing-plugin.git

# 2. Coworkのプラグインフォルダにシンボリックリンク or コピー
# （Coworkが認識するパスに配置）
```

Coworkではプラグインをインストールすると `skills/` 配下のSkillが自動認識されます。
