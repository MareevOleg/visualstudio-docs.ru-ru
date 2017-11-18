---
title: "В редакторе ядра | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "редакторы [Visual Studio SDK] прежних версий - базового редактора"
ms.assetid: 8265f31c-c45b-4858-882c-6d9f1e3b9083
caps.latest.revision: 21
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 21
---
# В редакторе ядра
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] редактор набора core нескольких компонентов, которые позволяют изменять и запросить данные в текстовом виде.  Если вы настраивали редактор с использованием традиционного основного API, то можно продолжить использовать эти настройки, которые направляются через адаптеров редактора.  Рекомендуется, однако, что адаптации в API настройки в новый редактор.  
  
 Следующие области некоторые важные основные аспекты редактора.  
  
-   Текстовый буфер  
  
-   Представление текста  
  
-   Окно кода  
  
-   Текст метки  
  
-   Диспетчер текста  
  
-   Интеграция со службами языка  
  
## В этом подразделе  
 [Создание базового редактора с помощью API прежних версий](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)  
 Содержит пошаговые инструкции по использованию <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> создать экземпляр редактора.  
  
 [Доступ к текстовый буфер с помощью API прежних версий](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)  
 Описывает роль текстового буфера в редакторе, описание, связанные переменные, которые используются для доступа к буфер, а также предоставляет список интерфейсов, реализованных объектом текстового буфера <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>.  
  
 [Текст события буфера в интерфейсе API прежних версий](../extensibility/text-buffer-events-in-the-legacy-api.md)  
 Предоставляет список интерфейсов, которые используются для уведомления событий текстового буфера.  
  
 [Практическое руководство: регистрация для событий текстового буфера с помощью API прежних версий](../Topic/How%20to:%20Register%20for%20Text%20Buffer%20Events%20with%20the%20Legacy%20API.md)  
 Описывает, как advise события текстового буфера.  
  
 [С помощью диспетчера текст для наблюдения за глобальные параметры](../extensibility/using-the-text-manager-to-monitor-global-settings.md)  
 Описывает, как диспетчер текста используется совместно использовать глобальные данные настройки редактора с компонентами основные и, как получить уведомление о событиях диспетчер текста.  
  
 [Доступ к theText представление с помощью API прежних версий](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)  
 Содержит описание роли представления текста в редакторе и перечислены базовые интерфейсы, реализованные <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> объект.  
  
 [Настройка кода Windows с помощью API прежних версий](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)  
 Предоставляет сведения о том, как окно кода используется для заключения в них представление текста, рассматриваются как диспетчер окон кода позволяет реализовать оформление окно кода, и обеспечивает уведомление новых представлений.  
  
 [Изменение параметров представления с помощью API прежних версий](../extensibility/changing-view-settings-by-using-the-legacy-api.md)  
 Содержит пошаговые инструкции о том, как обеспечить параметры представления и как удалить принудительную параметры.  
  
 [Языковые службы и базовый редактор](../extensibility/language-services-and-the-core-editor.md)  
 Описывает создание экземпляра службы языка в украшениям кода элемента управления.  
  
## Связанные подразделы  
 [Пошаговое руководство: Создание базового редактора и регистрация файла тип редактора](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)  
 Содержит пошаговые инструкции о том, как запустить редактор core из управляемого кода.  
  
 [Раскрывающийся список](../extensibility/drop-down-bar.md)  
 Обсуждается черта используется раскрывающемся списке в окне кода и описывает интерфейсы, используемые при реализации черта раскрывающемся списке.  
  
 [С помощью текстовых маркеров с API прежних версий](../extensibility/using-text-markers-with-the-legacy-api.md)  
 Описывается понятие меток текст и способ их использования в редакторе, и содержит интерфейсы, используемые для доступа и управления текстовой метки.  
  
 [Практическое руководство: Добавление маркеров стандартный текст](../extensibility/how-to-add-standard-text-markers.md)  
 Содержит пошаговые инструкции о том, как создать маркер текст и добавление пользовательской команды в контекстное меню.  
  
 [Практическое руководство: Создание пользовательского текста маркеры](../extensibility/how-to-create-custom-text-markers.md)  
 Содержит пошаговые инструкции о том, как создать пользовательскую метку, текст и предоставить тип маркера в качестве службы.