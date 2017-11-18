---
title: "Предупреждение безопасности. Присоединение к процессу, который принадлежит пользователю, не являющемуся доверенным, может быть опасным. Если следующие сведения не вызывают доверия, то не следует присоединяться к процессу | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.attachsecuritywarning"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 52246c1e-a371-40a0-b756-a435cc51876f
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Предупреждение безопасности. Присоединение к процессу, который принадлежит пользователю, не являющемуся доверенным, может быть опасным. Если следующие сведения не вызывают доверия, то не следует присоединяться к процессу
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Это диалоговое окно с предупреждением появляется непосредственно перед присоединением к процессу, который содержит частично доверенный код или принадлежит недоверенному пользователю.  Недоверенный процесс, содержащий вредоносный код, может нанести вред компьютеру, на котором выполняется отладка.  Если имеется причина не доверять процессу, следует нажать кнопку **Отмена** для предотвращения отладки.  
  
 Чтобы отключить это предупреждение при выполнении отладки в сценарии с заведомой надежностью процессов, закройте Visual Studio и введите значение "1" для следующего раздела реестра: `HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\<version>\Debugger\DisableAttachSecurityWarning`, после чего вновь запустите Visual Studio.  Завершив отладку данного сценария, вновь верните значение "0" и перезапустите Visual Studio.  
  
 К числу "доверенных пользователей" относится ваша учетная запись, а также набор стандартных пользователей, которые обычно определены на компьютерах с установленной платформой .NET Framework, например: `aspnet`, `localsystem`, `networkservice` и `localservice`.  
  
## Список элементов пользовательского интерфейса  
 Имя  
 Имя сборки, запрашиваемой для отладки  
  
 Пользователь  
 Текущий пользователь  
  
 Attach  
 Нажмите, чтобы продолжить отладку путем присоединения.  
  
 Не присоединяться  
 Не присоединяться к процессу.  
  
## См. также  
 [Присоединение к выполняемым процессам](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Безопасность отладчика](../debugger/debugger-security.md)