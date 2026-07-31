# 將 MD 加入 Windows 右鍵選單

> **文件語言**：[简体中文](README.md) · **繁體中文** · [English](README-en.md) · [Русский](README-ru.md) · [日本語](README-ja.md) · [한국어](README-ko.md) · [Français](README-fr.md) · [Español](README-es.md) · [العربية](README-ar.md)

在 Windows 檔案總管的右鍵選單中新增「新增 Markdown 檔案（.md）」選項。

## 功能

匯入登錄檔後，你可以：

- 在任意資料夾空白處右鍵 → **新增** → 選擇 Markdown 檔案
- 將 `.md` 副檔名關聯為 Markdown 檔案類型

## 使用方法

1. 根據你的系統語言，選擇下方對應版本的 `.reg` 檔案
2. 雙擊該檔案
3. 在彈出的確認對話框中點擊 **是**
4. 看到「已成功新增到登錄檔」提示後即完成

無需重新啟動，重新整理檔案總管或重新開啟資料夾即可生效。

## 語言版本

| 語言 | 檔案 | 新增選單顯示名稱 |
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

各語言版本功能完全相同，僅檔案類型顯示名稱不同。任意版本匯入後效果一致。

## 系統需求

- Windows 7 及以上
- 需要系統管理員權限確認（UAC 提示）

## 登錄檔說明

本工具會修改以下登錄檔項目：

```
HKEY_CLASSES_ROOT\.md
HKEY_CLASSES_ROOT\.md\ShellNew
HKEY_CLASSES_ROOT\MarkdownFile
```

具體作用：

- 註冊 `.md` 副檔名及 MIME 類型 `text/markdown`
- 透過 `ShellNew` 啟用右鍵「新增」選單
- 設定檔案類型在檔案總管中的顯示名稱

## 解除安裝

如需移除此功能，可建立並執行以下內容的 `.reg` 檔案（儲存為 `Remove-MD-Context-Menu.reg`）：

```reg
Windows Registry Editor Version 5.00

[-HKEY_CLASSES_ROOT\.md\ShellNew]

[HKEY_CLASSES_ROOT\.md]
@=-
"Content Type"=-
"PerceivedType"=-

[-HKEY_CLASSES_ROOT\MarkdownFile]
```

> **注意**：如果系統中已有其他程式將 `.md` 關聯到不同檔案類型，解除安裝後可能需要重新設定預設開啟方式。

## 授權條款

Apache-2.0 License
