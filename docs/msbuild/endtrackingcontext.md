---
title: "EndTrackingContext | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
apiname: EndTrackingContext
apilocation: filetracker.dll
apitype: COM
helpviewer_keywords: EndTrackingContext
ms.assetid: c2c5d794-8dc8-4594-8717-70dc79a0e75d
caps.latest.revision: "3"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 39313dd4bec3e5111aee588422080657d5a897d6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
---
# <a name="endtrackingcontext"></a>EndTrackingContext
Конц текущего контекста отслеживания.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT WINAPI EndTrackingContext();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 **HRESULT** с установленным битом **SUCCEEDED**, если контекст отслеживания был закончен.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** FileTracker.h  
  
## <a name="see-also"></a>См. также  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)