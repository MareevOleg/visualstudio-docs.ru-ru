---
title: Визуализатор параллелизма | Документы Майкрософт
ms.custom: ''
ms.date: 07/11/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.performance.viewnavigation
- vs.cv.overview
- vs.cv.performance.gettingstarted
- vs.cv.gettingstarted
helpviewer_keywords:
- Concurrency Visualizer, Concurrency Visualizer
ms.assetid: ae5879a0-1e1a-455a-ba72-148e57f59289
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 05ed2edd453cd9e267a32bfdd5d9a6b0ad6a7ac3
ms.sourcegitcommit: bccb05b5b4e435f3c1f7c36ba342e7d4031eb398
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2018
ms.locfileid: "51220668"
---
# <a name="concurrency-visualizer"></a>Визуализатор параллелизма
> [!NOTE]
>  Визуализатор параллелизма — это дополнительное расширение Visual Studio. Загрузите визуализатор параллелизма и средства сбора данных визуализатора параллелизма по следующим ссылкам:  
> 
> - Скачайте расширение [Визуализатор параллелизма для Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=VisualStudioProductTeam.ConcurrencyVisualizer2017#overview).  
> - Скачайте расширение [Визуализатор параллелизма для Visual Studio 2015](https://marketplace.visualstudio.com/items?itemName=Diagnostics.ConcurrencyVisualizerforVisualStudio2015).  
>   -   Скачайте              [средства сбора данных визуализатора параллелизма для Visual Studio 2015](http://www.microsoft.com/download/details.aspx?id=49103).  
> 
>   С помощью [служебной программы командной строки "Визуализатор параллелизма" (CVCollectionCmd)](../profiling/concurrency-visualizer-command-line-utility-cvcollectioncmd.md) можно собирать трассировки из командной строки, чтобы просматривать их в визуализаторе параллелизма для Visual Studio 2015. Это средство можно использовать на компьютерах без установленной среды Visual Studio.  
  
 Визуализатор параллелизма можно использовать для изучения работы многопоточного приложения. Представления в визуализаторе параллелизма предоставляют графические, табличные и текстовые данные, отражающие временные связи между потоками в программе и системе в целом. С помощью визуализатора параллелизма можно найти узкие места по производительности, случаи избыточного использования ЦП, конфликты потоков, межъядерную миграцию потоков, задержки синхронизации, действия DirectX, области перекрывающихся операций ввода-вывода и другие сведения. Эти представления предоставляют данные, действия с которыми можно выполнять путем связывания выводимой графической информации со стеками вызова и исходным кодом.  

> [!NOTE]
>  Визуализатор параллелизма не поддерживает веб-проекты.  
  
 Визуализатор параллелизма основывается на функции [Трассировка событий Windows](http://go.microsoft.com/fwlink/?LinkId=234579) .  
  
## <a name="related-topics"></a>См. также  
  
|Заголовок|Описание:|  
|-----------|-----------------|  
|[Представление "Использование"](../profiling/utilization-view.md)|Содержит описание процедуры просмотра и анализа системных действий для всех процессоров.|  
|[Представление потоков](../profiling/threads-view-parallel-performance.md)|Содержит описание процедуры анализа взаимодействия между потоками программы.|  
|[Представление "Ядра"](../profiling/cores-view.md)|Содержит описание процедуры анализа миграции потоков между ядрами.|  
|[Общие шаблоны для неправильно работающих многопоточных приложений](../profiling/common-patterns-for-poorly-behaved-multithreaded-applications.md)|Описывает несколько общих шаблонов и показывает, как они отображаются в визуализаторе параллелизма.|  
|[Блог о параллельной разработке в Visual Studio](http://go.microsoft.com/fwlink/?LinkId=235385)|Содержит советы и рекомендации для визуализатора параллелизма.|  
|[Представления отчетов о производительности](../profiling/performance-report-views.md)|Содержит справочные сведения по отчетам и представлениям средств профилирования Visual Studio.|  
|[Пакет SDK визуализатора параллелизма](../profiling/concurrency-visualizer-sdk.md)|Описывает, как инструментировать исходный код для отображения дополнительных сведений в визуализаторе параллелизма.|  
|[Служебная программа командной строки "Визуализатор параллелизма" (CVCollectionCmd)](../profiling/concurrency-visualizer-command-line-utility-cvcollectioncmd.md)|Описывает, как использовать программу командной строки визуализатора параллелизма (CVCollectionCmd.exe) для сбора и обработки трассировки на компьютерах, на которых не установлена Visual Studio.|  
  
## <a name="see-also"></a>См. также  
 [Профилирование в Visual Studio](../profiling/index.md)  
 [Первое знакомство со средствами профилирования](../profiling/profiling-feature-tour.md)
