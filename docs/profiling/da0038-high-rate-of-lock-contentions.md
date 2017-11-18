---
title: "DA0038. Большое число конфликтов при блокировке | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.38
- vs.performance.rules.DA0038
- vs.performance.DA0038
ms.assetid: ae0c8b2f-17b2-4f3d-a834-aa2f6371753b
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 30f9dbb760bd013bae08b5539f32d652ec3313bd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
---
# <a name="da0038-high-rate-of-lock-contentions"></a>DA0038. Большое число конфликтов при блокировке
|||  
|-|-|  
|Идентификатор правила|DA0038|  
|Категория|Использование .NET Framework|  
|Способ профилирования|Дискретизация<br /><br /> Инструментирование<br /><br /> Память .NET|  
|Сообщение|Возникло большое число конфликтов при блокировке .NET. Выявите причину этого конфликта при блокировке, запустив профиль "Параллельность".|  
|Тип правила|Сведения|  
  
 При профилировании с помощью выборки, памяти .NET или методов разрешения конфликтов ресурсов необходимо собрать минимум 25 выборок, чтобы активировать это правило.  
  
## <a name="cause"></a>Причина  
 Данные о производительности системы, собранные с помощью данных профилирования, указывают на значительно большое число конфликтов блокировки, возникающих во время выполнения приложения. Рекомендуется повторить профилирование с использованием метода профилирования параллелизма для поиска причины конфликтов.  
  
## <a name="rule-description"></a>Описание правила  
 Блокировки используются для защиты критических частей кода, которые должны выполняться последовательно, одним потоком за раз в многопоточных приложениях. Среда CLR Microsoft .NET предоставляет полный набор примитивов синхронизации и блокировки. Например, в языке C# поддерживается оператор lock (SyncLock в Visual Basic). Управляемое приложение может вызывать методы Monitor.Enter и Monitor.Exit в пространстве имен System.Threading для получения и снятия блокировки напрямую. .NET Framework поддерживает дополнительные примитивы синхронизации и блокировки, включая классы, поддерживающие классы Mutexes, ReaderWriterLocks и Semaphores. Дополнительные сведения см. в документе [Обзор примитивов синхронизации](http://go.microsoft.com/fwlink/?LinkId=177867) в руководстве разработчика по .NET Framework на веб-сайте MSDN. Классы .NET Framework основаны на службах синхронизации более низкого уровня, встроенных в операционную систему Windows. Сюда входят важные объекты разделов и много разных функций ожидания и сигнализации о событиях. Дополнительные сведения см. в разделе [Синхронизация](http://go.microsoft.com/fwlink/?LinkId=177869) разработки COM и Win32 в библиотеке MSDN.  
  
 Базовыми для классов .NET Framework и собственных объектов Windows, которые используются для синхронизации и блокировки, являются области общей памяти, которые должны быть изменены с помощью операций блокировки. Операции блокировки используют определяемые оборудованием инструкции, которые работают с областями общей памяти, для изменения их состояния с помощью атомарных операций. Согласованность атомарных операций гарантируется для всех процессоров в компьютере. Объекты Lock и WaitHandle являются объектами .NET, которые автоматически используют операции блокировки при их назначении или сбросе. В приложении могут существовать другие структуры данных общей памяти, которые также требуют использования операций блокировки для изменения потокобезопасным способом. Дополнительные сведения см. в статье [Блокируемые операции](http://go.microsoft.com/fwlink/?LinkId=177870) раздела .NET Framework библиотеки MSDN.  
  
 Синхронизация и блокировка — это механизмы, используемые для обеспечения правильного выполнения многопоточных приложений. Каждый поток многопоточного приложения представляет собой независимый блок выполнения, запуск которого планируется операционной системой независимо. Конфликт блокировки происходит всякий раз, когда поток, который пытается получить блокировку, откладывается, так как другой поток удерживает блокировку.  
  
 Блокировки часто являются вложенными. Вложенность возникает, когда поток, выполняющий критический раздел, выполняет функцию, которая затем требует другую блокировку. Некоторая степень вложенности блокировок является неизбежной. Критический раздел может вызывать метод .NET Framework, зависящий от блокировок, чтобы гарантировать его потокобезопасность. Вызов из критического раздела приложения метода .NET Framework, который также выполняет блокировку с другим дескриптором блокировки, приводит к вложению блокировок. Вложенные блокировки могут вызывать проблемы производительности, которые сложно обнаружить и устранить.  
  
 Это правило срабатывает, если измерения, выполненные во время сеанса профилирования, свидетельствуют о большом числе конфликтов блокировки. Конфликты блокировки задерживают выполнение потоков, ожидающих блокировки. Следует проверять причину даже весьма незначительного числа конфликтов блокировки в модульных и в нагрузочных тестах, выполняемых на оборудовании с ограниченными ресурсами.  
  
> [!NOTE]
>  Если количество конфликтов блокировки в данных профилирования чрезмерно велико, вместо этого информационного сообщения вызывается предупреждение [DA0039. Очень большое число конфликтов при блокировке](../profiling/da0039-very-high-rate-of-lock-contentions.md).  
  
## <a name="how-to-investigate-a-warning"></a>Изучение причин предупреждения  
 Дважды щелкните сообщение, чтобы перейти к представлению [Метки](../profiling/marks-view.md) данных профилирования.  Найдите столбец **Блокировки и потоки CLR .NET\Частота конфликтов/сек**. Определите, есть ли какие-то конкретные этапы выполнения программы, когда число конфликтов блокировки больше, чем на других этапах.  
  
 Это правило срабатывает, только если не используется метод профилирования параллелизма. Метод профилирования параллелизма является лучшим средством для диагностики проблем производительности, связанных с конфликтами блокировки в приложении. Выполните сбор данных профилирования параллелизма, чтобы получить представление о режиме блокировки приложения. Вам потребуется выяснить, какие виды блокировок вызывают самое большое число конфликтов, насколько задерживается выполнение потока в ожидании конфликтующих блокировок и какой код ими затрагивается. Профили параллелизма собирают данные обо всех конфликтах блокировки, включая поведение блокировки собственных средств Windows, классов .NET Framework и любых других сторонних библиотек, на которые ссылается ваше приложение. Дополнительные сведения о профилировании параллелизма из интегрированной среды разработки [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] см. в разделе [Сбор данных о параллелизме потоков и процессов](../profiling/collecting-thread-and-process-concurrency-data.md). Ссылки на сведения о профилировании параллелизма из командной строки см. в разделе **Использование метода параллелизма для сбора данных о конфликтах ресурсов и действиях потока** статьи [Использование методов профилирования из командной строки](../profiling/using-profiling-methods-to-collect-performance-data-from-the-command-line.md).