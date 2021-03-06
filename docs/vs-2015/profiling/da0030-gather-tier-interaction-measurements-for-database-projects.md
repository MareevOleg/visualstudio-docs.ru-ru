---
title: 'DA0030: сбор измерений взаимодействия уровней для проектов баз данных | Документы Майкрософт'
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
- vs.performance.DA0030
- vs.performance.rules.DA0030
- vs.performance.30
ms.assetid: 42b2f69d-0cfa-4854-82c4-589c3d8b4557
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 16d6275074b3cae6b186fe9bb113e32c33e284af
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51796757"
---
# <a name="da0030-gather-tier-interaction-measurements-for-database-projects"></a>DA0030: сбор измерений взаимодействия уровней для проектов баз данных
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

ИД правила | DA0030 |  
| Категория | Использование средств профилирования |  
| Метод профилирования | Выборка |  
| Сообщение | Собрав показания измерений взаимодействия многоуровневых приложений помогают понять шаблоны использования баз данных и важных данных обращается к задержкам. Повторите профилирование приложения снова, включив параметр профилирования взаимодействия уровней. |  
| Тип правила | Сведения |  
  
## <a name="cause"></a>Причина  
 Вызовы методов <xref:System.Data> составляют значительную часть данных профилирования, и данные по взаимодействию уровней в сеансе профилирования не были собраны. Рекомендуется повторить профилирование и добавить данные об уровневом взаимодействии.  
  
## <a name="rule-description"></a>Описание правила  
 Это правило срабатывает, когда выполняется много операций в функциях, которые находятся в пространствах имен System.Data, включая <xref:System.Data.Linq><xref:System.Data.Linq>.  
  
 Многоуровневые приложения используют многоуровневые службы для уровней представления и данных. Часто уровень данных — это отдельный процесс, выполняющий систему управления базами данных, такую как Microsoft SQL Server. Уровень данных может даже выполняться на отдельном компьютере, независимо от остальной части приложения. Профили выборки недостаточно эффективно представляют функции и службы, выполняющиеся вне процесса или удаленно.  
  
 Средства профилирования могут собирать данные о времени для многоуровневых приложений, взаимодействующих с уровнем данных Microsoft SQL Server, используя асинхронные вызовы служб ADO.NET. Вы должны явно включить профилирование уровневого взаимодействия. Оно не включено по умолчанию.  
  
## <a name="how-to-fix-violations"></a>Устранение нарушений  
 Это правило используется только для сведения и не требует обязательных действий по исправлению.  
  
 Дополнительные сведения о добавлении данных об уровневом взаимодействии в данные профилирования из интегрированной среды разработки Visual Studio см. в разделе [Сбор данных взаимодействия уровней](../profiling/collecting-tier-interaction-data.md). Дополнительные сведения о добавлении данных об уровневом взаимодействии из командной строки см. в разделе [Сбор данных взаимодействия уровней](../profiling/adding-tier-interaction-data-from-the-command-line.md).



