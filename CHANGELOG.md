# 変更履歴

## [1.2.0] - 2026-05-10

### 追加
- `init-playbook-swift` / `init-playbook-dotnet` のインタビューに「CLI デバッグ基盤」の項目を追加
  - アプリにログ出力・CLI からの操作の機能を組み込むかどうかをユーザに確認する
  - 組み込む場合は、生成する設計ドキュメントに Swift / .NET それぞれの実装ガイドラインを含める

### 修正
- `init-playbook-generic` — Python スクリプトへの依存を廃止し、Claude Code が直接テンプレートを生成する方式に変更。`.gitignore` テンプレートにスクリプト側にのみ存在していた項目を反映

## [1.1.0] - 2026-04-16

### 追加
- `commands/init-playbook-generic.md` — 汎用プロジェクト初期化スキル
  - 言語・フレームワークに依存しない共通設定を自動生成
  - 質問なしでデフォルト値で即座に適用
  - CLAUDE.md、README.md、.gitignore、メモリシステムを生成

### 変更
- README.md — init-playbook-generic の説明と使い方を追加
- CLAUDE.md — セットアップ手順に init-playbook-generic を追加

## [1.0.0] - 2026-04-13

### 追加
- `commands/init-playbook-dotnet.md` — .NET + C# アプリ開発向けの初期化
- `commands/init-playbook-swift.md` — Swift + SwiftUI + Xcode アプリ開発向けの初期化
- `README.md` — リポジトリの説明と使い方
- `CLAUDE.md` — このリポジトリ自体の Claude Code 設定

### 調査ベース
- 7 個以上の Claude Code ワークフローリポジトリと公式ドキュメントを調査（README.md に一覧）
- .NET + C# 固有、Swift + SwiftUI + Xcode 固有の知見を個別に調査・反映
