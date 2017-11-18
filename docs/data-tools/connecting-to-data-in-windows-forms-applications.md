---
title: "Подключение к данным в приложениях Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "System.Data.SqlClient.SqlConnection"
  - "System.Data.Odbc.OdbcConnection"
  - "System.Data.OleDb.OleDbConnection"
  - "System.Data.OracleClient.OracleConnection"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "подключение к базам данных, ADO.NET - подключения"
  - "объекты подключения"
  - "объекты подключения, средства для работы с"
  - "объекты подключения, типы"
  - "объединение подключений в пул, ADO.NET - подключения"
  - "строки подключения [Visual Studio], ADO.NET"
  - "подключения, сведения о подключениях"
  - "подключения, время разработки"
  - "данные [Visual Studio], подключение"
  - "адаптеры данных, подключения"
  - "подключения к базам данных [Visual Studio], ADO.NET"
  - "базы данных [Visual Studio], подключение к"
  - "подключения во время разработки"
  - "динамические свойства, ADO.NET - подключения"
  - "OleDbConnection - класс, объекты подключения ADO.NET"
  - "SqlConnection - класс, объекты подключения ADO.NET"
  - "адаптеры таблиц TableAdapter, подключения"
  - "транзакции, ADO.NET"
ms.assetid: 184cbd0d-3b26-418d-a11c-f9f8f004fbff
caps.latest.revision: 31
caps.handback.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# Подключение к данным в приложениях Windows Forms
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] предоставляет средства для подключения вашего приложения к данным из множества разных источников, таких как базы данных, веб\-службы и объекты.  Если вы используете инструменты проектирования данных в [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], вам часто не требуется явно создавать объект подключения для своей формы или своего компонента.  Обычно объект подключения создается в результате выполнения одного из мастеров по работе с данными или перетаскивания объектов данных на форму.  Чтобы подключить приложение к базе данных, веб\-службе или объекту, запустите [мастер настройки источника данных](../data-tools/media/data-source-configuration-wizard.png), выбрав **Добавить новый источник данных** в окне [окно "Источники данных"](../Topic/Data%20Sources%20Window.md).  
  
 На следующей схеме показана стандартная последовательность операций для подключения к данным посредством выполнения запроса адаптера таблицы в целях получения данных и их отображения на форме в приложении Windows.  
  
 ![Поток данных в клиентском приложении](../data-tools/media/clientdatadiagram.gif "ClientDataDiagram")  
  
 В некоторых ситуациях объект подключения удобно создавать без использования инструментов проектирования данных.  Дополнительные сведения о программном создании подключений см. в разделе [Подключение к источнику данных](../Topic/Connecting%20to%20a%20Data%20Source%20in%20ADO.NET.md).  
  
