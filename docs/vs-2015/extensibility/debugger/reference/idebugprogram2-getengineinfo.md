---
title: IDebugProgram2::GetEngineInfo | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProgram2::GetEngineInfo
helpviewer_keywords:
- IDebugProgram2::GetEngineInfo
ms.assetid: 3a4f2dc0-e082-4d8d-aeaf-463ab09d279b
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8980a3e19b115145129c14fd51278a745320e033
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51809848"
---
# <a name="idebugprogram2getengineinfo"></a>IDebugProgram2::GetEngineInfo
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Возвращает имя и идентификатор GUID для обработчика отладки (DE), выполнение программы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp#  
HRESULT GetEngineInfo(   
   BSTR* pbstrEngine,  
   GUID* pguidEngine  
);  
```  
  
```csharp  
int GetEngineInfo(   
   out string pbstrEngine,  
   out GUID   pguidEngine  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pbstrEngine`  
 [out] Возвращает имя DE, выполнение программы.  
  
 `pguidEngine`  
 [out] Возвращает идентификатор GUID для DE, выполнение программы.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.  
  
## <a name="remarks"></a>Примечания  
 Каждый DE определяет собственный идентификатор GUID для идентификации.  
  
## <a name="see-also"></a>См. также  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)

