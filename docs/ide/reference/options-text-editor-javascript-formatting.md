---
title: "\"Параметры\", \"Текстовый редактор\", JavaScript, \"Форматирование\""
ms.date: 10/29/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.JavaScript.Formatting.Spacing
- VS.ToolsOptionsPages.Text_Editor.JavaScript.Formatting.General
- VS.ToolsOptionsPages.Text_Editor.JavaScript.Formatting.New_Lines
- VS.ToolsOptionsPages.Text_Editor.TypeScript.Formatting.Spacing
- VS.ToolsOptionsPages.Text_Editor.TypeScript.Formatting.General
- VS.ToolsOptionsPages.Text_Editor.TypeScript.Formatting.New_Lines
ms.assetid: 28a0aef1-9353-4d94-95a5-54b42e15c0dc
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aa846a25e1383c0c164dfb4747899f5e86237d32
ms.sourcegitcommit: be938c7ecd756a11c9de3e6019a490d0e52b4190
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50671057"
---
# <a name="options-text-editor-javascript-formatting"></a>"Параметры", "Текстовый редактор", JavaScript, "Форматирование"
Используйте страницу **Форматирование** диалогового окна **Параметры** для задания параметров форматирования для кода в редакторе кода. Чтобы открыть эту страницу, выберите в меню **Сервис** пункт **Параметры**, а затем разверните узел **Текстовый редактор**, **JavaScript** и **Форматирование**.

[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]

## <a name="automatic-formatting"></a>Автоматическое форматирование
 Эти параметры определяют условия, при которых выполняется форматирование в представлении **Источник**.

### <a name="uielement-list"></a>Список элементов пользовательского интерфейса

|Параметр|Описание:|
|------------|-----------------|
|**Форматировать завершенную строку по нажатию клавиши ВВОД**|Если этот параметр выбран, редактор кода автоматически форматирует строку при нажатии клавиши ВВОД.|
|**Форматировать завершенный оператор по вводу ;**|Если этот параметр выбран, редактор кода автоматически форматирует строку при нажатии клавиши с точкой с запятой.|
|**Форматировать открытый блок по вводу {**|Если этот параметр выбран, редактор кода автоматически форматирует строку при нажатии клавиши с открывающей фигурной скобкой.|
|**Форматировать завершенный блок по вводу }**|Если этот параметр выбран, редактор кода автоматически форматирует строку при нажатии клавиши с закрывающей фигурной скобкой.|
|**Форматировать по операции вставки**|Если этот параметр выбран, редактор кода выполняет повторное форматирование кода при вставке его в редактор. Редактор использует текущие определенные правила форматирования. Если этот параметр не выбран, редактор использует исходное форматирование вставленного кода.|

## <a name="new-lines"></a>Новые строки
 Эти параметры определяют, помещает ли редактор кода открывающую скобку для функций и управляющих блоков на новой строке.

### <a name="uielement-list"></a>Список элементов пользовательского интерфейса

|Параметр|Описание:|
|------------|-----------------|
|**Помещать открывающую фигурную скобку на новой строке для функций**|Если выбран этот параметр, редактор кода перемещает открывающую скобку, связанную с функцией, на новую строку.|
|**Помещать открывающую фигурную скобку на новой строке для блоков управления**|Если выбран этот параметр, редактор кода перемещает открывающую скобку, связанную с блоком управления (например, с блоками управления `if` и `while`), на новую строку.|

## <a name="spacing"></a>Интервал
 Эти параметры определяют, как вставляются пробелы в представлении **Источник**.

### <a name="uielement-list"></a>Список элементов пользовательского интерфейса

|Параметр|Описание:|
|------------|-----------------|
|**Вставлять пробел после разделителя-запятой**|Если выбран этот параметр, редактор кода добавляет пробел после разделителя-запятой.|
|**Вставлять пробел после точки с запятой в операторах for**|Если выбран этот параметр, редактор кода добавляет пробел после каждой точки с запятой в первой строке цикла `for`.|
|**Вставлять пробел до и после бинарных операторов**|Если выбран этот параметр, редактор кода добавляет пробел до и после бинарных операторов (например, +, -, &&, &#124;&#124;).|
|**Вставлять пробел после ключевых слов в операторах потока управления**|Если выбран этот параметр, редактор кода добавляет пробел после ключевых слов JavaScript в операторах потока управления.|
|**Вставлять пробел после ключевого слова function для анонимных функций**|Если выбран этот параметр, редактор кода добавляет пробел после ключевого слова `function` для анонимных функций.|
|**Вставлять пробел после открывающих и перед закрывающими непустыми скобками**|Если выбран этот параметр, редактор кода добавляет пробел после открывающей скобки и перед закрывающей скобкой при наличии непустых символов в скобках.|

## <a name="see-also"></a>См. также

- [Страница "Общие", папка "Среда", диалоговое окно "Параметры"](../../ide/reference/general-environment-options-dialog-box.md)