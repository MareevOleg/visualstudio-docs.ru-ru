---
title: "Как: Добавление надежного издателя на клиентский компьютер для приложений ClickOnce | Документы Microsoft"
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
- ClickOnce deployment, install without prompting
- trusted application deployment, Trusted Publishers
ms.assetid: 35fe324c-45a1-4509-b7be-5c18b4b1b4ab
caps.latest.revision: "10"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 7b88b91111b40ae898fc53ad6bf4435e782a30b5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications"></a>Инструкции: добавление надежного издателя на клиентский компьютер для приложений ClickOnce
С помощью технологии развертывания доверенных приложений можно настроить клиентские компьютеры так, чтобы ваши приложения [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] выполнялись с более высоким уровнем доверия без вывода запроса пользователю. Следующие процедуры показывают, как использовать программу командной строки CertMgr.exe для добавления сертификата издателя в хранилище надежных издателей на клиентском компьютере.  
  
 Используемые команды могут незначительно отличаться в зависимости от того, является ли центр сертификации (ЦС), выдавший сертификат, частью доверенной корневой области клиента. Если клиентский компьютер Windows входит в состав домена, он будет содержать перечень доверенных корневых центров сертификации. Обычно этот список настраивается системным администратором. Если сертификат был выдан одним из этих доверенных корневых ЦС либо центром, связанным с одним из таких доверенных корневых ЦС, его можно добавить в доверенное корневое хранилище клиента. С другой стороны, если сертификат не был выдан одним из этих доверенных корневых ЦС, необходимо добавить его как в доверенное корневое хранилище клиента, так и в хранилище надежных издателей.  
  
> [!NOTE]
>  Подобным образом следует добавить сертификаты на каждый клиентский компьютер, где вы планируете развернуть приложение [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] , которое требует повышенного уровня разрешений. Сертификаты добавляются вручную или с помощью приложения, развернутого на клиентских компьютерах. Эти компьютеры нужно настроить всего один раз, после чего можно развернуть любое число приложений [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] , подписанных с помощью того же сертификата.  
  
 Кроме того, можно добавить сертификат в хранилище программным способом с помощью класса <xref:System.Security.Cryptography.X509Certificates.X509Store> .  
  
 Общие сведения о развертывании доверенных приложений см. в разделе [Trusted Application Deployment Overview](../deployment/trusted-application-deployment-overview.md).  
  
### <a name="to-add-a-certificate-to-the-trusted-publishers-store-under-the-trusted-root"></a>Добавление сертификата в хранилище надежных издателей в доверенной корневой области  
  
1.  Получите цифровой сертификат в центре сертификации.  
  
2.  Экспортируйте сертификат в формат Base64 X.509 (CER). Дополнительные сведения о форматах сертификатов см. в разделе [Экспорт сертификата](http://go.microsoft.com/fwlink/?LinkId=164793).  
  
3.  В командной строке на клиентских компьютерах выполните следующую команду:  
  
     **certmgr.exe -add certificate.cer -c -s -r localMachine TrustedPublisher**  
  
### <a name="to-add-a-certificate-to-the-trusted-publishers-store-under-a-different-root"></a>Добавление сертификата в хранилище надежных издателей в другой корневой области  
  
1.  Получите цифровой сертификат в центре сертификации.  
  
2.  Экспортируйте сертификат в формат Base64 X.509 (CER). Дополнительные сведения о форматах сертификатов см. в разделе [Экспорт сертификата](http://go.microsoft.com/fwlink/?LinkId=164793).  
  
3.  В командной строке на клиентских компьютерах выполните следующую команду:  
  
     **certmgr.exe -add good.cer -c -s -r localMachine Root**  
  
     **certmgr.exe -add good.cer -c -s -r localMachine TrustedPublisher**  
  
## <a name="see-also"></a>См. также  
 [Пошаговое руководство. Развертывание вручную приложения ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)   
 [Защита приложений ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Управление доступом для кода для приложения ClickOnce](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce и технология Authenticode](../deployment/clickonce-and-authenticode.md)   
 [Общие сведения о развертывании доверенных приложений](../deployment/trusted-application-deployment-overview.md)   
 [Практическое руководство. Включение параметров безопасности ClickOnce-приложений.](../deployment/how-to-enable-clickonce-security-settings.md)   
 [Практическое руководство. Установка зоны безопасности для ClickOnce-приложения](../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md)   
 [Практическое руководство. Установка пользовательских разрешений для ClickOnce-приложения](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [Практическое руководство. Отладка ClickOnce-приложения с ограниченными разрешениями](../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [Как: Добавление надежного издателя на клиентский компьютер для приложений ClickOnce](../deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications.md)   
 [Как: повторной подписи манифестов приложения и развертывания](../deployment/how-to-re-sign-application-and-deployment-manifests.md)   
 [Практическое руководство. Настройка поведения запроса о доверии ClickOnce](../deployment/how-to-configure-the-clickonce-trust-prompt-behavior.md)