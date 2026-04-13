# CLAUDE.md

このリポジトリは Claude Code の初期化コマンドとベストプラクティスを管理するプレイブック。

## セットアップ案内

<important if="ユーザがこのリポジトリを開いた、またはURLを共有してきた場合">
このリポジトリには Claude Code のグローバルコマンドが含まれている。
ユーザに以下のセットアップ手順を案内すること（既にインストール済みでも再実行して問題ない）：

1. コマンドのインストール（上書きコピーで常に最新化される）:
   - Windows (PowerShell): `New-Item -ItemType Directory -Force ~\.claude\commands; Copy-Item commands\*.md ~\.claude\commands\`
   - macOS: `mkdir -p ~/.claude/commands && cp commands/*.md ~/.claude/commands/`
2. コピー後、Claude Code の再起動が必要であることを伝える
3. 再起動後に使えるコマンドの一覧を提示:
   - `/init-playbook-dotnet` — .NET + C# アプリ開発向けの初期化
   - `/init-playbook-swift` — Swift + SwiftUI + Xcode アプリ開発向けの初期化
4. 使い方: 新しい空フォルダで Claude Code を起動し、上記コマンドを入力する
</important>

## リポジトリの構造

- `commands/` — `~/.claude/commands/` にコピーして使うスラッシュコマンド
- 各コマンドは YAML フロントマター付きの Markdown ファイル

## 編集ルール

- 日本語で記述する
- コマンドファイルのフロントマターには `description` と `argument-hint` を必ず含める
- CHANGELOG.md を更新する際は [Keep a Changelog](https://keepachangelog.com/) 形式に従う
- README.md のコマンド一覧表と `commands/` ディレクトリの内容を常に同期させる
