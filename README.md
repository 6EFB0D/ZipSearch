# ZipSearch - アーカイブログ横断検索ツール

**バージョン**: 0.5.7（評価版・DEV ビルド）  
**ライセンス**: MIT License

ZIP・ローカル・HTTP(S) 上のログや CSV を、**展開せずに横断検索**できる Windows 向けツールです。

> **log4net の過去ログを、ZIP のまま、複数ファイル横断で、ERROR と時刻で絞り込む。**

リアルタイム監視ではなく、**保守・障害調査・納品ログ確認**に特化しています。v0.5.0 から **log4net ログ解析**（Pro 限定）で、.NET アプリの過去ログを Level / Logger / 日時で構造化して調査できます。

## 🎯 こんなときに ZipSearch

- 障害時刻の前後を ERROR / WARN で素早く絞り込みたい
- `app.log` と `app.log.1` など **Rolling ログをまとめて**追いたい
- **ZIP に封入されたログ**を解凍せずに検索したい
- **HTTP(S) 上の ZIP ログ**を URL 指定で直接調べたい
- 調査結果を CSV / JSON で共有し、CLI で再現したい

## 💡 どんな調査に向いているか

| やりたいこと | ZipSearch でできること |
|--------------|------------------------|
| 過去ログを log4net の Level / Logger で絞る | **◎** Pro の列解析・フィルタ |
| ZIP ログを展開せず横断検索 | **◎** 非展開で ZIP / 7z 内を検索 |
| 社内 URL の ZIP ログを直接調べる | **◎** HTTP(S) 対応 |
| ローテーション済み .log を一括追跡 | **◎** Rolling 兄弟横断（Pro） |
| 稼働中アプリの常時リアルタイム監視 | 対象外（出力済みログの調査向け） |
| 巨大 1 ファイルの精読・編集 | 対象外（横断・絞り込み調査向け） |

## 📋 特徴

* ✅ **アーカイブ横断**: ZIP / 7z / HTTP(S) を**非展開**で検索
* ✅ **log4net 解析**（Pro）: PatternLayout 列解析・Level/Logger フィルタ・スタックトレース統合
* ✅ **Rolling 横断**（Pro）: `app.log` + `.log.1` 等を一括検索
* ✅ **3つのインターフェース**: CLI / GUI / WebUI
* ✅ **複数形式対応**: ZIP, CSV, TSV, TXT, `.log`, Excel（Pro）
* ✅ **HTTP/HTTPS検索**: イントラネットのZIPファイルも検索可能
* ✅ **結果エクスポート**: CSV/JSON形式で保存（Pro版）

## 🆓 フリー版 vs Pro版（v0.5.0）

| 項目 | フリー版 | Pro版 |
|------|---------|-------|
| ファイルサイズ | **10 MB**/ファイルまで | **無制限** |
| 同時検索 | 最大5ファイル | **無制限** |
| 検索結果 | 最大10件 | **無制限** |
| log4net ログ解析 | ❌（`.log` 行検索のみ） | ✅ PatternLayout 列解析 |
| INI / JSON / KV 構造化解析 | ❌（行検索のみ・表形式フラット化なし。結果に Pro 案内） | ✅ 表形式に展開 |
| サブフォルダ再帰 | ❌（フォルダ／ZIP とも直下のみ） | ✅ |
| ドラッグ＆ドロップ | ✅ | ✅ |
| エクスポート機能 | ❌ 使用不可 | ✅ CSV/JSON |
| 検索速度 | シングルスレッド | **マルチスレッド**（指定可能） |
| カラム指定検索 | ❌ 使用不可 | ✅ 列番号/列名で指定 |
| 範囲検索 | ❌ 使用不可 | ✅ 日付/数値の範囲指定 |
| お気に入り機能 | ❌ 使用不可 | ✅ グループ化・名前付き登録 |
| 端末数 | — | **1 ライセンス 1 台** |

## 💎 Pro版について

**価格: 9,980円（税込・買い切り）** — 1 ライセンス 1 台

### Pro版の主な機能

**log4net ログ調査（ZipSearch の差別化核）**
- PatternLayout の列解析（日時・Level・Logger・メッセージ）
- **マルチライン例外** — ERROR 行＋スタックトレースを1エントリとして検索
- レベル / Logger / 日時フィルタ、**Rolling 兄弟ファイル横断**
- **ZIP / HTTP(S) 上のログ**を非展開で横断

