---
title: "IDebugReference2::GetParent | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugReference2::GetParent
helpviewer_keywords:
- IDebugReference2::GetParent
ms.assetid: e3061665-ad3e-4c1b-b33f-82755fa21be3
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 6ad3a164eb6a214d0fa35cface5d157567d52eb7
ms.contentlocale: ru-ru
ms.lasthandoff: 09/26/2017

---
# <a name="idebugreference2getparent"></a>IDebugReference2::GetParent
Возвращает ссылку на родительской ссылки. Зарезервировано для будущего использования.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetParent (   
   IDebugReference2** ppParent  
);  
```  
  
```csharp  
int GetParent (   
   out IDebugReference2 ppParent  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppParent`  
 [out] Возвращает [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) , представляющий родителя данного свойства.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение `E_NOTIMPL`.  
  
## <a name="see-also"></a>См. также  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)