---
title: Сопоставление методов в стеке вызовов при отладке в Visual Studio | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- vs.progression.debugwithcodemaps
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- call stacks, code maps
- Call Stack window, mapping calls
- debugging [Visual Studio], diagramming the call stack
- call stacks, mapping
- Call Stack window, visualizing
- debugging code visually
- debugging [Visual Studio], mapping the call stack
- call stacks, visualizing
- debugging, code maps
- Call Stack window, tracing calls visually
- Call Stack window, show on code map
- debugging [Visual Studio], tracing the call stack visually
- debugging [Visual Studio], visualizing the call stack
ms.assetid: d6a72e5e-f88d-46fc-94a3-1789d34805ef
caps.latest.revision: 43
author: MikeJo5000
ms.author: gewarren
manager: douge
ms.openlocfilehash: f67a891327d179ffd23b56eb5bae951309bab8da
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51725616"
---
# <a name="map-methods-on-the-call-stack-while-debugging-in-visual-studio"></a>Сопоставление методов в визуализации стека вызовов при отладке в Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Для визуального отслеживания стека вызовов при отладке можно создать карту кода. В это сопоставление можно вносить примечания для отслеживания операций, выполняемых кодом. Таким образом, вы сможете сосредоточиться на поиске ошибок.  
  
 ![Отладка со стеками вызовов на картах кода](../debugger/media/debuggermap-overview.png "DebuggerMap_Overview")  
  
 Требуется:  
  
