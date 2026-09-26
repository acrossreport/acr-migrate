# ACR Migrate

ActiveReports (RPX) および Microsoft RDL/RDLC のレポート定義ファイルを、[ACR (Across Report Renderer)](https://acrossreport.com) のレポート定義ファイル(`.acr`)に変換するツール集です。

対応する2つの変換ツールを、Windows 版バイナリとして配布しています。

| ツール | 変換元 | 精度 |
|--------|--------|------|
| `rpx2json.exe` | ActiveReports の `.rpx` | 高精度(絶対座標のため、位置調整はほぼ不要) |
| `rdl2json.exe` | Microsoft RDL / RDLC の `.rdlc` | ベストエフォート(表形式の要素は推定座標。ACR Designer での位置調整が前提) |

いずれも無償・再配布自由です。ソースコードは非公開ですが、実行・配布に制限はありません。

---

## 対応環境

Windows のみ(x64)。変換元となる ActiveReports Designer / RDL デザイナー自体が Windows 版のみのため、当面 Windows 以外の対応予定はありません。

---

## ダウンロード

[Releases](../../releases) から、最新版の zip をダウンロードしてください。展開するだけで使えます。インストール作業は不要です。

---

## 使い方

### rpx2json.exe(ActiveReports RPX から変換)

```
rpx2json.exe 入力ファイル.rpx
```

同じフォルダに、同名の `.acr` ファイルが作成されます。

```
rpx2json.exe Report.rpx
# → Report.acr が作成されます
```

RPX はセクション内で絶対座標を持つ形式のため、変換後の位置調整はほとんど必要ありません。

### rdl2json.exe(Microsoft RDL/RDLC から変換)

```
rdl2json.exe 入力ファイル.rdlc
```

同じフォルダに、同名の `.acr` ファイルが作成されます。

```
rdl2json.exe report.rdlc
# → report.acr が作成されます
```

RDL は表形式(Tablix)の座標を実行時に解決する形式のため、変換後のファイルには推定座標である旨のマーカーが付きます。**ACR Designer で開き、レイアウトを確認・調整してください。** また、Subreport(サブレポート)は現在対応していません。

---

## 変換後のファイルを開くには

変換で作成された `.acr` ファイルは、[ACR Designer](https://acrossreport.com) で開いて、印刷・PDF出力・レイアウト調整ができます。ACR Designer をお持ちでない場合は、[acrossreport.com](https://acrossreport.com) からダウンロードしてください。

---

## サポートについて

無償でご利用いただけますが、動作保証やサポートはございません。移行作業でのご支援(変換後のレイアウト調整、大量データの一括移行など)をご希望の場合は、個別にサポート契約を承っております。お問い合わせは across.support@gmail.com まで。

---

## ライセンス

Copyright (C) 2026 Across Systems Corporation.

本ツールの実行・配布は自由に行っていただけます。逆コンパイル・改変は禁止します。詳細は同梱の LICENSE.txt をご覧ください。
