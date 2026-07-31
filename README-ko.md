# Windows 컨텍스트 메뉴에 MD 추가

> **문서 언어**: [简体中文](README.md) · [繁體中文](README-zh-TW.md) · [English](README-en.md) · [Русский](README-ru.md) · [日本語](README-ja.md) · **한국어** · [Français](README-fr.md) · [Español](README-es.md) · [العربية](README-ar.md)

Windows 파일 탐색기의 오른쪽 클릭 메뉴에 「새 Markdown 파일(.md)」 옵션을 추가합니다.

## 기능

레지스트리 파일을 가져온 후 다음을 할 수 있습니다:

- 아무 폴더에서 오른쪽 클릭 → **새로 만들기** → Markdown 파일 선택
- `.md` 확장자를 Markdown 파일 형식에 연결

## 사용 방법

1. 아래 표에서 시스템 언어에 맞는 `.reg` 파일을 선택
2. 해당 파일을 더블 클릭
3. 확인 대화 상자에서 **예** 클릭
4. 「레지스트리에 성공적으로 추가되었습니다」 메시지가 표시되면 완료

재시작이 필요 없습니다. 파일 탐색기를 새로 고치거나 폴더를 다시 열면 적용됩니다.

## 언어 버전

| 언어 | 파일 | 새로 만들기 메뉴 표시 이름 |
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

모든 언어 버전의 기능은 동일하며, 파일 형식 표시 이름만 다릅니다. 어떤 버전을 가져와도 동일한 결과가 적용됩니다.

## 시스템 요구 사항

- Windows 7 이상
- 관리자 권한 확인 필요(UAC 프롬프트)

## 레지스트리 세부 정보

이 도구는 다음 레지스트리 키를 수정합니다:

```
HKEY_CLASSES_ROOT\.md
HKEY_CLASSES_ROOT\.md\ShellNew
HKEY_CLASSES_ROOT\MarkdownFile
```

구체적으로:

- `.md` 확장자 및 MIME 유형 `text/markdown` 등록
- `ShellNew`를 통해 오른쪽 클릭 **새로 만들기** 메뉴 활성화
- 파일 탐색기에서 파일 형식 표시 이름 설정

## 제거

이 기능을 제거하려면 다음 내용의 `.reg` 파일을 만들어 실행하세요(`Remove-MD-Context-Menu.reg`로 저장):

```reg
Windows Registry Editor Version 5.00

[-HKEY_CLASSES_ROOT\.md\ShellNew]

[HKEY_CLASSES_ROOT\.md]
@=-
"Content Type"=-
"PerceivedType"=-

[-HKEY_CLASSES_ROOT\MarkdownFile]
```

> **참고**: 다른 프로그램이 `.md`를 다른 파일 형식에 연결한 경우, 제거 후 기본 앱을 다시 설정해야 할 수 있습니다.

## 라이선스

Apache-2.0 License
