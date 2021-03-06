---
title: 'Практическое: проверка обновлений для приложения программным способом с помощью API развертывания ClickOnce | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, updates
- application updates
ms.assetid: 1a886310-67c8-44e5-a382-c2f0454f887d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 25585dce22f74c8e8b2f6aef253ea00c3a6ad4e8
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/19/2018
ms.locfileid: "39151397"
---
# <a name="how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api"></a>Практическое: проверка обновлений для приложения программным способом с помощью API развертывания ClickOnce
ClickOnce обеспечивает два способа обновления приложения после его развертывания. Во-первых можно настроить развертывание ClickOnce автоматически проверять наличие обновлений, через определенные промежутки времени. Во втором методе, можно написать код, использующий <xref:System.Deployment.Application.ApplicationDeployment> для проверки наличия обновлений на основе события, например запрос пользователя.  
  
 Следующие процедуры показан код для выполнения программного обновления, а также описывается настройка развертывания ClickOnce для обеспечения проверок программных обновлений.  
  
 Чтобы обновить приложение ClickOnce программно, необходимо указать расположение для обновления. Иногда это называется поставщик развертывания. Дополнительные сведения об установке данного свойства см. в разделе [Выбор стратегии обновления ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md).  
  
> [!NOTE]
>  Можно также использовать метод, описанный ниже для развертывания приложения из одного расположения, но обновить ее из другого. Дополнительные сведения см. в разделе [как: задание альтернативного местоположения для обновлений развертывания](../deployment/how-to-specify-an-alternate-location-for-deployment-updates.md).  
  
### <a name="to-check-for-updates-programmatically"></a>Чтобы проверить наличие обновлений программным способом  
  
1.  Создайте новое приложение Windows Forms с помощью в предпочитаемое средство командной строки или визуального элемента.  
  
2.  Создать любой кнопки, меню или другой элемент пользовательского интерфейса требуется пользователям выбирать проверить наличие обновлений. Из этого элемента в обработчик событий вызовите следующий метод для проверки и установки обновлений.  
  
     [!code-csharp[ClickOnceAPI#6](../deployment/codesnippet/CSharp/how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api_1.cs)]
     [!code-cpp[ClickOnceAPI#6](../deployment/codesnippet/CPP/how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api_1.cpp)]
     [!code-vb[ClickOnceAPI#6](../deployment/codesnippet/VisualBasic/how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api_1.vb)]  
  
3.  Скомпилируйте приложение.  
  
### <a name="use-mageexe-to-deploy-an-application-that-checks-for-updates-programmatically"></a>Развернуть приложение, которое проверяет наличие обновлений программным способом с помощью Mage.exe  
  
-   Следуйте инструкциям по развертыванию приложения с помощью Mage.exe, как описано в [Пошаговое руководство: развертывание вручную приложения ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). При вызове Mage.exe для создания манифеста развертывания, убедитесь, что для использования параметра командной строки `providerUrl`, а также указать URL-адрес, где приложение ClickOnce должно проверять наличие обновлений. Если приложение обновит из [ http://www.adatum.com/MyApp ](http://www.adatum.com/MyApp), например, при вызове создания манифеста развертывания может выглядеть следующим образом:  
  
    ```cmd 
    mage -New Deployment -ToFile WindowsFormsApp1.application -Name "My App 1.0" -Version 1.0.0.0 -AppManifest 1.0.0.0\MyApp.manifest -providerUrl http://www.adatum.com/MyApp/MyApp.application  
    ```  
  
### <a name="using-mageuiexe-to-deploy-an-application-that-checks-for-updates-programmatically"></a>Развертывание приложения, которое проверяет наличие обновлений программным способом с помощью MageUI.exe  
  
-   Следуйте инструкциям по развертыванию приложения с помощью Mage.exe, как описано в [Пошаговое руководство: развертывание вручную приложения ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). На **варианты развертывания** вкладке **начальное расположение** поле в манифест приложения ClickOnce должно проверять наличие обновлений. На **параметры обновления** вкладке Очистить **это приложение должно проверять наличие обновлений** "флажок".  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Приложение должно иметь разрешения полного доверия для использования программного обновления.  
  
## <a name="see-also"></a>См. также  
 [Практическое: задание альтернативного местоположения для обновлений развертывания](../deployment/how-to-specify-an-alternate-location-for-deployment-updates.md)   
 [Выбор стратегии обновления ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md)   
 [Публикация приложений ClickOnce](../deployment/publishing-clickonce-applications.md)