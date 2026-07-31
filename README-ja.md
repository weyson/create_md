# Windows 右クリックメニューに MD を追加

> **ドキュメントの言語**：[简体中文](README.md) · [繁體中文](README-zh-TW.md) · [English](README-en.md) · [Русский](README-ru.md) · **日本語** · [한국어](README-ko.md) · [Français](README-fr.md) · [Español](README-es.md) · [العربية](README-ar.md)

Windows エクスプローラーの右クリックメニューに「新規 Markdown ファイル（.md）」オプションを追加します。

## 機能

レジストリファイルをインポートすると、次のことができます：

- 任意のフォルダーで右クリック → **新規作成** → Markdown ファイルを選択
- `.md` 拡張子を Markdown ファイルタイプに関連付け

## 使い方

1. 下の表からシステム言語に対応する `.reg` ファイルを選択
2. ファイルをダブルクリック
3. 確認ダイアログで **はい** をクリック
4. 「レジストリに正常に追加されました」と表示されたら完了

再起動は不要です。エクスプローラーを更新するか、フォルダーを開き直してください。

## 言語バージョン

| 言語 | ファイル | 新規メニュー表示名 |
|------|------|------------------|
| 简体中文 | `添加MD右键.reg` | MD 文件 |
| 繁体中文 | `添加MD右鍵-繁體中文.reg` | MD 檔案 |
| English | `Add-MD-Context-Menu-en.reg` | MD File |
| Русский | `Add-MD-Context-Menu-ru.reg` | Файл MD |
| 日本語 | `Add-MD-Context-Menu-ja.reg` | MD ファイル |
| 한국어 | `Add-MD-Context-Menu-ko.reg` | MD 파일 |
| Français | `Add-MD-Context-Menu-fr.reg` | Fichier MD |
| Español | `Add-MD-Context-Menu-es.reg` | Archivo MD |
| العربية | `Add-MD-Context-Menu-ar.reg` | ملف MD |

すべての言語バージョンは機能が同じで、ファイルタイプの表示名のみ異なります。どのバージョンをインポートしても同じ結果になります。

## システム要件

- Windows 7 以降
- 管理者権限の確認が必要（UAC プロンプト）

## レジストリの詳細

このツールは次のレジストリキーを変更します：

```
HKEY_CLASSES_ROOT\.md
HKEY_CLASSES_ROOT\.md\ShellNew
HKEY_CLASSES_ROOT\MarkdownFile
```

具体的には：

- `.md` 拡張子と MIME タイプ `text/markdown` を登録
- `ShellNew` により右クリックの **新規作成** メニューを有効化
- エクスプローラーでのファイルタイプ表示名を設定

## アンインストール

この機能を削除するには、次の内容の `.reg` ファイルを作成して実行してください（`Remove-MD-Context-Menu.reg` として保存）：

```reg
Windows Registry Editor Version 5.00

[-HKEY_CLASSES_ROOT\.md\ShellNew]

[HKEY_CLASSES_ROOT\.md]
@=-
"Content Type"=-
"PerceivedType"=-

[-HKEY_CLASSES_ROOT\MarkdownFile]
```

> **注意**：他のプログラムが `.md` を別のファイルタイプに関連付けている場合、アンインストール後に既定のアプリを再設定する必要がある場合があります。

## ライセンス

Apache-2.0 License