> [!NOTE]
>  Дополнительные сведения о подключении веб\-приложений к данным см. в разделе [ASP.NET Data Access Content Map](http://msdn.microsoft.com/ru-ru/f9219396-a0fa-481f-894d-e3d9c67d64f2).  
  
## Пошаговые руководства по подключению приложений Windows Forms к данным  
 Следующие пошаговые руководства содержат описание процедур, связанных с подключением к данным в приложениях Windows Forms:  
  
-   [Пошаговое руководство. Подключение к данным в базе данных \(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20a%20Database%20\(Windows%20Forms\).md)  
  
-   [Пошаговое руководство. Подключение к данным в локальном файле базе данных \(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20a%20Local%20Database%20File%20\(Windows%20Forms\).md)  
  
-   [Пошаговое руководство. Подключение к данным в веб\-службе \(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20a%20Web%20Service%20\(Windows%20Forms\).md)  
  
-   [Пошаговое руководство. Подключение к данным в объектах \(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20Objects%20\(Windows%20Forms\).md)  
  
-   [Пошаговое руководство. Подключение к данным в базе данных Access \(Windows Forms\)](../data-tools/connect-to-data-in-an-access-database-windows-forms.md)  
  
## Создание подключений  
 В [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] подключения настраиваются с помощью диалогового окна **Добавить\/изменить подключение**.  Диалоговое окно **Добавить подключение** отображается при изменении или создании подключений в одном из мастеров по работе с данными или в [Обозревателе серверов\/баз данных](../Topic/Server%20Explorer.md) либо при изменении свойств подключения в окне **Свойства**.  
  
 Подключения к данным настраиваются автоматически при выполнении одного из следующих действий.  
  
|Действие|Описание|  
|--------------|--------------|  
|Запуск мастера [мастер настройки источника данных](../data-tools/media/data-source-configuration-wizard.png).|Подключения настраиваются, когда в **Мастере настройки источника данных** выбран путь к базе данных.  Для получения дополнительной информации см. [Практическое руководство. Подключение к данным в базе данных](../data-tools/how-to-connect-to-data-in-a-database.md).|  
|Запуск мастера [мастер настройки адаптера таблицы](../Topic/TableAdapter%20Configuration%20Wizard.md).|Подключения создаются в **Мастере настройки адаптера таблицы**.  Для получения дополнительной информации см. [Практическое руководство. Создание адаптера таблицы](../data-tools/create-and-configure-tableadapters.md).|  
|Запуск мастера [мастер настройки запроса TableAdapter](../data-tools/editing-tableadapters.md).|Подключения создаются в **Мастере настройки запроса адаптера таблицы**.  Для получения дополнительной информации см. [Практическое руководство. Создание запросов TableAdapter](../data-tools/how-to-create-tableadapter-queries.md).|  
|Перетаскивание элементов из окна [окно "Источники данных"](../Topic/Data%20Sources%20Window.md) на форму или в [Component Designer](../Topic/Component%20Designer.md).|Объекты подключения создаются при перетаскивании элементов из окна **Источники данных** на **Конструктор Windows Forms** или **Конструктор компонентов**.  Для получения дополнительной информации см. [Привязка элементов управления к данным в Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md).|  
|Добавление новых подключений к данным в [Обозреватель серверов\/баз данных](../Topic/Server%20Explorer.md).|Возможности подключения к данным в **обозревателе сервера или обозревателе базы данных** отображаются в списке доступных подключений в мастерах работы с данными.|  
  
## Строки подключения  
 Строки подключения могут храниться в скомпилированном приложении или в файле конфигурации приложения.  Для получения дополнительной информации см. [Практическое руководство. Сохранение и изменение строк подключения](../Topic/How%20to:%20Save%20and%20Edit%20Connection%20Strings.md).  
  
## Информация о подключении и безопасность  
 Поскольку открытие подключения связано с получением доступа к важному ресурсу — базе данных, часто при настройке подключения и работе с ним возникают проблемы безопасности.  
  
 Способ обеспечения безопасности приложения и доступа к источнику данных зависит от архитектуры системы.  Например, в веб\-приложении пользователи обычно получают анонимный доступ к службам IIS, и поэтому не предоставляют учетные данные безопасности.  В этом случае ваше приложение хранит собственную информацию для входа и использует ее для открытия подключения и доступа к базе данных вместо сведений конкретного пользователя.  
  
> [!IMPORTANT]
>  Хранение сведений строки подключения, например пароля, может повлиять на безопасность приложений.  Использование встроенных средств безопасности Windows — более безопасный способ управления доступом к базе данных.  Для получения дополнительной информации см. [Защита сведений о соединении](../Topic/Protecting%20Connection%20Information.md).  
  
 В приложениях интрасети или многоуровневых приложениях вы можете воспользоваться преимуществом встроенных средств безопасности, доступных в Windows, службах IIS и SQL Server.  При такой модели учетные данные аутентификации пользователя для локальной сети также используются для доступа к ресурсам базы данных, и в строке подключения не используется имя пользователя или пароль в явной форме.  Обычно разрешения задаются на компьютере сервера базы данных посредством групп, поэтому вам не нужно задавать отдельные разрешения для каждого пользователя, который может получить доступ к базе данных.  В такой модели вам вообще не нужно хранить сведения о входе для подключения, а дополнительные меры по обеспечению безопасности информации строк подключения не требуются.  
  
 Дополнительные сведения о безопасности см. в следующих разделах:  
  
-   [Защита приложений ADO.NET](../Topic/Securing%20ADO.NET%20Applications.md)  
  
-   [More Secure File and Data Access in Windows Forms](../Topic/More%20Secure%20File%20and%20Data%20Access%20in%20Windows%20Forms.md)  
  
## Подключения времени разработки в Обозревателе серверов\/баз данных  
 **Обозреватель серверов\/баз данных** позволяет вам создавать подключения времени разработки к источникам данных.  Это дает вам возможность просматривать доступные источники данных, отображать информацию о таблицах, столбцах и других содержащихся в них элементах, а также изменять и создавать элементы базы данных.  
  
 Ваше приложение не использует подключения, доступные в **Обозревателе серверов\/баз данных**, напрямую.  Это подключения используются [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] для работы с базой данных во время разработки.  Для получения дополнительной информации см. [Визуальные инструменты для баз данных](http://msdn.microsoft.com/ru-ru/6b145922-2f00-47db-befc-bf351b4809a1).  
  
 Например, во время разработки вы можете использовать **Обозреватель серверов\/баз данных** для создания подключения к базе данных.  Позднее, при разработке формы, вы можете просмотреть базу данных, выбрать столбцы из таблицы и перетащить их на [Конструктор наборов данных](../data-tools/creating-and-editing-typed-datasets.md).  При этом в вашем наборе данных создается [Адаптер таблицы](../data-tools/tableadapter-overview.md).  Также создается новый объект подключения, являющийся частью нового адаптера таблицы.  
  
 Информация о подключениях времени разработки хранится на локальном компьютере независимо от конкретного проекта или решения.  Таким образом, после задания подключения времени разработки при работе в приложении оно отображается в **Обозревателе серверов\/баз данных**, когда вы работаете в [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], пока доступен сервер, на который указывает это подключение.  Для получения дополнительной информации см. [How to: Connect to a Database from Server Explorer](http://msdn.microsoft.com/ru-ru/7c1c3067-0d77-471b-872b-639f9f50db74).  
  
 [!INCLUDE[SQLObjectExplorer](../data-tools/includes/sqlobjectexplorer_md.md)]  
  
## См. также  
 [Подключение к данным в Visual Studio](../data-tools/connecting-to-data-in-visual-studio.md)   
 [Практическое руководство. Подключение к данным в базе данных](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [Пошаговое руководство. Подключение к данным в базе данных \(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20a%20Database%20\(Windows%20Forms\).md)   
 [ASP.NET Data Access Content Map](http://msdn.microsoft.com/ru-ru/f9219396-a0fa-481f-894d-e3d9c67d64f2)   
 [Подготовка приложения к получению данных](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [Выборка данных в приложение](../data-tools/fetching-data-into-your-application.md)   
 [Привязка элементов управления к данным в Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [Редактирование данных в приложении](../data-tools/editing-data-in-your-application.md)   
 [Проверка данных](../Topic/Validating%20Data.md)   
 [Сохранение данных](../data-tools/saving-data.md)