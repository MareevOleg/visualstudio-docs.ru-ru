---
title: Конструктор рабочих процессов - конструктора действия Rethrow
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Rethrow.UI
ms.assetid: 9cfa2eda-395f-4cf3-9154-83fadd4f7452
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2b1d1832a7c0c44abb1e8c97ec4c8265262d117e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49857553"
---
# <a name="rethrow-activity-designer"></a>Конструктор действия Rethrow

**Rethrow** конструктора действий используется для создания и настройки <xref:System.Activities.Statements.Rethrow> действия.

## <a name="the-rethrow-activity"></a>Действие Rethrow

Действие <xref:System.Activities.Statements.Rethrow> вызывает ранее вызванное исключение. Это действие может использоваться только в обработчике <xref:System.Activities.Statements.Catch> в действии <xref:System.Activities.Statements.TryCatch>.

### <a name="use-the-rethrow-activity-designer"></a>Использование конструктора действия ReThrow

Доступ **Rethrow** конструктора действий в **обработка ошибок** категории **элементов**. **Rethrow** конструктор действия можно перетащить из **элементов** и сбрасываться в область конструктора рабочих процессов, везде, где обычно размещаются действия, например внутри <xref:System.Activities.Statements.Sequence>. Удаление конструктора действий создает <xref:System.Activities.Statements.Rethrow> действие по умолчанию **DisplayName** для Throw. <xref:System.Activities.Activity.DisplayName%2A> Значение можно изменить в заголовке **Rethrow** конструктора действий, или в **DisplayName** поле таблицы свойств.

### <a name="the-rethrow-properties"></a>Свойства Rethrow

В следующей таблице показаны <xref:System.Activities.Statements.Rethrow> свойства и описывает их использование в конструкторе:

|Имя свойства|Обязательно|Использование|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Указывает необязательное понятное имя действия <xref:System.Activities.Statements.Rethrow>. По умолчанию используется Rethrow.|

## <a name="see-also"></a>См. также

- [Коллекция](../workflow-designer/collection-activity-designers.md)
- [Throw](../workflow-designer/throw-activity-designer.md)
- [TryCatch](../workflow-designer/trycatch-activity-designer.md)