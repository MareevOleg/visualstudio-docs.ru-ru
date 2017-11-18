---
title: "Управление каналами | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.cv.threads.tools.managechannels
helpviewer_keywords: Concurrency Visualizer, Manage Channels
ms.assetid: 507b06e9-bb56-4a72-8fd5-f91f958da6fc
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 794b34365dfa025c6ade7f2d7a2f1216c2b4e4ff
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
---
# <a name="manage-channels"></a>Управление каналами
В представлении **Потоки** в визуализаторе параллелизма можно организовать для процесса каналы для изучения определенных шаблонов. Вы можете сортировать каналы, перемещать их вверх и вниз, скрывать и отображать.  
  
## <a name="sort-by"></a>Порядок сортировки  
 Для сортировки потоков по различным критериям (на основе текущего уровня масштаба) можно использовать элемент управления "Сортировать по". Это особенно удобно, если вы ищете определенный шаблон. Можно выполнить сортировку по следующим критериям:  
  
|Критерии|Определение|  
|--------------|----------------|  
|Время начала|Сортировка потоков по времени начала. Это порядок сортировки по умолчанию.|  
|Время окончания|Сортировка потоков по времени завершения.|  
|Выполнение|Сортировка потоков по доле времени, затраченного на выполнение.|  
|Синхронизация|Сортировка потоков по доле времени, затраченного на синхронизацию.|  
|Ввод-вывод|Сортировка потоков по доле времени, затраченного на операции ввода-вывода (чтение и запись данных).|  
|Sleep|Сортировка потоков по доле времени, затраченного на спящий режим.|  
|Разбивка на страницы|Сортировка потоков по доле времени, затраченного на подкачку.|  
|Вытеснение|Сортировка потоков по доле времени, затраченного на вытеснение.|  
|Обработка UI|Сортировка потоков по доле времени, затраченного на обработку пользовательского интерфейса.|  
  
## <a name="move-selected-channel-up-or-down"></a>Перемещение выбранного канала вверх или вниз  
 Эти элементы управления можно использовать для перемещения канала вверх или вниз в списке. Например, можно разместить связанные каналы рядом друг с другом, чтобы проанализировать определенный шаблон или связь между потоками.  
  
## <a name="move-selected-channel-to-top-or-bottom"></a>Перемещение выбранного канала в верхнюю или нижнюю строку  
 Выбранные каналы можно переместить в верхнюю или нижнюю строку списка, чтобы изучить определенный шаблон, или переместить некоторые каналы так, чтобы они не мешали про работе.  
  
## <a name="hide-selected-channels"></a>Скрыть выбранные каналы  
 Используйте этот элемент управления, если вы хотите скрыть каналы. Например, если поток — на 100 процентов синхронизирован в течение времени выполнения управляемого процесса, вы можете скрыть его при анализе других потоков.  
  
> [!NOTE]
>  При скрытии потока он также удаляется из времени расчета, которое отображается в активной легенде и отчетах о профиле.  
  
## <a name="show-all-channels"></a>Показ всех каналов  
 Этот элемент управления активен, когда один или несколько каналов скрыты. При его выборе все скрытые элементы отображаются и возвращаются в расчет времени.  
  
## <a name="move-markers-to-top"></a>Переместить маркеры в начало  
 Если трассировка содержит события маркеров, эта команда используется для перемещения каналов маркера в верхнюю часть временной шкалы. Их относительный порядок сохраняется.  
  
## <a name="group-markers-by-thread"></a>Группировать маркеры по потокам  
 Если трассировка содержит события маркеров, эту команду можно использовать, чтобы группировать каналы маркеров в потоке, создавшем события маркеров.  Каналы диска перемещаются в верхнюю строку списка каналов, а каналы GPU — в нижнюю.  
  
## <a name="see-also"></a>См. также  
 [Элемент управления масштабом (представление "Потоки")](../profiling/zoom-control-threads-view.md)   
 [Режим измерения (вкл./выкл.)](../profiling/measure-mode-on-off.md)   
 [Представление "Потоки"](../profiling/threads-view-parallel-performance.md)