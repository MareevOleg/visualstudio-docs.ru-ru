---
title: "IEnumDebugObjects::Reset | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEnumDebugObjects::Reset"
helpviewer_keywords: 
  - "Метод IEnumDebugObjects::Reset"
ms.assetid: 4a245e47-cc39-4177-b83d-083ea0e3190f
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# IEnumDebugObjects::Reset
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

Этот метод сбросит перечисление к первому элементу.  
  
## Синтаксис  
  
```cpp#  
HRESULT Reset(void);  
```  
  
```c#  
int Reset();  
```  
  
#### Параметры  
 None  
  
## Возвращаемое значение  
 В случае успеха возвращает `S_OK`; в противном случае возвращает код ошибки.  
  
## Заметки  
 После вызова этого метода, следующий вызов [Далее](../../../extensibility/debugger/reference/ienumdebugobjects-next.md) возвращает первый элемент перечисления.  
  
## См. также  
 [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md)   
 [Далее](../../../extensibility/debugger/reference/ienumdebugobjects-next.md)