**基本機能の拡張**
- 無制限のファイル検索（ファイル数・サイズの制限なし）
- CSV/JSONエクスポート

**高速検索**
- 並列検索（マルチスレッド）

**高度な検索・便利機能**
- カラム指定検索、範囲検索、お気に入り登録

**評価版**: 14 日間 Pro をサポート経由で配布（v0.5.0）。購入・評価のお問い合わせは [Office Go Plan](https://6EFB0D.github.io/office-goplan/) から。

最新情報は [Discussions](https://github.com/6EFB0D/ZipSearch/discussions/categories/announce) でご確認ください。

## 📦 インストール

### Windows版（インストーラ）

1. [リリースページ](https://github.com/6EFB0D/ZipSearch/releases)を開き、ページ下部の **「Assets」** から `ZipSearch-0.5.7-dev-setup.exe` をダウンロード
2. インストーラを実行してインストール
3. デスクトップまたはスタートメニューから ZipSearch を起動

**注意**: Python環境の構築は不要です。すべての依存関係がインストーラに含まれています。

### うまくいかないとき（セキュリティでブロックされる場合）

ブラウザや Windows のセキュリティ警告（SmartScreen 等）で **`.exe` のダウンロードや実行ができない** 場合は、次をお試しください。

1. Assets から **`ZipSearch-*-dev-setup.zip`** をダウンロード
2. ZIP を解凍し、中の **setup.exe** を実行してインストール
3. 実行時に警告が出た場合は **「詳細情報」→「実行」** を選択
## 🚀 使い方

### GUI版（推奨）

インストール後、デスクトップアイコンまたはスタートメニューから起動できます。

1. **検索パス**を指定（ZIPファイルまたはフォルダ）
2. **検索キーワード**を入力
3. 必要に応じてオプションを設定
4. **検索開始**ボタンをクリック

### CLI版

コマンドプロンプトまたはターミナルから実行：

```bash
# ヘルプを表示
zipsearch --help

# ローカルファイル検索
zipsearch "keyword" ./data.zip

# フォルダ内のZIPファイルを検索
zipsearch "keyword" ./archive_folder/

# HTTP/HTTPS経由で検索
zipsearch "keyword" http://server/data.zip

# 結果をCSV形式で出力（Pro版限定）
zipsearch "keyword" ./data.zip -o results.csv --format csv

# 結果をJSON形式で出力（Pro版限定）
zipsearch "keyword" ./data.zip -o results.json --format json
```

### Web版

```bash
# Webサーバーを起動
zipsearch-web

# ブラウザで http://localhost:5000 にアクセス
# （自動的にブラウザが開きます）
```

終了するには、ターミナルで `Ctrl+C` を押してください。

## 📁 サンプルデータで試す

インストール先の `sample_data` フォルダ（スタートメニュー →「ZipSearch」→「サンプルデータ」からも開けます）に、評価用サンプルを同梱しています。

| フォルダ | 内容 | 試せる機能 |
|----------|------|-----------|
| `pdfhandler_demo_logs` | log4net 形式の Rolling ログ ZIP | log4net 解析（Pro）、Rolling 横断 |
| `structured_kv_logs` | 多層フォルダ + `key=value` ログの ZIP | サブフォルダ再帰検索、KV 構造化検索（Pro） |
| `empty_cell_csv` | 空セルありの CSV / ZIP | 空セル検索（Pro・値フィルタ完全一致 `列=` / `*=`） |

各フォルダの `README.md` に手順とキーワード例を記載しています。まずは `sample_data` の ZIP を GUI へドラッグ＆ドロップしてお試しください。

## 🤝 サポート

* [Office Go Plan](https://6EFB0D.github.io/office-goplan/)（ホームページ・お問い合わせ）

## 📄 ライセンス

MIT License - 詳細は [LICENSE](LICENSE) ファイルをご覧ください

Copyright (c) 2026 Office Go Plan

## 📥 ダウンロード

インストーラは [Releases](https://github.com/6EFB0D/ZipSearch/releases) の **ページ下部「Assets」** から入手できます。各ファイルの SHA-256 チェックサムを同梱しています。`.exe` がセキュリティでブロックされる場合は **setup.zip** をご利用ください（詳細は「インストール」章）。
