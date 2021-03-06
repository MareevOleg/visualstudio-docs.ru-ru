---
title: Представление "Дерево вызовов" | Документы Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.view.calltree
helpviewer_keywords:
- Call Tree view
- profiling tools reports, Call Tree view
- performance reports, Call Tree view
- profiling tools, Call Tree view
ms.assetid: b2dbc033-bf95-4d10-8e51-f9462979133e
caps.latest.revision: 39
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8f09b85c20d84cb25d6a1fdbbd8493c47056318a
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51738751"
---
# <a name="call-tree-view"></a>Представление "Дерево вызовов"
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

В преставлении "Дерево вызовов" отображаются пути выполнения функции, пересеченные в профилируемом приложении. Корнем дерева является точка входа в приложение или компонент. В каждом узле функции перечислены все вызванные в ней функции и содержатся данные по производительности, связанные с этими вызовами функций.  
  
 Кроме того, можно развернуть представление "Дерево вызовов" и проанализировать путь выполнения функции, приведший к наибольшей задержке или встречавшийся наиболее часто. Чтобы отобразить самый активный путь, щелкните функцию правой кнопкой мыши и выберите команду **Развернуть критический путь**.  
  
 Каждый процесс в сеансе профилирования отображается как корневой узел. В представлении "Дерево вызовов" можно задать начальный узел, щелкнув правой кнопкой мыши узел, который должен стать начальным, и выбрав команду **Задать корень**.  
  
 После задании корневого узла из представления удаляются все записи, кроме поддеревьев выбранного узла. Корневым узлом можно снова сделать узел, который вы просматривали. Для этого щелкните правой кнопкой мыши в окне представления "Дерево вызовов" и выберите команду **Сбросить корень**.  
  
 Представление "Дерево вызовов" можно настроить, удалив или добавив столбцы. Щелкните правой кнопкой мыши заголовок **Имя столбца** и выберите в контекстном меню команду **Добавить или удалить столбцы**.  
  
 Представление "Дерево вызовов" можно настроить для снижения шума, сократив объем представляемых данных. Благодаря снижению шума проблемы производительности в представлении становятся более наглядными. Возможность более простого выявления проблем повышает эффективность анализа. Дополнительные сведения см. в разделе [Практическое руководство. Настройка подавления шума для представлений отчетов](../profiling/how-to-configure-noise-reduction-in-report-views.md).  
  
> [!NOTE]
>  Если снижение шума настроено для отображения предупреждений при их появлении, в отчете появится информационная панель.  
  
 Дополнительные сведения об определениях столбцов в представлении "Дерево вызовов" см. в следующих разделах:  
  
 [Представление "Дерево вызовов"](../profiling/call-tree-view-sampling-data.md)  
  
 [Представление "Дерево вызовов"](../profiling/call-tree-view-instrumentation-data.md)  
  
 [Представление "Дерево вызовов" — выборка](../profiling/call-tree-view-dotnet-memory-sampling-data.md)  
  
 [Представление "Дерево вызовов"](../profiling/call-tree-view-contention-data.md)  
  
## <a name="see-also"></a>См. также  
 [Представления отчетов о производительности](../profiling/performance-report-views.md)   
 [Общие сведения о значениях данных инструментирования](../profiling/understanding-instrumentation-data-values.md)   
 [Общие сведения о значениях выборочных данных](../profiling/understanding-sampling-data-values.md)



