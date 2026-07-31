# Add MD to Windows Context Menu

> **Documentation Languages**: [简体中文](README.md) · [繁體中文](README-zh-TW.md) · **English** · [Русский](README-ru.md) · [日本語](README-ja.md) · [한국어](README-ko.md) · [Français](README-fr.md) · [Español](README-es.md) · [العربية](README-ar.md)

Add a "New Markdown File (.md)" option to the right-click menu in Windows File Explorer.

## Features

After importing the registry file, you can:

- Right-click in any folder → **New** → select Markdown file
- Associate the `.md` extension with the Markdown file type

## Usage

1. Choose the `.reg` file for your system language from the table below
2. Double-click the file
3. Click **Yes** in the confirmation dialog
4. Done when you see the "successfully added to the registry" message

No restart required. Refresh File Explorer or reopen the folder for changes to take effect.

## Language Versions

| Language | File | New Menu Display Name |
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

All language versions work identically; only the file type display name differs. Any version produces the same result after import.

## Requirements

- Windows 7 or later
- Administrator confirmation required (UAC prompt)

## Registry Details

This tool modifies the following registry keys:

```
HKEY_CLASSES_ROOT\.md
HKEY_CLASSES_ROOT\.md\ShellNew
HKEY_CLASSES_ROOT\MarkdownFile
```

Specifically:

- Registers the `.md` extension and MIME type `text/markdown`
- Enables the right-click **New** menu via `ShellNew`
- Sets the file type display name in File Explorer

## Uninstall

To remove this feature, create and run a `.reg` file with the following content (save as `Remove-MD-Context-Menu.reg`):

```reg
Windows Registry Editor Version 5.00

[-HKEY_CLASSES_ROOT\.md\ShellNew]

[HKEY_CLASSES_ROOT\.md]
@=-
"Content Type"=-
"PerceivedType"=-

[-HKEY_CLASSES_ROOT\MarkdownFile]
```

> **Note**: If another program has associated `.md` with a different file type, you may need to reset the default app after uninstalling.

## License

Apache-2.0 License
