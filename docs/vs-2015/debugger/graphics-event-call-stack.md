---
title: Стек вызовов событий графики | Документация Майкрософт
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
- vs.graphics.callstack
ms.assetid: 8a30168d-8b39-4de1-b094-c7356ba101a3
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7c6ac7860fe846c86d846fd668c4647cd4145756
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51762852"
---
# <a name="graphics-event-call-stack"></a>Стек вызовов событий графики
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Стек вызовов событий графики в анализаторе графики Visual Studio позволяет выявить связь между проблемными событиями графики и исходным кодом приложения.  
  
 Окно «Стек вызовов событий» выглядит так:  
  
 ![Стек вызовов на событие DrawIndexed. ](../debugger/media/gfx-diag-demo-graphics-event-call-stack-orientation.png "gfx_diag_demo_graphics_event_call_stack_orientation")  
  
## <a name="understanding-the-graphics-event-call-stack"></a>Основные сведения о стеке вызовов событий графики  
 Стек вызовов событий можно использовать для анализа потока выполнения, который привел к определенному событию Direct3D. Это окно напоминает окно стека вызовов Visual Studio за тем исключением, что вместо вывода текущего стека вызовов активного потока в выполняющемся приложении отображается стек вызовов в том состоянии, которое существовало, когда произошло выбранное событие Direct3D. Из стека вызовов событий можно перейти к месту вызова выбранного события Direct3D, чтобы проверить окружающий код.  
  
 Используя стек вызовов событий для определения пути кода, в котором возникает проблемное событие, и имеющиеся знания о базе кода, можно выявить возможные источники проблемы. Вы также можете добавить точки останова в исходный код приложения, чтобы использовать традиционные методы отладки для анализа того, как состояние приложения или параметры события вызывают неправильное поведение события. Такой анализ может помочь найти проблемы в исходном коде, которые проявляются только как проблемы отрисовки.  
  
### <a name="graphics-event-call-stack-information"></a>Данные стека вызовов событий графики  
 Стек вызовов событий не поддерживает события перед кадром или определенные пользователем события. Стек вызовов событий графики отображается в виде таблицы.  
  
|Столбец|Описание:|  
|------------|-----------------|  
|**Name**|Символ, который однозначно определяет функцию, содержащую место вызова. Отладочный символ для функции отображается, если он доступен; в противном случае отображается смещение функции.|  
|**Файл**|Имя файла исходного кода или файла библиотеки, содержащего место вызова.|  
|**Расположение**|Номер строки места вызова.|  
  
### <a name="links-to-graphics-objects"></a>Ссылки на графические объекты  
 Для анализа выбранного события графики могут понадобиться сведения об объектах Direct3D, с которыми оно связано. **Стек вызовов событий графики** окно предоставляет ссылки на эти сведения.  
  
## <a name="see-also"></a>См. также  
 [Пошаговое руководство. Отсутствие объектов вследствие заливки вершин](../debugger/walkthrough-missing-objects-due-to-vertex-shading.md)



