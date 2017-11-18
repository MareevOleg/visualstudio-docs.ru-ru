---
title: "DA0503. Средний рабочий набор в байтах для профилируемого процесса | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.503
- vs.performance.DA0503
- vs.performance.rules.DA0503
ms.assetid: 9047a494-eaaf-4679-b422-c64e8bde77a4
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e47af0282eb5731a931be35a6acf16c776204574
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
---
# <a name="da0503-average-working-set-in-bytes-for-the-process-being-profiled"></a>DA0503. Средний рабочий набор в байтах для профилируемого процесса
|||  
|-|-|  
|Идентификатор правила|DA0503|  
|Категория|Наблюдение за ресурсами|  
|Способ профилирования|Все|  
|Сообщение|Эти сведения были собраны только для информации. Счетчик рабочего набора процесса измеряет объем использования физической памяти профилируемым процессом. Полученное значение является средним значением, вычисленным в течение всех интервалов измерения.|  
|Тип правила|Сведения|  
  
 При профилировании с помощью выборки, памяти .NET или методов разрешения конфликтов ресурсов необходимо собрать минимум 10 выборок, чтобы активировать это правило.  
  
## <a name="rule-description"></a>Описание правила  
 В этом сообщении указывается средний объем физической памяти (в байтах), используемой процессом в данный момент (рабочий набор). Рабочий набор процесса представляет страницы из адресного пространства процесса, которые в настоящий момент находятся в физической памяти.  
  
 В указываемом значении учитываются постоянные страницы из сегментов общей памяти, на которые ссылается процесс. Общие библиотеки DLL, на которые ссылается процесс, включаются в сегменты общей памяти, которые учитываются счетчиком. Значение рабочего набора процесса может превышать объем виртуальной памяти, выделенной процессом из-за сегментов общей памяти.  
  
 Содержащееся в отчете значение является средним по всем интервалам измерения, в которых профилируемый процесс был активным.  
  
 Размер рабочего набора процесса отражает объем виртуальной памяти, активно используемой процессом. На него также влияет объем физической памяти (или ОЗУ), доступной для запуска приложения, и состязание за физическую память с другими процессами. Если физическая память ограничена, значение рабочего набора процесса обычно существенно меняется, когда операционная система пытается балансировать использование памяти активными процессами, периодически исключая явно неактивные страницы из рабочих наборов процесса.  
  
 Дополнительные сведения о рабочих наборах процесса см. в разделе [Рабочий набор](http://go.microsoft.com/fwlink/?LinkId=177830) в документации MSDN по управлению памятью Windows.  
  
## <a name="how-to-use-rule-data"></a>Использование данных правила  
 Значение правила используется для сравнения производительности разных версий или сборок программы или для анализа производительности приложения в различных сценариях профилирования.  
  
 Дважды щелкните сообщение в окне "Список ошибок", чтобы перейти к представлению [Метки](../profiling/marks-view.md) данных профилирования. Найдите столбцы **Процесс\Рабочий набор** и **Память\Страниц в секунду**. Сравните значения в двух столбцах и определите, есть ли конкретные этапы выполнения программы, которые могут быть связаны с увеличением числа операций ввода-вывода подкачки.