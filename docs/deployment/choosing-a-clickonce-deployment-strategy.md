---
title: "Выбор стратегии развертывания ClickOnce | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, strategies
- deploying applications, ClickOnce
ms.assetid: 98bcab65-ab8b-4ed1-9adc-fdacf92b8106
caps.latest.revision: "19"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: e0f39c75620eab8e94ecd65b1ab1f41cc5e67875
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2017
---
# <a name="choosing-a-clickonce-deployment-strategy"></a>Выбор стратегии развертывания ClickOnce
Существует три разные стратегии развертывания приложения [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. Выбираемая стратегия зависит главным образом от типа развертываемого приложения. Ниже перечисляются следующие три стратегии развертывания:  
  
-   установка из Интернета или общего сетевого ресурса;  
  
-   установка с компакт-диска;  
  
-   запуск приложения из Интернета или общего сетевого ресурса.  
  
    > [!NOTE]
    >  Помимо выбора стратегии развертывания потребуется также выбрать стратегию предоставления обновлений приложения. Дополнительные сведения см. в разделе [Выбор стратегии обновления ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md).  
  
## <a name="install-from-the-web-or-a-network-share"></a>установка из Интернета или общего сетевого ресурса;  
 При использовании этой стратегии приложение развертывается на веб-сервер или в общий сетевой файловый ресурс. Когда конечный пользователь хочет установить приложение, он или она щелкает значок на веб-странице или дважды щелкает значок в общем файловом ресурсе. Тогда приложение загружается, устанавливается и запускается на компьютере конечного пользователя. Элементы добавляются **запустить** меню и **Установка и удаление программ** в **панели управления**.  
  
 Так как эта стратегия зависит от связности узлов в сети, она оптимальна для приложений, которые разворачиваются для пользователей, имеющих доступ к локальной сети или высокоскоростное подключение к Интернету.  
  
 Если приложение развертывается из Интернета, можно передать аргументы в приложение при его активации с помощью URL-адреса. Дополнительные сведения см. в разделе [как: получение сведений строки запроса в приложение ClickOnce](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md). Аргументы невозможно передать в приложение, которое активируется с помощью любого другого метода, описанного в данном документе.  
  
 Чтобы активировать эту стратегию развертывания в [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], нажмите кнопку **из Интернета** или **из UNC-путь или общую папку** на **способ установки** страницы мастера публикации.  
  
 Эта стратегия развертывания используется по умолчанию.  
  
## <a name="install-from-a-cd"></a>установка с компакт-диска;  
 При использовании этой стратегии приложение развертывается на съемный носитель, такой как компакт-диск или DVD-диск. Как и в случае предыдущего варианта, когда пользователь выбирает установку приложения, оно устанавливается и запускается и добавления элементов **запустить** меню и **Установка и удаление программ** в **управления Панель**.  
  
 Эта стратегия оптимально подходит для приложений, которые развертываются для пользователей, не имеющих постоянной связности узлов сети или оснащенных малопроизводительными подключениями. Так как приложение устанавливается со съемного носителя, для установки не требуется сетевое подключение; однако связность узлов сети по-прежнему необходима для обновлений приложения.  
  
 Чтобы активировать эту стратегию развертывания в [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], нажмите кнопку **с компакт-диска или DVD-диска** на **способ установки** страницы мастера публикации.  
  
 Чтобы активировать эту стратегию развертывания вручную, измените **deploymentProvider** тег в манифесте развертывания. (В Visual Studio это свойство представляется как **URL-адрес установки** на **публикации** страницы конструктора проектов. Mage.exe в это **начальное местоположение**.)  
  
## <a name="start-the-application-from-the-web-or-a-network-share"></a>Запуск приложения из Интернета или общего сетевого ресурса  
 Эта стратегия подобна первой стратегии за исключением того, что приложение ведет себя как веб-приложение. Когда пользователь щелкает ссылку на веб-странице (или дважды щелкает значок в общем файловом ресурсе), запускается приложение. Когда пользователи закрывают приложение, оно больше не доступно на их локальном компьютере; ничего не добавляется к **запустить** меню или **Установка и удаление программ** в **панели управления**.  
  
> [!NOTE]
>  Технически приложение загружается и устанавливается в кэш приложения на локальном компьютере, точно так, как веб-приложение загружается в веб-кэш. Как и в случае веб-кэша, файлы в конечном счете извлекаются из кэша приложений. Однако согласно восприятию пользователя приложение выполняется из Интернета или общего файлового ресурса.  
  
 Данная стратегия оптимально подходит для приложений, которые используются редко — например средство расчета пособий работающим по найму, которое обычно выполняться лишь один раз в год.  
  
 Чтобы активировать эту стратегию развертывания в [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], нажмите кнопку **не устанавливать приложение** на **установить или выполнить из Интернета** страницы мастера публикации.  
  
 Чтобы активировать эту стратегию развертывания вручную, измените **установить** тег в манифесте развертывания. (Его значение может быть **true** или **false**. В Mage.exe, используйте **сети только** в диалоговом окне **тип приложения** список.)  
  
## <a name="web-browser-support"></a>Поддержка веб-браузера  
 Приложения, предназначенные для платформы .NET Framework 3.5, могут быть установлены с помощью любого браузера.  
  
 Для приложений, предназначенных для платформы .NET Framework 2.0, требуется Internet Explorer.  
  
## <a name="see-also"></a>См. также  
 [Развертывание и безопасность технологии ClickOnce](../deployment/clickonce-security-and-deployment.md)   
 [Выбор стратегии обновления ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md)   
 [Практическое руководство. Публикация приложения ClickOnce с помощью мастера публикации](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [Защита приложений ClickOnce](../deployment/securing-clickonce-applications.md)