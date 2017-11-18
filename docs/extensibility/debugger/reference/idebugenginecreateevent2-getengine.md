---
title: "IDebugEngineCreateEvent2::GetEngine | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugEngineCreateEvent2::GetEngine"
helpviewer_keywords: 
  - "IDebugEngineCreateEvent2::GetEngine"
ms.assetid: 187d24ed-9f9a-4418-a0ef-b8a19f54652c
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugEngineCreateEvent2::GetEngine
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

Извлекает объект, представляющий только что созданный обработчик отладки \(DE\).  
  
## Синтаксис  
  
```cpp#  
HRESULT GetEngine(   
   IDebugEngine2** pEngine  
);  
```  
  
```c#  
int GetEngine(   
   out IDebugEngine2 pEngine  
);  
```  
  
#### Параметры  
 `pEngine`  
 \[out\] возвращает [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) объект, представляющий созданный DE.  
  
## Возвращаемое значение  
 В случае успеха возвращает `S_OK`; в противном случае возвращает код ошибки.  
  
## См. также  
 [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)