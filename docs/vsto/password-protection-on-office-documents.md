---
title: Защита паролей в документах Office
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- permissions [Office development in Visual Studio]
- workbooks [Office development in Visual Studio], restricted permissions
- passwords [Office development in Visual Studio], document protections
- documents [Office development in Visual Studio], restricted permissions
- Office documents [Office development in Visual Studio, restricted permissions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 02deaccdd615bae0c948d50abdd41758dc701704
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "35673881"
---
# <a name="password-protection-on-office-documents"></a>Защита паролей в документах Office
  Существует возможность установить пароль на свои документы Microsoft Office Word и книг Microsoft Office Excel, чтобы они не удается открыть тому, кто не знает пароль. Этот параметр называется **пароль для открытия**.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Вы можете создавать проекты уровня документа, с помощью существующих документов и книг, содержащих **пароль для открытия** включена. Поведение в Visual Studio отличается для документов Word и Excel, содержащих **пароль для открытия** включена.  
  
 Сведения о включении **пароль для открытия**, см. в справке в Word или Excel.  
  
## <a name="behavior-of-excel-and-word"></a>Поведение Excel и Word  
 Каждый раз при открытии книги Excel в Visual Studio, **пароль для открытия** включен, Excel предлагает вам ввести пароль. При построении решения вы будут запрашиваться пароль еще раз, так как документ открыт во время сборки.  
  
 Первый раз при открытии документа Word в Visual Studio, **пароль для открытия** включен, Word запросит пароль. После успешного ввода пароля, **пароль для открытия** удаляется из документа и открытии документа больше не требуется пароль. Если документ в решении для запрашивания пароля перед его можно открыть, необходимо включить **пароль для открытия** после последнего построения, и перед развертыванием решения.  
  
## <a name="see-also"></a>См. также  
 [Защита документов в решениях уровня документа](../vsto/document-protection-in-document-level-solutions.md)   
 [Управление правами и общие сведения о расширениях управляемого кода](../vsto/information-rights-management-and-managed-code-extensions-overview.md)   
 [Как: разрешить выполнения кода программной части документов с ограниченными разрешениями](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)   
 [Разработка и создание решений Office](../vsto/designing-and-creating-office-solutions.md)  
  
  