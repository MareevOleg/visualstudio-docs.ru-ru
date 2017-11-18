---
title: "DA0008. Собрано мало выборок | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.rules.DATooFewSamples
- vs.performance.8
- vs.performance.DA0008
- vs.performance.rules.DA0008
ms.assetid: 8a5b78aa-7b3d-476c-a47d-abfaff3fae7c
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9f78e1e75eb328331adfdcdddfc659a4167ae503
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
---
# <a name="da0008-few-samples-collected"></a>DA0008. Собрано несколько образцов
|||  
|-|-|  
|Идентификатор правила|DA0008|  
|Категория|Использование средств профилирования|  
|Способ профилирования|Дискретизация|  
|Сообщение|Собрано небольшое число выборок. Для получения значительных результатов рекомендуется использовать более высокую частоту выборки или более долгий запуск.|  
|Тип правила|Сведения|  
  
## <a name="cause"></a>Причина  
 В сеансе профилирования было собрано небольшое число выборок.  
  
## <a name="rule-description"></a>Описание правила  
 При использовании метода выборки следует собрать статистически значимое число выборок, чтобы данные отражали фактическое поведение программы. Чтобы свести к минимуму ошибки выборки, нужно собрать по крайней мере 1000 выборок данных по выполнению инструкции программы. Недостаточное количество выборок может привести к неправильным выводам при анализе данных профилирования.  
  
## <a name="how-to-fix-violations"></a>Устранение нарушений  
 Для получения статистически значимых результатов рекомендуется дольше выполнять процедуру профилирования приложения или увеличить частоту выборки. Дополнительные сведения об изменении частоты выборки в интегрированной среде разработки Visual Studio см. в разделе [Практическое руководство. Выбор событий выборки](../profiling/how-to-choose-sampling-events.md). Дополнительные сведения об изменении частоты выборки при использовании командной строки средств профилирования см. в разделе [Таймер](../profiling/timer.md) руководства [VSPerfCmd](../profiling/vsperfcmd.md).