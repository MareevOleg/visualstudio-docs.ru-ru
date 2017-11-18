---
title: "&lt;Расписания&gt; элемент (загрузчик) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords: <Schedules> element [bootstrapper]
ms.assetid: 28d094cf-64f5-42b1-bd8a-3697082aab4f
caps.latest.revision: "5"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 104c187d373113e8e5dafe589af3995bef5c8cdc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2017
---
# <a name="ltschedulesgt-element-bootstrapper"></a>&lt;Расписания&gt; элемент (загрузчик)
`Schedules` Элемент содержит `Schedule` элементы, которые определяют времена команд, определенных с `Command` элемент должен выполняться.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
<Schedules>  
    <Schedule  
        Name  
    >  
        <BuildList />  
        <BeforePackage />  
        <AfterPackage />  
    </Schedule>  
</Schedules>  
```  
  
## <a name="elements-and-attributes"></a>Элементы и атрибуты  
 `Schedules` Элемент является дочерним элементом `Product` элемента. Каждый `Product` элемент может иметь не более одного `Schedules` элемента. `Schedules` Элемент не имеет атрибутов.  
  
## <a name="schedule"></a>Расписание  
 `Schedule` Элемент является дочерним элементом `Schedules` элемента. Объект `Schedules` элемент должен иметь по крайней мере один `Schedule` элемента.  
  
 `Schedule`имеет следующий атрибут.  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`Name`|Обязательный. Имя элемента расписания. Это соответствует `ScheduleName` свойство `Command` элемента. Когда `Command` ссылается на именованное расписание, он будет выполняться только во времени, указанного в этом `Schedule` элемента. Расписания также могут быть связаны с `FailIf` и `BypassIf` элементы, которые ограничивают эти условия выполнения по определенному расписанию. Дополнительные сведения см. в разделе [ \<команды > элемент](../deployment/commands-element-bootstrapper.md).|  
  
 Данный `Schedule` элемент может иметь только один из следующих дочерних элементов.  
  
## <a name="buildlist"></a>BuildList  
 `BuildList` Элемент указывает, что программа установки для выполнения команды, сразу после запуска приложение начальной загрузки.  
  
## <a name="beforepackage"></a>BeforePackage  
 `BeforePackage` Элемент указывает, что программа установки для выполнения команды перед установкой указанного пакета.  
  
## <a name="afterpackage"></a>AfterPackage  
 `AfterPackage` Элемент указывает, что программа установки для выполнения команды после установки указанного пакета.  
  
## <a name="see-also"></a>См. также  
 [\<Продукта > элемент](../deployment/product-element-bootstrapper.md)   
 [Справочные сведения о схеме пакетов и продуктов](../deployment/product-and-package-schema-reference.md)