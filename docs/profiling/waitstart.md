---
title: WaitStart | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 6c737177-2dfb-4150-963e-a49ac9aaa591
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 059f05d25f1882cd857dd1e39ea40a58a7c5e1d3
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34571374"
---
# <a name="waitstart"></a>WaitStart
Благодаря параметру WaitStart подкоманда *VSPerfCmd.exe* Start возвращается только после инициализации профилировщика или через указанное число секунд. По умолчанию команда Start возвращается немедленно. Если подкоманда Start возвращается без инициализации профилировщика, возвращается ошибка. Если не указано число секунд, команда Start ожидает неограниченное время.  
  
 Параметр WaitStart полезно использовать в пакетных файлах, чтобы обеспечивать инициализацию профилировщика.  
  
## <a name="syntax"></a>Синтаксис  
  
```cmd  
VSPerfCmd.exe /Start:Method /Output:FileName[Options] /StartWait[:Seconds]  
```  
  
#### <a name="parameters"></a>Параметры  
 `Seconds`  
 Число секунд ожидания перед возвращением подкоманды Start.  
  
## <a name="required-options"></a>Обязательные параметры  
 Параметр WaitStart может использоваться только с подкомандой Start.  
  
 **Output:** `filename`  
 Задает имя выходного файла.  
  
## <a name="remarks"></a>Примечания  
  
## <a name="example"></a>Пример  
 В этом примере пакетного файла команда Start ожидает инициализацию профилировщика 5 секунд.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WaitStart:5  
if not %errorlevel% 0 goto :error_tag  
VSPerfCmd.exe /Launch:TestApp.exe  
goto :end  
:error_tag  
@echo Could not start Profiler!  
@echo Error %errorlevel%  
:end  
```