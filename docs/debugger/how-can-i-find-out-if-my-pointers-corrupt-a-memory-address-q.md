---
title: Определить указатели поврежденный адрес памяти | Документация Майкрософт
ms.custom: seodec18
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- addresses, pointers corrupting memory address
- memory, corruption
- pointers, corrupting memory addresses
- memory address corruption by pointers
- debugging [C++], memory corruption
- corrupted memory address
ms.assetid: a147c939-4fb1-415c-8410-cf303781e9e8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 966a21bfbe5e6813bd4ea1cd6f11c682deea2d0f
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/07/2018
ms.locfileid: "53062987"
---
# <a name="how-can-i-find-out-if-my-pointers-corrupt-a-memory-address"></a>Как определить, повреждают ли указатели адрес памяти?
## <a name="problem-description"></a>Описание проблемы  
 Возможно, один из указателей повреждает память по адресу 0x00408000. Как определить, что происходит в этой точке?  
  
## <a name="solution"></a>Решение  
  
#### <a name="check-for-heap-corruption"></a>Проверка целостности кучи  
  
-   В большинстве случаев повреждение памяти происходит из-за повреждения кучи. Используйте программу глобальных флагов (gflags.exe) или pageheap.exe. См. в разделе [ http://support.microsoft.com/default.aspx?scid=kb; en-us; 286470](http://support.microsoft.com/default.aspx?scid=kb;en-us;286470).  
  
#### <a name="to-find-where-the-memory-address-is-modified"></a>Поиск места изменения адреса памяти  
  
1.  Задайте точку останова данных по адресу 0x00408000. Подробнее см. раздел [Установка точки останова, действующей при изменении данных (только для машинного кода C++)](../debugger/using-breakpoints.md#BKMK_set_a_data_breakpoint_native_cplusplus_only).  
  
2.  При попадании в точку останова используйте окно **Память** для просмотра содержимого памяти начиная с адреса 0x00408000. Дополнительные сведения см. в разделе [памяти Windows](../debugger/memory-windows.md).  
  
## <a name="see-also"></a>См. также  
 [Вопросы и ответы по отладке машинного кода](../debugger/debugging-native-code-faqs.md)   
 [Отладка машинного кода](../debugger/debugging-native-code.md)