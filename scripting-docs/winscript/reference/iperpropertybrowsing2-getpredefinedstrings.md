---
title: IPerPropertyBrowsing2::GetPredefinedStrings | Документация Майкрософт
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IPerPropertyBrowsing2.GetPredefinedStrings
apilocation:
- scrobj.dll
helpviewer_keywords:
- IPerPropertyBrowsing2::GetPredefinedStrings
ms.assetid: d2fa30f7-a566-4dbd-8b47-ffdc00419771
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a60225e69a04399a3ff0160291b84e9f3fda513c
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49915970"
---
# <a name="iperpropertybrowsing2getpredefinedstrings"></a>IPerPropertyBrowsing2::GetPredefinedStrings
Позволяет вызывающему объекту заполнить поле со списком сосчитанный массив указателей на строки, которые представляют возможные значения этого свойства.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetPredefinedStrings(  
   DISPID  dispid,  
   CALPOLESTR*  pCaStrings,  
   CADWORD*  pCaCookies  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `dispid`  
 [in] Идентификатор диспетчера свойства, для которого вызывающий объект запрашивает список строк.  
  
 `pCaStrings`  
 [out] Указатель на структуру выделенный вызывающим объектом одномерный сосчитанный массив, содержащий адрес метода выделенный массив указателей на строки и количество элементов. Если происходит сбой метода, память не выделяется и содержимое структуры не определено.  
  
 `pCaCookies`  
 [out] Указатель на структуру одномерный сосчитанный массив выделенный вызывающим объектом, который содержит количество элементов и адрес метод выделенный массив DWORD. Если происходит сбой метода, память не выделяется и содержимое структуры не определено.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает допустимый `HRESULT`, обычно `S_OK`.  
  
## <a name="see-also"></a>См. также  
 [Интерфейс 1 IPerPropertyBrowsing2](../../winscript/reference/iperpropertybrowsing2-interface-1.md)