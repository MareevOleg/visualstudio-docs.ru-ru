---
title: Обзор и Выбор типа .NET диалоговое окно | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- TypeBrowser.UI
- ActivityTypeResolver.UI
ms.assetid: 864b60b6-a070-4e5c-aa5b-a25341b57ea6
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 1bff5fccfbd4998e477043188c955e3446a45d69
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49192540"
---
# <a name="browse-and-select-a-net-type-dialog-box"></a>Диалоговое окно "Обзор и выбор типа .NET"
В **свойства** окна, диалоговые окна или конструкторы, такие как конструктор переменных, при выборе **Выбор типов...** в списке типов данных является **Обзор и Выбор типа .NET** диалоговое окно (которое в сокращенной форме называют «Обозреватель типов»). В этом диалоговом окне из представления в виде дерева сборок и проектов можно выбрать тип.  
  
 Данное диалоговое окно используется во множестве пользовательских сценариев, включая следующие.  
  
-   При задании типа переменной или аргумента.  
  
-   При выборе типа для универсального действия.  
  
-   При добавлении захвата в действие <xref:System.Activities.Statements.TryCatch>.  
  
> [!NOTE]
>  Браузер типов может отображать типы массива массивов Visual Basic, но не типы многомерных массивов. См. в разделе [массивы массивов](http://go.microsoft.com/fwlink/?LinkId=195226) и [многомерные массивы](http://go.microsoft.com/fwlink/?LinkId=195227) подробные сведения.  
  
## <a name="selecting-a-value-or-reference-type-from-the-type-browser"></a>Выбор значения или ссылочного типа из браузера типов  
  
#### <a name="to-select-a-value-or-reference-type-from-the-type-browser"></a>Выбор значения или ссылочного типа из браузера типов  
  
1.  В **имя типа** введите имя типа, который вы хотите использовать.  
  
2.  Выполните одно из следующих действий.  
  
    -   Как только появится имя типа, который вы хотите использовать в дереве в **имя типа** окне дважды щелкните тип, чтобы выбрать его.  
  
    -   Введите достаточного количества символов в **имя типа** служит для уникальной идентификации нужного типа, который вы хотите использовать, и нажмите клавишу ВВОД для выбора типа  
  
#### <a name="to-select-a-generic-type-from-the-type-browser"></a>Выбор универсального типа из браузера типов  
  
1.  В **имя типа** », вкладка «имя типа, который вы хотите использовать.  
  
2.  Как только появится имя типа, который вы хотите использовать в дереве в **имя типа** поле, щелкните тип, выберите его, чтобы вызвать раскрывающиеся списки отображаются.  
  
     Выберите тип, который вы хотите использовать раскрывающиеся списки будут закрыты, а затем нажмите кнопку **ОК**.  
  
## <a name="types-displayed-in-the-type-browser"></a>Типы, отображенные в браузере типов  
 Типы, отображенные в браузере типов, могут изменяться в зависимости от способа запуска браузера. Если браузер типов был запущен из проекта рабочего процесса, внутри **vs2010**, по умолчанию все типы в сборках, на которую указывает ссылка, и отображаются проекты, на которую указывает ссылка. Если браузер типов был запущен из за пределами **vs2010** проекта системы (например, приложение повторно размещенном рабочего процесса или в автономном файле рабочего процесса), то по умолчанию отображаются типы из всех сборок, загруженных в AppDomain .  
  
 Разработчики конструкторов операций могут отфильтровать типы в браузере типов. Для каждого данного действия можно увидеть поднабор типов. Например, в действии <xref:System.Activities.Statements.TryCatch> в браузере типов отображаются только типы, производные от <xref:System.Exception>.  
  
## <a name="filtering-search-results-in-the-type-browser"></a>Фильтрация результатов поиска в браузере типов  
 Список типов в **имя типа** уменьшается по мере ввода символов для поиска совпадений. В отфильтрованном списке отображаются только те типы, чье полное или короткое имя начинается с введенной строки.  
  
 Пример:  
  
1.  Введя **операции** соответствует <xref:System.OperationCanceledException> , но не <xref:System.InvalidOperationException>. Чтобы введенное слово совпало с <xref:System.InvalidOperationException>, начните строку с System.I или Invalid.  
  
2.  Введя **универсального** соответствует <xref:System.GenericUriParser> , но не вводит в <xref:System.Collections.Generic> пространства имен. Чтобы выполнить поиск типов в пространстве имен <xref:System.Collections.Generic>, введите полное имя пространства имен.  
  
## <a name="selecting-a-service-contract-using-the-type-browser-dialog"></a>Выбор контракта службы с помощью диалогового окна браузера типов  
 При выборе типа контракта службы браузер типов отображает только типы, имеющие атрибут <xref:System.ServiceModel.ServiceContractAttribute>.  
  
## <a name="see-also"></a>См. также  
 [Использование конструкторов действий](../workflow-designer/using-the-activity-designers.md)