# Agregar MD al menú contextual de Windows

> **Idiomas de la documentación**: [简体中文](README.md) · [繁體中文](README-zh-TW.md) · [English](README-en.md) · [Русский](README-ru.md) · [日本語](README-ja.md) · [한국어](README-ko.md) · [Français](README-fr.md) · **Español** · [العربية](README-ar.md)

Agrega la opción «Nuevo archivo Markdown (.md)» al menú contextual del Explorador de archivos de Windows.

## Características

Después de importar el archivo de registro, puedes:

- Clic derecho en cualquier carpeta → **Nuevo** → seleccionar archivo Markdown
- Asociar la extensión `.md` con el tipo de archivo Markdown

## Uso

1. Elige el archivo `.reg` de tu idioma del sistema en la tabla siguiente
2. Haz doble clic en el archivo
3. Haz clic en **Sí** en el cuadro de diálogo de confirmación
4. Listo cuando veas el mensaje de éxito al agregar al registro

No se requiere reinicio. Actualiza el Explorador o vuelve a abrir la carpeta para que surta efecto.

## Versiones de idioma

| Idioma | Archivo | Nombre en el menú Nuevo |
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

Todas las versiones de idioma funcionan igual; solo difiere el nombre mostrado del tipo de archivo. Cualquier versión produce el mismo resultado tras la importación.

## Requisitos

- Windows 7 o posterior
- Se requiere confirmación de administrador (aviso UAC)

## Detalles del registro

Esta herramienta modifica las siguientes claves del registro:

```
HKEY_CLASSES_ROOT\.md
HKEY_CLASSES_ROOT\.md\ShellNew
HKEY_CLASSES_ROOT\MarkdownFile
```

En concreto:

- Registra la extensión `.md` y el tipo MIME `text/markdown`
- Habilita el menú contextual **Nuevo** mediante `ShellNew`
- Establece el nombre mostrado del tipo de archivo en el Explorador

## Desinstalación

Para eliminar esta función, crea y ejecuta un archivo `.reg` con el siguiente contenido (guárdalo como `Remove-MD-Context-Menu.reg`):

```reg
Windows Registry Editor Version 5.00

[-HKEY_CLASSES_ROOT\.md\ShellNew]

[HKEY_CLASSES_ROOT\.md]
@=-
"Content Type"=-
"PerceivedType"=-

[-HKEY_CLASSES_ROOT\MarkdownFile]
```

> **Nota**: si otro programa ha asociado `.md` con un tipo de archivo diferente, es posible que debas restablecer la aplicación predeterminada tras desinstalar.

## Licencia

Apache-2.0 License
