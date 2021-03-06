---
title: Безопасное развертывание
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- deploying applications [Office development in Visual Studio], security
- Office development in Visual Studio, security
- Office applications [Office development in Visual Studio], security
- ClickOnce deployment [Office development in Visual Studio], security
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 852e66bb4e29e732093cdac6b44c6791ad9b772d
ms.sourcegitcommit: be938c7ecd756a11c9de3e6019a490d0e52b4190
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50671084"
---
# <a name="secure-deployment"></a>Безопасное развертывание
  При создании решения Office, на компьютере разработчика обновляется автоматически, чтобы кода в проекте для запуска. Тем не менее, при развертывании решения, необходимо предоставить свидетельство, на котором основывается решение о доверии подписи решения с помощью сертификата или с помощью [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] ключ запроса доверия. Дополнительные сведения см. в разделе [предоставления доверия решениям Office](../vsto/granting-trust-to-office-solutions.md).  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Для настроек уровня документа Если развернуть его в сетевую папку, необходимо также добавить расположение документа в список надежных расположений в центре управления безопасностью приложения Office. Дополнительные сведения о методах настройки разрешений документа на компьютерах конечных пользователей, см. в разделе [предоставления доверия к документам](../vsto/granting-trust-to-documents.md).  
  
## <a name="prevent-office-solutions-from-running-code"></a>Предотвратить выполнение кода решений Office  
 Администраторы могут использовать реестр для предотвращения запуска на компьютере все решения Office. Решения Office, имеющая расширения управляемого кода открытием, Visual Studio Tools для Office среда выполнения проверяет ли запись с именем `Disabled` существует при выполнении одного из следующих разделов реестра на компьютере:  
  
- **HKEY_CURRENT_USER\Software\Microsoft\VSTO**  
  
- **Находится в другой**  
  
  Чтобы предотвратить выполнение кода решения Office, создайте `Disabled` запись в одном или обоих из этих разделов реестра и задайте одно из следующих типов данных и значения для `Disabled`:  
  
- REG_SZ или REG_EXPAND_SZ, которой присваивается любой строку, отличную от «0» (ноль).  
  
- Параметр типа REG_DWORD, которой присваивается значение, отличное от 0 (ноль).  
  
  Чтобы включить решения Office, для выполнения кода, установите для обоих атрибутов `Disabled` записей 0 (ноль), или удалить записи реестра.  
  
## <a name="see-also"></a>См. также  
 [Развертывание решения Office](../vsto/deploying-an-office-solution.md)   
 [Подготовка компьютеров для запуска или размещения решений Office](https://msdn.microsoft.com/be1b173f-7261-4d74-aa4e-94ccd43db8d8)   
 [Безопасные решения Office](../vsto/securing-office-solutions.md)  
  
  