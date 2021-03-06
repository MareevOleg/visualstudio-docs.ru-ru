---
title: Sys (VSPerfCmd) | Документы Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 294a6f9e-b49f-4c83-b322-5ac5411b66fb
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7968d35050c7b36957b56b9c707fe0404842a07a
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51749827"
---
# <a name="sys-vsperfcmd"></a>Sys (VSPerfCmd)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Параметр **Sys** программы VSPerfCmd.exe задает событие профилирования, которое дискретизируется в соответствии с событиями системных вызовов (вызовы функций из профилируемого приложения в операционную систему), и при необходимости изменяет число системных вызовов в интервале выборки (по умолчанию используется значение 10).  
  
 Параметр **Sys** можно указывать только в командной строке, которая также содержит параметр **Launch** или **Attach**.  
  
 По умолчанию событие выборки профилировщика равно числу циклов тактовой частоты ЦП, а интервал выборки равен 10 000 000. Параметры **Timer**, **PF**, **Sys** и **Counter** позволяют задать событие и интервал выборки. Параметр **GC** служит для сбора данных памяти .NET для каждого события выделения памяти и сборки мусора. В командной строке может быть указан только один из этих параметров.  
  
 Событие выборки и интервал выборки могут быть заданы только в первой командной строке, которая содержит параметр **Launch** или **Attach**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
VSPerfCmd.exe {/Launch:AppName|Attach:PID} /Sys[:Events] [Options]  
```  
  
#### <a name="parameters"></a>Параметры  
 `Events`  
 Целочисленное значение, которое задает число событий системных вызовов в интервале выборки. Если параметр `Events` не задан, то значение интервала по умолчанию равно 10.  
  
## <a name="required-options"></a>Обязательные параметры  
 Параметру **Sys** нужен один из следующих параметров:  
  
 **Launch:** `AppName`  
 Запускает профилировщик и приложение, заданное параметром `AppName`.  
  
 **Attach:** `PID`  
 Подключает профилировщик к процессу, указанному в параметре `PID`.  
  
## <a name="invalid-options"></a>Недопустимые параметры  
 Следующие параметры не могут быть указаны в одной командной строке с параметром **Sys**.  
  
 **PF**[**:**`Events`]  
 Задает в качестве события выборки ошибку выгрузки и при необходимости устанавливает интервал выборки, равный `Events`. Интервал PF по умолчанию — 10.  
  
 **Timer**[**:**`Cycles`]  
 Задает для события выборки значение, равное тактовой частоте процессора, и при необходимости задает для интервала выборки значение параметра `Cycles`. Значение этого параметра по умолчанию — 10 000 000.  
  
 **Counter:** `Name`[`,Reload`[`,FriendlyName`]]  
 Задает в качестве события выборки счетчик производительности ЦП, указанный параметром `Name`, и устанавливает интервал выборки, равный `Reload`.  
  
 **GC**[**:**{**Allocation**&#124;**Lifetime**}]  
 Собирает данные .NET. По умолчанию (**Allocation**) данные собираются для каждого события выделения памяти. Если указан параметр **Lifetime**, данные также собираются для каждого события сборки мусора.  
  
## <a name="example"></a>Пример  
 Этот пример демонстрирует присвоение событию выборки профилирования значения, равного числу системных вызовов, а также показывает, как задать интервал выборки, равный 20 вызовам.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /Sys:20  
```  
  
## <a name="see-also"></a>См. также  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Профилирование автономных приложений](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Профилирование веб-приложений ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Профилирование служб](../profiling/command-line-profiling-of-services.md)



