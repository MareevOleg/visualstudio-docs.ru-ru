---
title: "IDebugWindowsComputerPort2::GetComputerInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "GetComputerInfo"
  - "IDebugWindowsComputerPort2::GetComputerInfo"
ms.assetid: 654910b2-c239-44c8-92fc-317680a5672f
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugWindowsComputerPort2::GetComputerInfo
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

Извлекает сведения о компьютере, на котором отладчик находится в запущенном.  
  
## Синтаксис  
  
```cpp#  
HRESULT GetComputerInfo(  
   COMPUTER_INFO * pInfo  
);  
```  
  
```c#  
public int GetComputerInfo(  
   out COMPUTER_INFO[] pInfo  
);  
```  
  
#### Параметры  
 `pInfo`  
 \[out\] ссылка на структуру, содержащую сведения о компьютере.  
  
## Возвращаемое значение  
 В случае успеха возвращает `S_OK`; в противном случае возвращает код ошибки.  
  
## См. также  
 [IDebugWindowsComputerPort2](../../../extensibility/debugger/reference/idebugwindowscomputerport2.md)   
 [COMPUTER\_INFO](../../../extensibility/debugger/reference/computer-info.md)