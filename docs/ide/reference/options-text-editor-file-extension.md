---
title: "\"Параметры\", \"Текстовый редактор\", \"Расширение файла\" | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.toolsoptionspages.text_editor.file_extension
helpviewer_keywords:
- file extensions, associating to editor
- Editing Experience
- Options dialog box
- Editing Experience, selecting
ms.assetid: 05298fc5-fc4e-4bb2-b942-1f7d2dcdff0f
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 5ea9179ad37514ffad4876177b05150eecc22def
ms.openlocfilehash: 37e5b813482eae6c4d46051ed4b261594d9e5164
ms.contentlocale: ru-ru
ms.lasthandoff: 05/24/2017

---
# <a name="options-text-editor-file-extension"></a>"Параметры", "Текстовый редактор", "Расширение файла"
Это диалоговое окно параметров позволяет задать способ обработки файлов с определенными расширениями в интегрированной среде разработки Visual Studio (IDE). Для каждого введенного **расширения** можно выбрать соответствующий редактор. Это дает возможность выбрать редактор или конструктор интегрированной среды разработки, в котором будут открываться документы определенного типа. Чтобы отобразить эти параметры, выберите в меню **Сервис** пункт **Параметры**, разверните узел **Текстовый редактор**, а затем выберите **расширение файла**.  
  
 При выборе варианта "с кодировкой" при каждом открытии документа этого типа будет отображаться диалоговое окно, в котором можно выбрать схему кодировки для этого документа. Это может быть удобно при подготовке версий документов проекта, которые будут использоваться для других платформ или других целевых языков.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](../../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **Расширение**  
 Введите расширение файла, для которого требуется определить редактор в интегрированной среде разработки.  
  
 **Редактор**  
 Выберите редактор или конструктор интегрированной среды разработки, в котором будут открываться файлы с этим расширением. При выборе варианта "с кодировкой" при каждом открытии документа этого типа будет отображаться диалоговое окно, в котором можно выбрать схему кодировки.  
  
 **Добавить**  
 Добавляет запись, включающую указанное **расширение** и **использование редакторов** в список расширений.  
  
 **Remove**  
 Удаляет выбранную запись из списка расширений.  
  
 Список расширений  
 Список всех расширений, для которых задано использование редакторов  
  
 **Сопоставить файлы без расширений с**  
 Выберите этот вариант, если вы хотите указать, как файлы без расширений будут обрабатываться в интегрированной среде разработки.  
  
 **Параметры файлов без расширений**  
 Предоставляет такой же список, что и **Редактор**. Выберите редактор или конструктор интегрированной среды разработки, в котором будут открываться файлы без расширений.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Управление режимами редактора](../../ide/how-to-manage-editor-modes.md)