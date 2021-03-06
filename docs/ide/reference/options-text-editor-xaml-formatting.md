---
title: "\"Параметры\", \"Текстовый редактор\", XAML, \"Форматирование\""
ms.date: 10/29/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.XAML.Formatting.General
- VS.ToolsOptionsPages.Text_Editor.XAML.Formatting.Spacing
helpviewer_keywords:
- element spacing, XAML view settings
- attribute spacing, XAML view settings
- XAML view settings, auto-formatting events
- auto-formatting events, XAML view settings
- XAML view settings, tag wrapping
- XAML view settings, auto insert
- quotation mark style, XAML view settings
- XAML formatting, WPF Designer
- XAML view settings, Toolbox
- XAML view settings, element spacing
- default view, XAML view settings
- auto insert, XAML view settings
- XAML view settings, default view
- XAML view settings, quotation mark style
- tag wrapping, XAML view settings
- WPF Designer, XAML formatting
- XAML view settings, attribute spacing
ms.assetid: ad3820b1-0d94-4807-a74c-c3467ed973a2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 4686760625062fea7984cdc05386284f8f98c4ee
ms.sourcegitcommit: dd839de3aa24ed7cd69f676293648c6c59c6560a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2018
ms.locfileid: "52388992"
---
# <a name="options-text-editor-xaml-formatting"></a>"Параметры", "Текстовый редактор", XAML, "Форматирование"

Используйте страницу свойств **Форматирование** для настройки форматирования элементов и атрибутов в документах XAML. Чтобы открыть диалоговое окно **Параметры**, в меню **Сервис** выберите пункт **Параметры**. Чтобы открыть страницу свойств **Форматирование**, разверните узел **Текстовый редактор**  >  **XAML**  >  **Форматирование**.

## <a name="auto-formatting-events"></a>События автоформатирования

Автоматическое форматирование может возникать при обнаружении одного из следующих событий.

-   Ввод закрывающего тега или тега в краткой форме записи.

-   Ввод открывающего тега.

-   Вставка из буфера обмена.

-   Форматирование команд клавиатуры.

Можно указать, какие события инициируют автоматическое форматирование.

**При вводе закрывающего тега или тега в краткой форме записи**

Автоматическое форматирование происходит после ввода закрывающего тега или тега в краткой форме записи. Тег в краткой форме записи не имеет атрибутов, например `<Button />`.

**При вводе открывающего тега**

Автоматическое форматирование происходит после ввода открывающего тега.

**При вставке из буфера обмена**

Автоматическое форматирование происходит при вставке кода XAML из буфера обмена в представление XAML.

## <a name="quotation-mark-style"></a>Стиль кавычек

Этот параметр определяет заключение значений атрибутов в одинарные или двойные кавычки. Он используется в средстве автоматического форматирования и в функции автоматического завершения IntelliSense.

Установка этого параметра затрагивает только атрибуты, добавляемые впоследствии при помощи конструктора или вручную в представление XAML.

**Двойные кавычки (")**

Значения атрибутов заключаются в двойные кавычки.
`<Button Name="button1">Hello</Button>`

**Одинарные кавычки (')**

Значения атрибутов заключаются в одинарные кавычки.
`<Button Name='button1'>Hello</Button>`

## <a name="tag-wrapping"></a>Перенос тегов

Можно задать длину строки для переноса тегов. Если перенос тегов включен, любой добавляемый впоследствии код XAML (при помощи конструктора) будет соответствующим образом переноситься.

**Переносить теги, превосходящие указанную длину**

Указывает, будут ли строки переноситься при достижении длины строки, указанной значением параметра **Длина**.

**Длина**

Допустимое число символов в строке. При необходимости длина строк XAML может превышать указанную длину строк.

## <a name="attribute-spacing"></a>Интервалы между атрибутами

С помощью этого параметра можно настроить расположение атрибутов в документе XAML.

**Сохранять символы новой строки и пробелы между атрибутами**

Автоматическое форматирование не будет применяться к новым строкам и пробелам между атрибутами.

```xml
<Button Height="23"   Name="button1"
Width="75">Hello</Button>
```

**Вставлять только один пробел между атрибутами**

Атрибуты располагаются на одной строке. Соседние атрибуты отделяются одним пробелом. Применяются параметры переноса тегов.

```xml
<Button Height="23" Name="button1" Width="75">Hello</Button>
```

**Размещать каждый атрибут на отдельной строке**

Каждый атрибут располагается на отдельной строке, что бывает полезно при наличии большого количества атрибутов.

```xml
<Button
Height="23"
Name="button1"
Width="75">Hello</Button>
```

**Размещать первый атрибут на одной строке с открывающим тегом**

Если флажок установлен, первый атрибут будет размещаться в той же строке, что открывающий тег элемента.

```xml
<Button Height="23"
Name="button1"
Width="75">Hello</Button>
```

## <a name="element-spacing"></a>Интервалы между элементами

С помощью этого параметра можно настроить расположение элементов в документе XAML.

**Сохранять в содержимом символы новой строки**

Пустые строки в содержимом элемента не удаляются.

```xml
<Grid>


<Button Name="button1">Hello</Button>

</Grid>
```

**Свертывать в содержимом пустые строки в одну**

Пустые строки в содержимом элемента будут свернуты в одну строку.

```xml
<Grid>

<Button Name="button1">Hello</Button>

</Grid>
```

**Удалять в содержимом пустые строки**

В содержимом элемента будут удаляться все пустые строки.

```xml
<Grid>
<Button Name="button1">Hello</Button>
</Grid>
```

## <a name="see-also"></a>См. также

- [XAML в WPF](/dotnet/framework/wpf/advanced/xaml-in-wpf)