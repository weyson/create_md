# Ajouter MD au menu contextuel Windows

> **Langues de la documentation** : [简体中文](README.md) · [繁體中文](README-zh-TW.md) · [English](README-en.md) · [Русский](README-ru.md) · [日本語](README-ja.md) · [한국어](README-ko.md) · **Français** · [Español](README-es.md) · [العربية](README-ar.md)

Ajoute l'option « Nouveau fichier Markdown (.md) » au menu contextuel de l'Explorateur de fichiers Windows.

## Fonctionnalités

Après l'importation du fichier de registre, vous pouvez :

- Clic droit dans n'importe quel dossier → **Nouveau** → sélectionner Fichier Markdown
- Associer l'extension `.md` au type de fichier Markdown

## Utilisation

1. Choisissez le fichier `.reg` correspondant à la langue de votre système dans le tableau ci-dessous
2. Double-cliquez sur le fichier
3. Cliquez sur **Oui** dans la boîte de dialogue de confirmation
4. Terminé lorsque le message de succès d'ajout au registre s'affiche

Aucun redémarrage requis. Actualisez l'Explorateur ou rouvrez le dossier pour appliquer les changements.

## Versions linguistiques

| Langue | Fichier | Nom affiché dans le menu Nouveau |
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

Toutes les versions linguistiques fonctionnent de la même manière ; seul le nom affiché du type de fichier diffère. Toute version produit le même résultat après importation.

## Configuration requise

- Windows 7 ou version ultérieure
- Confirmation administrateur requise (invite UAC)

## Détails du registre

Cet outil modifie les clés de registre suivantes :

```
HKEY_CLASSES_ROOT\.md
HKEY_CLASSES_ROOT\.md\ShellNew
HKEY_CLASSES_ROOT\MarkdownFile
```

En particulier :

- Enregistre l'extension `.md` et le type MIME `text/markdown`
- Active le menu contextuel **Nouveau** via `ShellNew`
- Définit le nom affiché du type de fichier dans l'Explorateur

## Désinstallation

Pour supprimer cette fonctionnalité, créez et exécutez un fichier `.reg` avec le contenu suivant (enregistrez sous `Remove-MD-Context-Menu.reg`) :

```reg
Windows Registry Editor Version 5.00

[-HKEY_CLASSES_ROOT\.md\ShellNew]

[HKEY_CLASSES_ROOT\.md]
@=-
"Content Type"=-
"PerceivedType"=-

[-HKEY_CLASSES_ROOT\MarkdownFile]
```

> **Remarque** : si un autre programme a associé `.md` à un type de fichier différent, vous devrez peut-être réinitialiser l'application par défaut après la désinstallation.

## Licence

Apache-2.0 License
