---
title: Параметры, текстовый редактор, общие
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.TOOLSOPTIONSPAGES.TEXT_EDITOR.SQL_SERVER_TOOLS.GENERAL
- VS.ToolsOptionsPages.Text_Editor.All_Languages.General
- VS.ToolsOptionsPages.Text_Editor.RDL_Expression.General
- VS.ToolsOptionsPages.Text_Editor.SQL.General
- vs.toolsoptionspages.text_editor
- VS.ToolsOptionsPages.Text_Editor.XML.General
- VS.ToolsOptionsPages.Text_Editor.T-SQL80.General
- VS.ToolsOptionsPages.Text_Editor.CSS
- VS.ToolsOptionsPages.Text_Editor.Plain_Text.General
- VS.ToolsOptionsPages.Text_Editor.SQL_Script.General
- VS.ToolsOptionsPages.Text_Editor.CSharp.General
- VS.ToolsOptionsPages.Text_Editor.All_Languages
- VS.ToolsOptionsPages.Text_Editor.T-SQL7.General
- VS.ToolsOptionsPages.Text_Editor.Basic.General
- VS.ToolsOptionsPages.Text_Editor.T-SQL.General
- VS.ToolsOptionsPages.Text_Editor.F#.Tabs
- VS.ToolsOptionsPages.Text_Editor.F#
- VS.ToolsOptionsPages.Text_Editor.PL/SQL.General
- VS.ToolsOptionsPages.Text_Editor.C/C++.General
- VS.ToolsOptionsPages.Text_Editor.Plain_Text
- VS.ToolsOptionsPages.Text_Editor.HTML
- VS.ToolsOptionsPages.Text_Editor.XAML.General
- VS.ToolsOptionsPages.Text_Editor
- VS.ToolsOptionsPages.Text_Editor.F#.General
- VS.ToolsOptionsPages.Text_Editor.XOML.General
- VS.ToolsOptionsPages.Text_Editor.SQL
- vs.toolsoptionspages.text_editor.c/c++
- VS.ToolsOptionsPages.Text_Editor.SQL_Script
- VS.ToolsOptionsPages.Text_Editor.T-SQL90.General
- VS.ToolsOptionsPages.Text_Editor.General
- VS.ToolsOptionsPages.Text_Editor.CSharp
- VS.ToolsOptionsPages.Text_Editor.Python
- VS.ToolsOptionsPages.Text_Editor.R
helpviewer_keywords:
- Text Editor Options dialog box
- Code Editor
- Text Editor [Visual Studio]
- editors, global settings
ms.assetid: 4ac21e48-3243-4141-9058-7eaf12b3cde7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 75051013e38d4acf5339193cf9f80e6da6758284
ms.sourcegitcommit: dd839de3aa24ed7cd69f676293648c6c59c6560a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2018
ms.locfileid: "52388805"
---
# <a name="options-text-editor-general"></a>Параметры, текстовый редактор, общие

Это диалоговое окно позволяет изменять глобальные параметры для редактора кода и текста Visual Studio. Для вывода этого диалогового окна выберите пункт **Параметры** в меню **Сервис**, разверните папку **Текстовый редактор**, а затем щелкните **Общие**.

## <a name="settings"></a>Параметры

### <a name="drag-and-drop-text-editing"></a>Перетаскивание текста при редактировании

Если этот флажок установлен, вы можете переместить текст, выбрав и перетащив его мышью в другое расположение внутри текущего документа или в любой открытый документ.

### <a name="automatic-delimiter-highlighting"></a>Автоматически выделять разделители

Если этот флажок установлен, символы-разделители, отделяющие параметры или пары "элемент-значение", а также парные фигурные скобки, выделяются.

### <a name="track-changes"></a>Отслеживание изменений

При выборе редактора кода в поле выделения появляется желтая вертикальная линия, отмечающая код, который был изменен с момента последнего сохранения файла. При сохранении изменений вертикальные линии становятся зелеными.

### <a name="auto-detect-utf-8-encoding-without-signature"></a>Автоматически определять кодировку UTF-8 без сигнатуры

По умолчанию редактор определяет кодировку путем поиска меток порядка байтов или тегов наборов символов. Если их не удается найти в текущем документе, редактор кода пытается автоматически определить кодировку UTF-8 путем сканирования последовательностей байтов. Чтобы отключить автоматическое определение кодировки, снимите этот флажок.

## <a name="display"></a>Показать

### <a name="selection-margin"></a>Поле выделения

Если этот флажок установлен, вдоль левого края области текста редактора отображается вертикальное поле. Можно щелкнуть это поле, чтобы выделить всю строку текста, или щелкнуть и перетащить последовательные строки текста.

|Поле выделения включено|Поле выделения выключено|
| - | - |
|![Снимок экрана HTMLpageSelectionMarginOn](../../ide/reference/media/vxselmaron.gif)|![Снимок экрана HTMLpageSelectionMarginOff](../../ide/reference/media/vxselmaroff.gif)|

### <a name="indicator-margin"></a>Поле индикаторов

Если этот флажок установлен, за левым краем области текста редактора отображается вертикальное поле. Если щелкнуть это поле, отображаются значок и подсказка, связанные с текстом. Например, в поле индикаторов отображаются ярлыки точки останова или списка задач. Сведения в поле индикаторов не выводятся на печать.

### <a name="highlight-current-line"></a>Выделение текущей строки

Если этот флажок установлен, вокруг строки кода, в которой находится курсор, отображается серый квадрат.

## <a name="see-also"></a>См. также

- ["Параметры", "Текстовый редактор", "Все языки"](../../ide/reference/options-text-editor-all-languages.md)
- ["Параметры", "Текстовый редактор", "Все языки", "Вкладки"](../../ide/reference/options-text-editor-all-languages-tabs.md)
- ["Параметры", "Текстовый редактор", "Расширение файла"](../../ide/reference/options-text-editor-file-extension.md)
- [Определение и настройка сочетаний клавиш](../../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md)
- [Настройка редактора](../../ide/customizing-the-editor.md)
- [Использование технологии IntelliSense](../../ide/using-intellisense.md)