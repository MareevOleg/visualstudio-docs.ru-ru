---
title: 'Практическое: изменить вариант пошаговой отладки (для прежних версий) | Документация Майкрософт'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- branch stepping
- debugging, stepping options
- debugging workflows, stepping options
- stepping, changing options
- instance stepping
ms.assetid: aedc06af-d58a-44d6-aee4-f397f1f923a0
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: b89ad55fec7b15884acefd5607cfd863a45564b3
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49179248"
---
# <a name="how-to-change-the-debug-stepping-option-legacy"></a>Как изменить вариант пошаговой отладки (для прежних версий)
В этом разделе описывается изменение варианта пошаговой отладки для приложений [!INCLUDE[wf](../includes/wf-md.md)] прежних версий [!INCLUDE[wfd1](../includes/wfd1-md.md)] с параллельными действиями. [!INCLUDE[wfd2](../includes/wfd2-md.md)] прежних версий используется при создании приложений для [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] или [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
 При отладке действия прежних версий, которые выполняются одновременно, таких как **ParallelActivity** или **ConditionedActivityGroup**, можно использовать один из двух вариантов для пошаговой проверки кода.  
  
 Выполните следующие действия, чтобы изменить вариант пошаговой отладки в проекте рабочего процесса прежних версий.  
  
## <a name="procedures"></a>Процедуры  
  
#### <a name="to-change-the-debug-stepping-option"></a>Изменение варианта пошаговой отладки  
  
1.  Запустите Visual Studio.  
  
2.  Откройте существующий проект рабочего процесса прежних версий или создайте новый проект, в котором применяются параллельные действия и который предназначен для работы с [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] или [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
3.  На **рабочего процесса** меню прежних версий [!INCLUDE[wfd2](../includes/wfd2-md.md)], пункты **Отладка**, а затем **варианты пошаговой отладки**.  
  
4.  Выберите либо **экземпляр** или **ветви**.  
  
## <a name="see-also"></a>См. также  
 [Отладка рабочих процессов для прежних версий](../workflow-designer/debugging-legacy-workflows.md)   
 [Варианты пошаговой отладки (для прежних версий)](../workflow-designer/debug-stepping-options-legacy.md)