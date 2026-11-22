# ArkLidFind - アーカイブログ横断検索ツール

**バージョン**: 1.0.12（商用・prerelease）  
**製品ページ**: https://office-goplan.com/zipsearch  
**サポート**: support@office-goplan.com ／ [お問い合わせフォーム](https://docs.google.com/forms/d/1NpXzk1kyUn2LhUzQhhMHq_tnT1oOGAsv561L-7nMfos/viewform)

ZIP・ローカル・HTTP(S) 上のログや CSV を、**展開せずに横断検索**できる Windows 向けツールです。主製品は **GUI** です。

> **log4net の過去ログを、ZIP のまま、複数ファイル横断で、ERROR と時刻で絞り込む。**

リアルタイム監視ではなく、**保守・障害調査・納品ログ確認**に特化しています。Pro では **log4net ログ解析**で、.NET アプリの過去ログを Level / Logger / 日時で構造化して調査できます。

## こんなときに ArkLidFind

- 障害時刻の前後を ERROR / WARN で素早く絞り込みたい
- `app.log` と `app.log.1` など **Rolling ログをまとめて**追いたい
- **ZIP に封入されたログ**を解凍せずに検索したい
- **HTTP(S) 上の ZIP ログ**を URL 指定で直接調べたい
- 調査結果を CSV / JSON で共有したい（Pro）

## どんな調査に向いているか

| やりたいこと | ArkLidFind でできること |
|--------------|------------------------|
| 過去ログを log4net の Level / Logger で絞る | **◎** Pro の列解析・フィルタ |
| ZIP ログを展開せず横断検索 | **◎** 非展開で ZIP 内を検索 |
| 社内 URL の ZIP ログを直接調べる | **◎** HTTP(S) 対応 |
| ローテーション済み .log を一括追跡 | **◎** Rolling 兄弟横断（Pro） |
| 稼働中アプリの常時リアルタイム監視 | 対象外（出力済みログの調査向け） |
| 巨大 1 ファイルの精読・編集 | 対象外（横断・絞り込み調査向け） |

## 特徴

* ✅ **アーカイブ横断**: ZIP / HTTP(S) を**非展開**で検索
* ✅ **log4net 解析**（Pro）: PatternLayout 列解析・Level/Logger フィルタ・スタックトレース統合
* ✅ **Rolling 横断**（Pro）: `app.log` + `.log.1` 等を一括検索
* ✅ **複数形式**: ZIP, CSV, TSV, TXT, `.log`, Excel（Pro）
* ✅ **結果エクスポート**: CSV/JSON（Pro）
* ✅ **クロス集計**（Pro）: 検索ヒットの集計表・xlsx グラフ

## Free と Pro

| 項目 | Free | Pro（買い切り） |
|------|------|----------------|
| 価格 | 無償 | **¥9,980（税込）・1 ライセンス 1 台** |
| ファイルサイズ | **10 MB**/ファイルまで | **無制限** |
| 同時検索 | 最大 5 ファイル | **無制限** |
| 検索結果 | 最大 10 件 | **無制限** |
| log4net ログ解析 | ❌（`.log` 行検索のみ） | ✅ |
| INI / JSON / KV 構造化 | ❌（行検索のみ） | ✅ |
| サブフォルダ再帰 | ❌ | ✅ |
| エクスポート / 高度な絞り込み / 集計 | ❌ | ✅ |
| 検索速度 | シングルスレッド | **マルチスレッド** |

制限に当たった画面では、その場で Free の範囲を案内します（黙って切れません）。

## Pro について

**¥9,980（税込・買い切り）** — 1 ライセンス 1 台

- log4net 列解析・Rolling 横断・ZIP / HTTP(S) 非展開検索
- ファイル数・サイズ・結果件数の制限解除、並列検索
- CSV/JSON エクスポート、値フィルタ・範囲検索、クロス集計 など

購入はアプリ内「ヘルプ」→「ライセンス」から（Stripe Checkout）。法人・複数台はお問い合わせください。

利用規約・プライバシーポリシー: https://office-goplan.com/terms-of-service ／ https://office-goplan.com/privacy-policy  
（製品同梱の `TERMS_OF_USE.txt` も参照。案内用 GitHub リポジトリの MIT License は **リポジトリ文書用**であり、本ソフトウェア本体の利用許諾ではありません。）

## インストール

1. [リリースページ](https://github.com/6EFB0D/ZipSearch/releases)下部の **Assets** から  
   `ArkLidFind-1.0.12-prod-setup.exe`（または案内の **setup.zip**）をダウンロード  
   ※ Source code の zip/tar はインストーラではありません
2. **ArkLidFind を終了してから** セットアップを実行する
3. **利用規約に同意**したうえでインストールする
4. デスクトップまたはスタートメニューの **ArkLidFind** から起動

**NTFS**（C:、既定のユーザーフォルダなど）: 終了してから setup すれば **上書きインストール**できます。

**exFAT**（一部の D: や外付け）: セットアップが **警告と手順**を出します（インストールは止めません）。終了 → 必要なら再起動 → インストール先を手動削除 → setup、の順をお勧めします。既定の NTFS フォルダへの変更を推奨します。

Python の別途インストールは不要です。

### うまくいかないとき（SmartScreen 等）

1. Assets から **setup.zip** をダウンロードして解凍
2. 中の setup.exe を実行
3. 警告時は **「詳細情報」→「実行」**

## 使い方（GUI）

1. **検索パス**を指定（ZIP またはフォルダ／URL）
2. **検索キーワード**を入力
3. 必要に応じてオプションを設定
4. **検索開始**

詳しくはアプリ内「ヘルプ」→「取扱説明書」（F1）を参照してください。

## サンプルデータ

インストール先の `sample_data`（スタートメニュー → サンプルデータ）に、動作確認用の ZIP / CSV を同梱しています。各フォルダの README に手順があります。期限付きの自動試用（14日試用等）は設けていません。

## サポート

* 製品ページ: https://office-goplan.com/zipsearch  
* メール: support@office-goplan.com
* [お問い合わせフォーム](https://docs.google.com/forms/d/1NpXzk1kyUn2LhUzQhhMHq_tnT1oOGAsv561L-7nMfos/viewform)

## ライセンス表記

- **製品の利用条件**: 同梱 `TERMS_OF_USE.txt` およびサイト利用規約
- **案内用リポジトリ**: [LICENSE](LICENSE)（MIT）— 上記のとおり本体許諾ではありません
- **オープンソース帰属**: 同梱 `OPEN_SOURCE_LICENSES.txt`

Copyright (c) 2025-2026 Office Go Plan

## ダウンロード

インストーラは [Releases](https://github.com/6EFB0D/ZipSearch/releases) の **Assets** から入手できます。SHA-256 チェックサムを同梱します。
