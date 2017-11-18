---
title: "Представление в виде дерева вызовов — данные о конфликтах | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Call Tree view
ms.assetid: 9bd4bde2-2ca3-446c-9ccc-7421522e03ae
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 41bf306b96db2b3aa00fff1bdcc8562823cd9d98
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
---
# <a name="call-tree-view---contention-data"></a>Представление в виде дерева вызовов — данные о конфликтах
В преставлении "Дерево вызовов" отображаются пути выполнения функции, пересеченные в профилируемом приложении. Корнем дерева является точка входа в приложение или компонент. В каждом узле функции перечислены все вызванные ею функции, указано число и общая продолжительность блокировок этой функции из-за конфликтов с другими потоками или процессами при доступе к ресурсам.  
  
 Значения в представлении "Дерево вызовов" приведены для экземпляров функций, вызванных родительской функцией в дереве вызовов. Процентные значения вычисляются в ходе сравнения значений для экземпляров функции с общим числом конфликтов в сеансе профилирования.  
  
## <a name="highlighting-the-execution-hot-path"></a>Выделение критического пути выполнения  
 Можно развернуть представление в виде дерева вызовов и выделить путь выполнения процесса или функции, который создал больше всего конфликтов.  
  
-   Чтобы отобразить самый активный путь, щелкните процесс или функцию правой кнопкой мыши и выберите команду **Развернуть критический путь**.  
  
## <a name="setting-the-call-tree-root-node"></a>Задание корневого узла дерева вызовов  
 Каждый процесс в сеансе профилирования отображается как корневой узел. Чтобы задать начальный узел для представления в виде дерева вызовов, щелкните правой кнопкой мыши тот узел, который следует задать в качестве начального, и выберите команду **Задать корень**.  
  
 Когда вы выбираете корневой узел, из представления удаляются все записи, кроме поддерева этого узла. Чтобы восстановить исходное значение корневого узла, щелкните правой кнопкой мыши в окне представления в виде дерева вызовов и выберите **Сбросить корень**.  
  
|Столбец|Описание|  
|------------|-----------------|  
|**Эксклюзивное время блокировки**|Время, в течение которого экземпляры этой функции в этом пути выполнения были заблокированы при выполнении сеанса профилирования. Сюда не включается время блокировки дочерних функций, которые были вызваны этой функцией.|  
|**Эксклюзивное время блокировки %**|Доля времени в процентах от общего времени блокировки в сеансе профилирования, в течение которого эта функция была эксклюзивно заблокирована в этом пути выполнения.|  
|**Эксклюзивные конфликты**|Число конфликтов для экземпляров этой функции в этом пути выполнения. Это число не включает конфликты дочерних функций, которые были вызваны этой функцией.|  
|**Эксклюзивные конфликты %**|Процентная доля конфликтов в сеансе профилирования, которые оказались эксклюзивными для экземпляров этой функции, вызванных родительской функцией в дереве вызовов.|  
|**Адрес функции**|Адрес функции.|  
|**Имя функции**|Полное имя функции.|  
|**Включая время блокирования**|Общее время, в течение которого экземпляры этой функции в этом пути выполнения были заблокированы при выполнении сеанса профилирования. Сюда включается время блокировки дочерних функций, вызванных этой функцией.|  
|**Включая % времени блокирования**|Доля времени в процентах от общего времени блокировки в сеансе профилирования, в течение которого экземпляры этой функции были инклюзивно заблокированы в этом пути выполнения.|  
|**Включая состязания**|Общее число конфликтов, заблокировавших экземпляры этой функции в этом пути выполнения. Это число включает конфликты дочерних функций, которые были вызваны этой функцией.|  
|**Включая % состязаний**|Доля времени в процентах от общего времени конфликтов в сеансе профилирования, в течение которого существовали инклюзивные конфликты для этой функции в этом пути выполнения.|  
|**Уровень**|Уровень расположения функции в дереве вызовов. Только в отчетах командной строки VSPerfReport. Дополнительные сведения см. в [статье о VSPerfReport](../profiling/vsperfreport.md).|  
|**Номер строки функции**|Номер строки, на которой эта функция начинается в исходном файле.|  
|**Имя модуля**|Имя модуля, содержащего функцию.|  
|**Путь к модулю**|Путь к модулю, содержащему функцию.|  
|**Идентификатор процесса**|Идентификатор процесса (PID) сеанса профилирования.|  
|**Имя процесса**|Имя процесса.|  
|**Исходный файл**|Исходный файл, содержащий определение данной функции.|  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Настройка столбцов представлений отчета](../profiling/how-to-customize-report-view-columns.md)   
 [Call Tree View](../profiling/call-tree-view.md)  (Представление "Дерево вызовов")  
 [Call Tree View - Instrumentation](../profiling/call-tree-view-dotnet-memory-instrumentation-data.md)  (Представление "Дерево вызовов" — инструментирование)  
 [Call Tree View - Sampling](../profiling/call-tree-view-dotnet-memory-sampling-data.md)  (Представление "Дерево вызовов" — выборка)  
 [Представление "Дерево вызовов"](../profiling/call-tree-view-instrumentation-data.md)   
 [Представление "Дерево вызовов"](../profiling/call-tree-view-sampling-data.md)