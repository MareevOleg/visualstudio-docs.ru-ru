---
title: Конструктор рабочих процессов - RemoveFromCollection&lt;T&gt; конструктора действий
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.RemoveFromCollection`1.UI
ms.assetid: 6617ba26-c8bc-4aed-b746-112bf490d288
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 415d03ffda6bbd2e839354b4f7cb143337ab08c8
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49891366"
---
# <a name="removefromcollectiont-activity-designer"></a>RemoveFromCollection\<T > конструктора действий

**RemoveFromCollection\<T >** конструктора действий используется для создания и настройки <xref:System.Activities.Statements.RemoveFromCollection%601> действия.

## <a name="the-removefromcollectiontactivity"></a>RemoveFromCollection\<T > действия

Действие <xref:System.Activities.Statements.RemoveFromCollection%601> удаляет указанный элемент из определенной коллекции.

### <a name="using-the-removefromcollectiont-activity-designer"></a>С помощью RemoveFromCollection\<T > конструктора действий

Доступ **RemoveFromCollection\<T >** конструктора действий в **коллекции** категории **элементов**.
**RemoveFromCollection\<T >** конструктор действия можно перетащить из **элементов** и сбрасываться в область конструктора рабочих процессов, везде, где обычно размещаются действия, такие как внутри <xref:System.Activities.Statements.Sequence>. При этом создается <xref:System.Activities.Statements.RemoveFromCollection%601> действие по умолчанию <xref:System.Activities.Activity.DisplayName%2A> из RemoveFromCollection < Int32\>. <xref:System.Activities.Activity.DisplayName%2A> Значение можно изменить в заголовке **RemoveFromCollection < T\>**  конструктора действий или в **DisplayName** поле таблицы свойств. Другие свойства следует изменять в таблице свойств.

### <a name="the-removefromcollectiont-properties"></a>RemoveFromCollection < T\> свойства

В следующей таблице показаны <xref:System.Activities.Statements.RemoveFromCollection%601> свойства и показывается, как они используются в конструкторе:

|Имя свойства|Обязательно|Использование|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Необязательное понятное имя действия <xref:System.Activities.Statements.RemoveFromCollection%601>. Значение по умолчанию — RemoveFromCollection < Int32\>.<br /><br /> Несмотря на то что свойство <xref:System.Activities.Activity.DisplayName%2A> не является обязательным, его все же рекомендуется использовать.|
|<xref:System.Activities.Statements.RemoveFromCollection%601.Item%2A>|Да|Элемент, удаляемый из **коллекции\<T >**. Этот элемент имеет тип *T*, который имеет тип *TypeArgument*. Чтобы указать элемент, введите выражение Visual Basic в таблице свойств.|
|<xref:System.Activities.Statements.RemoveFromCollection%601.Collection%2A>|Да|Коллекция, из которой должен быть удален элемент. Эта коллекция имеет тип **ICollection < TypeArgument\>.** Чтобы указать коллекцию, введите выражение Visual Basic в сетке свойств.|
|*TypeArgument*|Да|Тип T элементов, содержащихся в коллекции <xref:System.Collections.Generic.ICollection%601>. По умолчанию это *TypeArgument* установлен тип **Int32**. Чтобы изменить тип, измените значение *TypeArgument* в поле со списком в сетке свойств.|
|<xref:System.Activities.Activity%601.Result%2A>|False|Значение, которое указывает, удален ли из коллекции указанный объект. Чтобы указать переменную, к которой необходимо привязать результат, введите переменную в таблицу свойств.|

## <a name="see-also"></a>См. также

- [Коллекция](../workflow-designer/collection-activity-designers.md)
- [AddToCollection\<T >](../workflow-designer/addtocollection-t-activity-designer.md)
- [ClearCollection\<T >](../workflow-designer/clearcollection-t-activity-designer.md)
- [ExistsInCollection\<T >](../workflow-designer/existsincollection-t-activity-designer.md)