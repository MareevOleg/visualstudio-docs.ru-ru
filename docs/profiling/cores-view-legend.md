---
title: "Легенда представления \"Ядра\" | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.cv.cores.legend
helpviewer_keywords: Concurrency Visualizer, Cores View Legend
ms.assetid: e160384c-fcfe-49b3-86b7-229adb736c51
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 820c5c48b9fc3b8d05d6e4d867e198ecc9237634
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
---
# <a name="cores-view-legend"></a>Легенда представления "Ядра"
В легенде представления "Ядра" каждый поток обозначается с помощью цвета и имени. Она включает в себя столбцы, которые показывают количество переключений контекста между ядрами и процент переключений контекста между ядрами. Строки в легенде сортируются по количеству переключений контекста между ядрами по убыванию.  
  
 Допускается выбор строк в условных обозначениях для фильтрации потоков, которые отображаются на временной шкале. На временной шкале отображаются только выбранные потоки. Если строки не выбраны, на временной шкале будут отображены все строки.  
  
 Переключения контекста между ядрами требуют больше накладных расходов и расходов ресурсов, чем переключения, остающиеся на том же логическом ядре. Во время переключений контекста сохраняются и восстанавливаются регистры процессора и код ядра операционной системы, перезагружается ассоциативный буфер трансляции инструкций и очищается конвейер процессора. Переключения контекста между ядрами могут быть еще более дорогими по сравнению с другими переключениями контекста, так как данные кэша являются недопустимыми для этого потока на другом ядре. Напротив, если поток переключился на ядро, на котором он перед этим выполнялся, то, вероятно, полезные данные все еще находятся в кэше. Если при увеличении количества межъядерных переключений контекста было увеличено количество попыток управления сходством потоков и произошло ухудшение производительности, необходимо решить, можно ли устранить эту проблему. Необходимо начать с устранения сходства потоков, после чего посмотреть полученное межъядерное поведение.  
  
 Элементы легенды описаны в следующей таблице.  
  
|Элемент|Определение|  
|-------------|----------------|  
|Имя потока|Цвет потока во временной шкале предыдущих ядер выше и имя данного потока.|  
|Переключений контекста между ядрами|Количество переключений контекста для потока, который также переключается с одного логического ядра на другое. Не существует различий между переключениями контекста между ядрами, которые осуществляются на разных ядрах процессора, и теми, которые остаются на том же.|  
|Всего переключений контекста|Общее количество переключений контекста для данного потока во время выборки. При каждом изменении контекста потока (например, с выполнения на синхронизацию) учитывается одно переключение контекста.|  
|Процент переключений контекста между ядрами|Рассчитывается как процент путем деления количества переключений контекста на количество всех переключений контекста. Чем выше этот процент, тем больше общее влияние служебных данных переключений контекста между ядрами на производительность данного потока.|  
  
## <a name="see-also"></a>См. также  
 [Представление "Ядра"](../profiling/cores-view.md)