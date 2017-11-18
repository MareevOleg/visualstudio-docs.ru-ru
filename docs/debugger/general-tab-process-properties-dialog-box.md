---
title: "Вкладка &quot;Общие&quot; диалогового окна &quot;Свойства процесса&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Свойства процессов для Windows NT"
ms.assetid: 86f4d61d-a594-4aac-8960-c5279b4a10fd
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# Вкладка &quot;Общие&quot; диалогового окна &quot;Свойства процесса&quot;
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Вкладка **Общие** используется для получения дополнительных сведений о конкретном процессе.  Для отображения диалогового окна [Свойства процесса](../debugger/process-properties-dialog-box.md) переместите фокус в окно [Представление процессов](../debugger/processes-view.md).  Выберите любой узел процесса в дереве, а затем выберите в меню **Вид** пункт **Свойства**.  
  
 На вкладке **Общие** доступны следующие параметры.  
  
|Entry|Описание|  
|-----------|--------------|  
|**Имя модуля**|Имя модуля.|  
|**Идентификатор процесса**|Уникальный идентификатор этого процесса.  Номера идентификаторов процессов используются неоднократно; т. е. они определяют конкретный процесс только в течение времени его существования \(и могут определять другой процесс после завершения существования первого\).  При выполнении программы создается тип объекта процесса.  Все потоки процесса разделяют одно адресное пространство и могут обращаться к одним данным.|  
|**Базовый приоритет**|Текущий базовый приоритет процесса.  Потоки в пределах процесса могут повышать и понижать собственный базовый приоритет относительно базового приоритета самого процесса.|  
|**Потоки**|Количество потоков, активных в данный момент в процессе.|  
|**Время ЦП**|Общее время ЦП, затраченное на процесс и его потоки.  Равно сумме времени работы в пользовательском и привилегированном режимах.|  
|**Время работы в пользовательском режиме**|Общее время, затраченное процессом на выполнение кода в пользовательском режиме в небездействующих потоках.  Приложения выполняются в пользовательском режиме так же, как и подсистемы, например диспетчер окон и графическое ядро.|  
|**Время работы в привилегированном режиме**|Общее время, затраченное процессом в привилегированном режиме в небездействующих потоках.  Уровень служб, исполняющие подпрограммы и ядро выполняются в привилегированном режиме.  Драйверы большинства устройств, кроме графических адаптеров и принтеров, также выполняются в привилегированном режиме.  В дополнение к времени в привилегированном режиме некоторая работа, выполняемая операционной системой Windows для приложения, может попасть в процессы подсистем.|  
|**Затраченное время**|Общее время, в течение которого выполнялся процесс.|