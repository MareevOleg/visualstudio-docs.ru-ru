---
title: SuspendTracking | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
apiname:
- SuspendTracking
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- SuspendTracking
ms.assetid: f5e06e5a-8083-444c-99c1-07ba834226b5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b0d52fb5d50a75207a0aad49f7b29cfc66b8e889
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/19/2018
ms.locfileid: "39154200"
---
# <a name="suspendtracking"></a>SuspendTracking
Приостанавливает отслеживание в текущем контексте.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp 
HRESULT WINAPI SuspendTracking(void);  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 **HRESULT** с установленным битом **SUCCEEDED**, если отслеживание было приостановлено.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** *FileTracker.h*  
  
## <a name="see-also"></a>См. также  
 [ResumeTracking](../msbuild/resumetracking.md)