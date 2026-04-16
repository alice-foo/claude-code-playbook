# claude-code-playbook

> **Note:** This is a community project, not an official Anthropic product.

Claude Code でアプリ開発を始めるためのプレイブックです。

空のフォルダで `/init-playbook-generic`、`/init-playbook-dotnet`、`/init-playbook-swift` を実行すると、
Claude Code が要件のヒアリングから設計・実装まで段階的に進めてくれます。

- **汎用初期化**：言語・フレームワークに依存しない共通設定を即座に適用
- **言語別初期化**：.NET、Swift など特定の言語に最適化されたフロー

## 使い方

### 1. インストール

`commands/` 内のファイルを `~/.claude/commands/` にコピーします。

**Windows (PowerShell):**
```powershell
New-Item -ItemType Directory -Force ~\.claude\commands; Copy-Item commands\*.md ~\.claude\commands\
```

**macOS:**
```bash
mkdir -p ~/.claude/commands && cp commands/*.md ~/.claude/commands/
```

コピー後、Claude Code を再起動すると、どのプロジェクトからでも以下のコマンドが使えるようになります。

### 2. コマンドの実行

空のフォルダで Claude Code を起動し、以下を入力するだけです。

**言語非依存の汎用初期化の場合:**
```
/init-playbook-generic
```
（質問なしで、共通的な設定テンプレート（CLAUDE.md、README.md、.gitignore など）を即座に生成）

**.NET + C# 開発の場合:**
```
/init-playbook-dotnet
```

**Swift + SwiftUI + Xcode 開発の場合:**
```
/init-playbook-swift
```

### 3. Claude Code の動作

1. Plan Mode で起動します（いきなりコードは書きません）
2. ユーザへのインタビュー形式で要件を定義します
3. CLAUDE.md、プロジェクト構造、実装計画を生成します
4. 承認後、「実装 → ビルド確認 → コミット」のサイクルをフェーズごとに繰り返します

## コマンド一覧

| コマンド | 対象 |
|---------|------|
| `/init-playbook-generic` | 汎用プロジェクト初期化（質問なし、即座にテンプレート生成） |
| `/init-playbook-dotnet` | .NET + C# アプリ開発向けの初期化（インタビュー式、計画先行） |
| `/init-playbook-swift` | Swift + SwiftUI + Xcode アプリ開発向けの初期化（インタビュー式、計画先行） |

## リポジトリ構成

```
claude-code-playbook/
├── .gitignore
├── CHANGELOG.md        # 変更履歴
├── CLAUDE.md           # このプレイブックの Claude Code 設定
├── LICENSE             # MIT License
├── README.md           # このファイル
└── commands/           # ~/.claude/commands/ にコピーして使います
    ├── init-playbook-generic.md     # 汎用プロジェクト初期化
    ├── init-playbook-dotnet.md      # .NET + C# アプリ開発向けの初期化
    └── init-playbook-swift.md       # Swift + SwiftUI + Xcode アプリ開発向けの初期化
```

## 設計原則

| パターン | 採用理由 |
|---------|---------|
| 計画先行の開発 | いきなりコードを書く暴走を防ぐため |
| 対話式の要件定義 | ユーザの想定していない要件を洗い出すため |
| 簡潔な設定ファイル | Claude による個別ルールの見落としを防ぐため |
| 段階的な実装 | コンテキストの鮮度維持と各段階での品質確認に役立つため |
| 毎回のビルド検証 | 品質確認に役立つため |

## 参考リポジトリ

このプレイブックの設計原則は、以下のリポジトリや Claude Code 公式ドキュメントの調査から得た知見に基づいています。

| リポジトリ | 概要 |
|-----------|------|
| [shanraisshan/claude-code-best-practice](https://github.com/shanraisshan/claude-code-best-practice) | Claude Code の使い方ガイド |
| [obra/superpowers](https://github.com/obra/superpowers) | テスト駆動の開発フロー集 |
| [github/spec-kit](https://github.com/github/spec-kit) | 仕様書ベースの開発手法 |
| [garrytan/gstack](https://github.com/garrytan/gstack) | AI との対話テンプレート集 |
| [gsd-build/get-shit-done](https://github.com/gsd-build/get-shit-done) | 段階的な実装の進め方 |
| [bmad-code-org/BMAD-METHOD](https://github.com/bmad-code-org/BMAD-METHOD) | AI に役割を与える開発手法 |
| [affaan-m/everything-claude-code](https://github.com/affaan-m/everything-claude-code) | Claude Code の設定例の大規模コレクション |

## 免責事項

- このプレイブックは Anthropic の公式プロダクトではありません。
- このプレイブックは無保証で提供されます。利用によって生じた損害について、作者は一切の責任を負いません。

## ライセンス

[MIT License](LICENSE)
