# ZipSearch - ZIP内高速検索ツール
ZIP/7z内のCSV/TSV/TXTを高速検索するツール

![GitHub release](https://img.shields.io/github/v/release/6EFB0D/ZipSearch?style=flat-square)
![GitHub downloads](https://img.shields.io/github/downloads/6EFB0D/ZipSearch/total?style=flat-square)
![GitHub latest downloads](https://img.shields.io/github/downloads/6EFB0D/ZipSearch/latest/total?style=flat-square)
![License](https://img.shields.io/github/license/6EFB0D/ZipSearch?style=flat-square)
![GitHub stars](https://img.shields.io/github/stars/6EFB0D/ZipSearch?style=flat-square)
![GitHub forks](https://img.shields.io/github/forks/6EFB0D/ZipSearch?style=flat-square)
![GitHub issues](https://img.shields.io/github/issues/6EFB0D/ZipSearch?style=flat-square)

**バージョン**: 0.2.0 (フリーミアム版)  
**ライセンス**: MIT License

ZIP/7z形式の圧縮ファイル内のCSV/TSV/TXTファイルを、**展開せずに高速検索**できるツールです。

## 📋 特徴

* ✅ **3つのインターフェース**: CLI / GUI / WebUI
* ✅ **複数形式対応**: ZIP, 7z, CSV, TSV, TXT
* ✅ **HTTP/HTTPS検索**: イントラネットのZIPファイルも検索可能
* ✅ **HTTPブラウジング**: フォルダURLからZIPファイル一覧を取得・選択（サブフォルダ対応）
* ✅ **リアルタイム進捗**: 検索の進捗をリアルタイム表示
* ✅ **結果エクスポート**: CSV/JSON形式で保存（Pro版）

## 🆓 フリー版 vs Pro版（準備中）

| 項目 | フリー版 | Pro版 |
|------|---------|-------|
| ファイルサイズ | 100MB/ファイルまで | **無制限** |
| 同時検索 | 最大5ファイル | **無制限** |
| 検索結果 | 最大1000件 | **無制限** |
| エクスポート機能 | ❌ 使用不可 | ✅ CSV/JSON |
| カラム指定検索 | ❌ 使用不可 | ✅ 列番号/列名で指定 |
| お気に入り機能 | ❌ 使用不可 | ✅ グループ化・名前付き登録 |

## 💎 Pro版について

Pro版は**近日公開予定**です。

### Pro版の主な機能

**基本機能の拡張**
- 無制限のファイル検索（ファイル数・サイズの制限なし）
- CSV/JSONエクスポート

**高度な検索**
- カラム指定検索: 特定の列のみを検索対象に

**便利機能**
- お気に入り登録: フォルダ/ファイル/URLをグループ化して管理

最新情報は[Discussions](https://github.com/6EFB0D/ZipSearch/discussions/categories/announce)でご確認ください。

## 📦 インストール

### Windows版（インストーラ）

1. [リリースページ](https://github.com/6EFB0D/ZipSearch/releases)から最新のインストーラをダウンロード
2. インストーラを実行してインストール
3. デスクトップまたはスタートメニューからZipSearchを起動

**注意**: Python環境の構築は不要です。すべての依存関係がインストーラに含まれています。

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

## 📖 詳細ドキュメント

* [お知らせ](https://github.com/6EFB0D/ZipSearch/discussions/categories/announce)
* [使い方ガイド](https://github.com/6EFB0D/ZipSearch/wiki)
* [Q&A](https://github.com/6EFB0D/ZipSearch/discussions/categories/q-a)
* [機能リクエスト](https://github.com/6EFB0D/ZipSearch/discussions/categories/ideas)

## 🤝 サポート

* バグ報告: [Issues](https://github.com/6EFB0D/ZipSearch/issues)
* 質問・相談: [Discussions](https://github.com/6EFB0D/ZipSearch/discussions)

## 📄 ライセンス

MIT License - 詳細は [LICENSE](LICENSE) ファイルをご覧ください

Copyright (c) 2026 Goplan


