---
title: Порт поставщики | Документация Майкрософт
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
- port suppliers
- debugging [Debugging SDK], port suppliers
ms.assetid: a8f3db96-1a13-4e93-9ef6-0861880369e0
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c8ca5c7d9154b07cbc51b5fde6b9c85e97d880df
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51751583"
---
# <a name="port-suppliers"></a>Поставщики портов
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

С точки зрения архитектуры отладчика **поставщика порта**:  
  
- Находится на сервере и предоставляет порты на запрос к этому серверу.  
  
- Можно добавлять и удалять порты из содержащую сервер.  
  
- Можно перечислить все порты, которые он предоставил к серверу.  
  
- Представленный [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md) интерфейс, который регистрируется с помощью Visual Studio через реестр. Этот интерфейс можно получить, вызвав [GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md).  
  
  [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] предоставляет поставщика порта по умолчанию и порт по умолчанию. Если задан специальный порт должен быть реализован, поставщика пользовательского порта также необходимо реализовать для предоставления этих Настраиваемые порты.  
  
## <a name="see-also"></a>См. также  
 [Серверы](../../extensibility/debugger/servers-visual-studio-sdk.md)   
 [Порты](../../extensibility/debugger/ports.md)   
 [Отладчик: основные понятия](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)

