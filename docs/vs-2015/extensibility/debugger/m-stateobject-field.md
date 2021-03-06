---
title: m_stateObject поле | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- m_stateObject field, Task class [.NET Framework debug engines]
ms.assetid: 68c54b22-3e1c-4031-b9c7-b972c519d8a0
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3231f63d91e8393e5fa1417d97202d1b46cdd571
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51732364"
---
# <a name="mstateobject-field"></a>Поле m_stateObject
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Объект, представляющий данные, которые будет использовать действие.  
  
 **Пространство имен:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Сборка:** mscorlib (в mscorlib.dll)  
  
 Так как не удается получить доступ к внутреннему элементу из .NET Framework, следующий синтаксис предоставляется общего промежуточного языка (CIL).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
.field assembly object m_stateObject  
```  
  
## <a name="remarks"></a>Примечания  
 Это `state` параметр в <xref:System.Threading.Tasks.Task.%23ctor%2A> конструктор. Это также резервное поле для <xref:System.Threading.Tasks.Task.AsyncState%2A?displayProperty=fullName> свойство.  
  
## <a name="see-also"></a>См. также  
 [Класс Task](../../extensibility/debugger/task-class-internal-members.md)

