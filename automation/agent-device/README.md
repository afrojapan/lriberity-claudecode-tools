# agent-device

AIエージェントがモバイル・デスクトップアプリのUIを操作・テストするためのCLIツールです。

iOS / tvOS / macOS / Android / AndroidTV に対応しており、Vercel の [agent-browser](https://github.com/vercel/agent-browser) にインスパイアされてモバイル向けに設計されました。

**リポジトリ:** https://github.com/callstackincubator/agent-device

---

## 特徴

| 機能 | 説明 |
|---|---|
| UI インスペクション | アクセシビリティツリーをコンパクトな形式でスナップショット化 |
| セッション管理 | アプリを一度起動し、セッション内で確定的に操作・終了 |
| 確定的なアクション | `press` / `fill` / `scroll` / `type` などのコマンドで操作 |
| テスト自動化 | `.ad` スクリプトでE2Eテスト・リトライ・タイムアウト管理 |
| パフォーマンス計測 | 起動時間・CPU・メモリ使用量のメトリクス収集 |

---

## インストール

```bash
npm install -g agent-device
```

---

## 基本的な使い方

```bash
# アプリのUIスナップショットを取得
agent-device snapshot --platform ios --app com.example.app

# ボタンをタップ
agent-device press --selector "Login Button"

# テキストを入力
agent-device fill --selector "Email Field" --value "user@example.com"

# .ad スクリプトを実行
agent-device run ./test.ad
```

---

## 対応プラットフォーム

- iOS
- tvOS
- macOS
- Android
- AndroidTV

---

## 技術スタック

- TypeScript（メイン実装）
- Swift（macOS ヘルパーアプリ）
- npm グローバルパッケージとして配布
