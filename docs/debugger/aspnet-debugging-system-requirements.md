---
title: 'Отладка ASP.NET: Системные требования | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging ASP.NET Web applications, system requirements
- debugging ASP.NET Web applications, security requirements
ms.assetid: 7810b9b2-debf-4271-8fc7-1df031123255
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 71b6cbc3f523b8f21b21b0e69b1d6e45e23acb0c
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49915351"
---
# <a name="aspnet-debugging-system-requirements"></a>Отладка ASP.NET: системные требования
В этом разделе описаны требования к программному обеспечению и безопасности для сценариев локальной и удаленной отладки [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] .  
  
- При локальной отладке [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] и веб-приложение выполняются на одном и том же компьютере. Существуют две версии этого сценария:  
  
  - код [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] располагается в файловой системе;  
  
  - код [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] располагается на веб-сайте служб IIS.  
  
- При удаленной отладке [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] выполняется на клиентском компьютере и используется для отладки веб-приложения, работающего на удаленном (серверном) компьютере.  
  
## <a name="security-requirements"></a>Требования безопасности  
 Для удаленной отладки локальный и удаленный компьютеры должны входить в домен или рабочую группу.  
  
 Для отладки [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] рабочий процесс (с размещением, пул приложений), необходимо иметь разрешение на отладку этого процесса. По умолчанию [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] приложений IIS 6.0 и предыдущих Запуск от имени **ASPNET** пользователя. В IIS 6.0 и IIS 7.0 **СЕТЕВОЙ службы** учетной записи используется по умолчанию. Если рабочий процесс выполняется от имени учетной записи **ASPNET**или **NETWORK SERVICE**, для его отладки необходимо иметь права администратора.

 > [!IMPORTANT]
 > Начиная с Windows Server 2008 R2, мы рекомендуем использовать [ApplicationPoolIdentity](/iis/manage/configuring-security/application-pool-identities) с удостоверением, для каждого пула приложений.
  
 Имя рабочего процесса [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] варьируется в зависимости от сценария отладки и версии служб IIS. Дополнительные сведения см. в разделе [Практическое руководство. Поиск имени процесса ASP.NET](../debugger/how-to-find-the-name-of-the-aspnet-process.md).  
  
 Вы можете изменить учетную запись пользователя, от имени которой должен выполняться рабочий процесс [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] . Для этого следует внести соответствующие изменения в файл machine.config на сервере, на котором запускаются службы IIS. Оптимальный способ сделать это — с помощью **Диспетчера служб IIS**. Дополнительные сведения см. в разделе [как: запустить рабочий процесс в учетной записи пользователя](../debugger/how-to-run-the-worker-process-under-a-user-account.md).  
  
 Если в качестве учетной записи, от имени которой должен запускаться рабочий процесс [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] , указать собственную учетную запись, то обладать правами администратора на сервере, на котором работают службы IIS, не потребуется.  
  
> [!CAUTION]
>  Прежде чем запускать рабочий процесс [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] от имени другой учетной записи, проанализируйте последствия возможной вредоносной атаки на рабочий процесс [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] при его выполнении от имени этой учетной записи. Учетные записи ASPNET и NETWORK SERVICE обладают минимальным набором разрешений, минимизируя возможный вред в случае вредоносной атаки на процесс. При выполнении рабочего процесса [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] от имени учетной записи с более широким объемом прав объем возможного вреда возрастает.  
  
## <a name="see-also"></a>См. также  
 [Отладка приложений ASP.NET](../debugger/how-to-enable-debugging-for-aspnet-applications.md)   
 [Практическое руководство. Выполнение рабочего процесса с учетной записью пользователя](../debugger/how-to-run-the-worker-process-under-a-user-account.md)