- [Visual Studio Enterprise](https://www.visualstudio.com/downloads/download-visual-studio-vs)  
  
- Код, поддерживающий отладку: Visual C# .NET, Visual Basic .NET, C++, JavaScript и X++  
  
  См.: [видео: визуальная отладка с интеграцией отладчика сопоставления кода (канал 9)](http://go.microsoft.com/fwlink/?LinkId=293418) • [сопоставьте стек вызовов](#MapStack) • [сделать примечания о коде](#MakeNotes) • [обновите карту с следующим стеком вызовов](#UpdateMap) • [Добавление связанного кода в сопоставление](#AddRelatedCode) • [поиск ошибок, используя сопоставление](#FindBugs) • [вопросы И ответы](#QA)  
  
  Узнать о командах и действиях, которые можно использовать при работе с картами кода, см. в разделе [Просмотр и реорганизация карт кода](../modeling/browse-and-rearrange-code-maps.md).  
  
##  <a name="MapStack"></a> Сопоставьте стек вызовов  
  
1.  Приступите к отладке. (Клавиатура: **F5**)  
  
2.  Когда приложение переходит в режим приостановки выполнения или при входе в функцию, нажмите кнопку **карта кода**. (Клавиатура: **Ctrl** + **Shift** + **`**)  
  
     ![Выберите карту кода, чтобы запустить сопоставление стека вызовов](../debugger/media/debuggermap-choosecodemap.png "DebuggerMap_ChooseCodeMap")  
  
     Текущий стек вызовов выделен в новой карте кода оранжевым цветом:  
  
     ![См. в разделе стек вызовов на карте кода](../debugger/media/debuggermap-seeundocallstack.png "DebuggerMap_SeeUndoCallStack")  
  
     Эта карта будет автоматически обновляться в ходе отладки. См. в разделе [обновление сопоставления путем добавления следующего стека вызовов](#UpdateMap).  
  
##  <a name="MakeNotes"></a> Добавление примечаний в код  
 Добавьте комментарии для отслеживания операций, выполняемых в коде. Чтобы добавить новую строку в комментарий, нажмите клавишу **Shift + Return**.  
  
 ![Добавление комментария к стеку вызовов на карте кода](../debugger/media/debuggermap-addcomment.png "DebuggerMap_AddComment")  
  
##  <a name="UpdateMap"></a> Обновление сопоставления путем добавления следующего стека вызовов  
 Выполните приложение до следующей точки останова или зайдите в функцию. В сопоставление будет добавлен новый стек вызовов.  
  
 ![Обновление карты кода следующим стеком вызовов](../debugger/media/debuggermap-addclearcallstack.png "DebuggerMap_AddClearCallStack")  
  
##  <a name="AddRelatedCode"></a> Добавление связанного кода на карту  
 Итак, сопоставление готово. Что дальше? При работе с Visual C#, .NET или Visual Basic .NET добавьте в него элементы, такие как поля, свойства и методы, для отслеживания операций в коде.  
  
 Дважды щелкните метод для просмотра его определения кода или используйте контекстное меню метода. (Клавиатура: выделите метод в сопоставлении и нажмите клавишу **F12**)  
  
 ![Перейти к определению кода для метода на карте кода](../debugger/media/debuggermap-gotocodedefinition.png "DebuggerMap_GoToCodeDefinition")  
  
 Добавьте элементы, которые необходимо отслеживать в сопоставлении.  
  
 ![Отображение полей в методе на карте кода со стеком вызовов](../debugger/media/debuggermap-showfields.png "DebuggerMap_ShowFields")  
  
> [!NOTE]
>  По умолчанию при добавлении элементов в сопоставление также добавляются узлы родительской группы, соответствующие, например, классу, пространству имен или сборке. Хотя эта возможность полезна, вы можете постоянно карты простой, отключение этой функции через **включить родительские элементы** кнопки на панели инструментов карты или нажимая клавиши **CTRL** при добавлении элементов.  
  
 ![Поля, связанные с методом на карте кода со стеком вызовов](../debugger/media/debuggermap-showedfields.png "DebuggerMap_ShowedFields")  
  
 Нетрудно определить, какие методы используют одинаковые поля. Последние добавленные элементы отображаются зеленым цветом.  
  
 Продолжайте формировать сопоставление, чтобы увидеть дополнительный код.  
  
 ![См. в разделе методов, использующие поле: карте кода со стеком вызовов](../debugger/media/debuggermap-findallreferences.png "DebuggerMap_FindAllReferences")  
  
 ![Методы, использующие поле на карте кода со стеком вызовов](../debugger/media/debuggermap-foundallreferences.png "DebuggerMap_FoundAllReferences")  
  
##  <a name="FindBugs"></a> Поиск ошибок с помощью карты  
 Визуализация кода поможет вам быстрее находить ошибки. Например, предположим, что вы ищите ошибку в программе для рисования. Когда вы создаете линию и пробуете отменить ее создание, ничего не происходит до тех пор, пока не будет нарисована следующая линия.  
  
 Установив точки останова в методах `clear`, `undo` и `Repaint`, вы начинаете отладку и создаете сопоставление, аналогичное представленному ниже:  
  
 ![Добавление другого стека вызовов на карте кода](../debugger/media/debuggermap-addpaintobjectcallstack.png "DebuggerMap_AddPaintObjectCallStack")  
  
 Учтите, что все жесты пользователя в сопоставлении вызывают метод `Repaint`, за исключением `undo`. Возможно, именно поэтому функция `undo` срабатывает не сразу.  
  
 Когда вы исправите ошибку и продолжите выполнение программы, в сопоставление будет добавлен новый вызов из `undo` в `Repaint`.  
  
 ![Добавить новый стек вызова к вызову метода на карте кода](../debugger/media/debuggermap-addnewcallforrepaint.png "DebuggerMap_AddNewCallForRepaint")  
  
##  <a name="QA"></a> Вопросы и ответы  
  
- **Не все вызовы отображаются на карте. Почему?**  
  
   По умолчанию в сопоставлении отображается только ваш код. Чтобы просмотреть внешний код, включите его **стек вызовов** окна:  
  
   ![Отображение внешнего кода, в окне стека вызовов](../debugger/media/debuggermap-callstackmenu.png "DebuggerMap_CallStackMenu")  
  
   или отключите **включить только мой код** в параметрах отладки Visual Studio:  
  
   ![Показать внешний код, используя диалоговое окно параметров](../debugger/media/debuggermap-debugoptions.png "DebuggerMap_DebugOptions")  
  
- **Изменение сопоставления влияет на код?**  
  
   Изменение сопоставления никак не влияет на код. Можно свободно переименовать, изменить или удалить любой элемент в сопоставлении.  
  
- **Что означает сообщение: «диаграмме могут основываться на более старой версии кода»?**  
  
   С момента последнего обновления сопоставления код мог измениться. Например, вызов в сопоставлении может уже не существовать в коде. Закройте сообщение, а затем попытайтесь повторить сборку решения, прежде чем повторно обновлять сопоставление.  
  
- **Как управлять макетом сопоставления?**  
  
   Откройте **макета** меню на панели инструментов карты:  
  
  -   Измените макет по умолчанию.  
  
  -   Чтобы остановить автоматическую перекомпоновку сопоставления, отключите режим **автоматически формировать макет при отладке**.  
  
  -   Для изменения порядка как можно реже карты, при добавлении элементов, отключите **последовательный макет**.  
  
- **Можно ли совместно использовать карты с другими пользователями?**  
  
   Сопоставление можно экспортировать, отправить его другим пользователям при наличии Microsoft Outlook или сохранить его в решении, чтобы можно было вернуть его в систему управления версиями Team Foundation.  
  
   ![Карта кода стек вызова общей папки с другими пользователями](../debugger/media/debuggermap-sharewithothers.png "DebuggerMap_ShareWithOthers")  
  
- **Как остановить сопоставление добавляло новые стеки вызова автоматически?**  
  
   Выберите ![кнопку &#45; стек вызовов Показать на карте кода автоматически](../debugger/media/debuggermap-automaticupdateicon.gif "DebuggerMap_AutomaticUpdateIcon") на панели инструментов карты. Чтобы вручную добавить текущий стек вызовов на карту, нажмите клавишу **Ctrl** + **Shift** + **`**.  
  
   Существующие стеки вызовов по-прежнему будут выделяться на сопоставлении во время отладки.  
  
- **Что значки элементов и стрелки означают?**  
  
   Чтобы узнать дополнительные сведения об элементе, наведите на него указатель мыши и прочитайте подсказку. Вы также можете изучить **условных обозначений** чтобы узнать, что означает каждый значок.  
  
   ![Что означают значки на карте кода со стеком вызовов ](../debugger/media/debuggermap-showlegend.png "DebuggerMap_ShowLegend")  
  
  См.: [сопоставьте стек вызовов](#MapStack) • [сделать примечания о коде](#MakeNotes) • [обновление сопоставления путем добавления следующего стека вызовов](#UpdateMap) • [Добавление связанного кода в сопоставление](#AddRelatedCode) • [ Поиск ошибок с помощью карты](#FindBugs)  
  
## <a name="see-also"></a>См. также  
 [Сопоставление зависимостей во всех решениях](../modeling/map-dependencies-across-your-solutions.md)   
 [Использование карт кода для отладки приложений](../modeling/use-code-maps-to-debug-your-applications.md)   
 [Поиск потенциальных проблем, с помощью анализаторов карт кода](../modeling/find-potential-problems-using-code-map-analyzers.md)   
 [Просмотр и реорганизация карт кода](../modeling/browse-and-rearrange-code-maps.md)





