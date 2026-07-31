# إضافة MD إلى قائمة السياق في Windows

> **لغات الوثائق**: [简体中文](README.md) · [繁體中文](README-zh-TW.md) · [English](README-en.md) · [Русский](README-ru.md) · [日本語](README-ja.md) · [한국어](README-ko.md) · [Français](README-fr.md) · [Español](README-es.md) · **العربية**

يضيف خيار «ملف Markdown جديد (.md)» إلى قائمة النقر بزر الماوس الأيمن في مستكشف ملفات Windows.

## الميزات

بعد استيراد ملف التسجيل، يمكنك:

- النقر بزر الماوس الأيمن في أي مجلد → **جديد** → اختيار ملف Markdown
- ربط امتداد `.md` بنوع ملف Markdown

## طريقة الاستخدام

1. اختر ملف `.reg` المناسب للغة نظامك من الجدول أدناه
2. انقر نقرًا مزدوجًا على الملف
3. انقر **نعم** في مربع حوار التأكيد
4. اكتمل عند ظهور رسالة النجاح في إضافة التسجيل

لا حاجة لإعادة التشغيل. حدّث مستكشف الملفات أو أعد فتح المجلد لتطبيق التغييرات.

## إصدارات اللغة

| اللغة | الملف | اسم العرض في قائمة جديد |
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

جميع إصدارات اللغة تعمل بنفس الطريقة؛ يختلف فقط اسم عرض نوع الملف. أي إصدار يُنتج نفس النتيجة بعد الاستيراد.

## المتطلبات

- Windows 7 أو أحدث
- يتطلب تأكيد مسؤول (مطالبة UAC)

## تفاصيل التسجيل

تعدّل هذه الأداة مفاتيح التسجيل التالية:

```
HKEY_CLASSES_ROOT\.md
HKEY_CLASSES_ROOT\.md\ShellNew
HKEY_CLASSES_ROOT\MarkdownFile
```

على وجه التحديد:

- تسجيل امتداد `.md` ونوع MIME `text/markdown`
- تفعيل قائمة **جديد** عبر `ShellNew`
- تعيين اسم عرض نوع الملف في مستكشف الملفات

## إلغاء التثبيت

لإزالة هذه الميزة، أنشئ وشغّل ملف `.reg` بالمحتوى التالي (احفظه باسم `Remove-MD-Context-Menu.reg`):

```reg
Windows Registry Editor Version 5.00

[-HKEY_CLASSES_ROOT\.md\ShellNew]

[HKEY_CLASSES_ROOT\.md]
@=-
"Content Type"=-
"PerceivedType"=-

[-HKEY_CLASSES_ROOT\MarkdownFile]
```

> **ملاحظة**: إذا ربط برنامج آخر `.md` بنوع ملف مختلف، قد تحتاج إلى إعادة تعيين التطبيق الافتراضي بعد الإزالة.

## الترخيص

Apache-2.0 License
