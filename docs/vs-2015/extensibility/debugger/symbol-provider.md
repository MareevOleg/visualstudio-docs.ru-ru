---
title: Символ поставщика | Документация Майкрософт
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
- symbol handler
- debugging [Debugging SDK], symbol handler
ms.assetid: 5fce651b-fead-4418-81b0-a011df7644ab
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 31bfba509081b47988e25beae79529df7f20a760
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51758036"
---
# <a name="symbol-provider"></a>Поставщик символов
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Реализация вычислителя выражений необходимо получить доступ к символической отладочной информации, создаваемой компилятором языка для оценки переменных и выражений. Это достигается путем использования интерфейсы поставщика символов (SP), также вызывается обработчик символов.  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] SPs предоставляет для управляемого кода, а также машинного кода, в формате базы данных программы (PDB) символов. При отсутствии надежный, необходимые для вашей программы символов, хранящихся в пользовательском формате, это рекомендуется использовать пакеты обновления, предоставляемые [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
## <a name="implementation-notes"></a>Примечания по реализации  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Отладчиков ожидать, что дает возможность общаться с SPs, с помощью интерфейсов Common Language Runtime (CLR). Таким образом SP, который будет использоваться механизмы отладки Visual Studio должна поддерживать среды CLR. Полный список всех интерфейсами отладки среды CLR можно найти в debugref.doc, входящий в состав из [!INCLUDE[winsdklong](../../includes/winsdklong-md.md)].  
  
 Если ваш пакет будет работать только с вашего пользовательского модуля отладки, можно реализовать SP по своему усмотрению в зависимости от потребностей вашего модуля отладки.  
  
## <a name="see-also"></a>См. также  
 [Компоненты отладчика](../../extensibility/debugger/debugger-components.md)

