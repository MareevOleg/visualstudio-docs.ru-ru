---
title: "Практическое руководство. Обновление до локальной базы данных или продолжение работы с SQL Server Express | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "LocalDB"
  - "SQL Server, экспресс-выпуск"
  - "SQL Server LocalDB"
  - "SQLEXPRESS"
  - "обновление SQLExpress до SQLExpress"
  - "обновление до LocalDB"
ms.assetid: 14ca6f76-f80e-4926-8020-3fee2d802b75
caps.latest.revision: 33
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# Практическое руководство. Обновление до локальной базы данных или продолжение работы с SQL Server Express
В этом подразделе описываются параметры для обновления файла базы данных \(mdf\) после установите [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] и содержит инструкции для выполнения следующих задач:  
  
-   Обновление файла базы данных для использования LocalDB  
  
-   Обновление файла базы данных для использования новой версии SQL Server Express  
  
-   Работа с файлом базы данных, в [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], но сохраняет совместимость с [!INCLUDE[ssKatmai_exp](../data-tools/includes/sskatmai_exp_md.md)]  
  
-   Сделайте SQL Server Express обработчик базы данных по умолчанию  
  
 Можно использовать [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] чтобы открыть проект, содержащий файл базы данных \(mdf\), который был создан с использованием более старой версии SQL Server Express.  Однако продолжения разработки проекта в [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], необходимо иметь то, что версия SQL Server Express установлена на одном механической обработке подвергает как Visual Studio или необходимо обновить файл базы данных SQL Server Express LocalDB.  При обновлении файла базы данных, невозможно будет получить доступ к его с предыдущими версиями SQL Server Express.  
  
 Можно также быть предложено обновить файл базы данных, созданный с помощью [!INCLUDE[sql_Denali_exp](../data-tools/includes/sql_denali_exp_md.md)] если версия файла не совместима с экземпляром SQL Server Express, который в данный момент установленно.  Чтобы разрешить проблему, Visual Studio предложит обновить файл до более новой версии SQL Server Express.  
  
> [!IMPORTANT]
>  Рекомендуется создать резервную копию файла базы данных перед обновлением.  
  
 Перед обновлением базы данных нужно учесть следующие условия:  
  
-   Обновление если требуется работать в проекте как в [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)], так и в [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].  
  
-   Обновление если приложение будет использоваться в средах, которые используют SQL Server Express, а не LocalDB.  
  
-   Обновление если приложение использует удаленные соединения, поскольку LocalDB не поддерживает их.  
  
-   Обновление если приложение полагается на службы IIS \(IIS\).  
  
-   Попробуйте обновить если требуется приложениям тестовой базы данных среды, " песочницы ", но не те управления базой данных.  
  
### Обновление файла базы данных для использования LocalDB  
  
1.  В **Обозреватель серверов**, нажмите кнопку **\*\*\* подключение к базе данных \*\*\***.  
  
2.  В диалоговом окне **Добавить подключение** укажите следующие сведения:  
  
    -   **\*\*\* источник данных: \*\*\*** Microsoft SQL Server \(SqlClient\)  
  
    -   **\*\*\* имя сервера: \*\*\*** \) \(LocalDB \\ v11.0  
  
    -   **\*\*\* Вложение файла базы данных. \*\*\*** *путь*, где *путь* физический путь первичного файла mdf.  
  
    -   **Logical Name:** *имя*, где *имя* имя, которое необходимо использовать с файлом.  
  
3.  Нажмите кнопку **ОК**.  
  
4.  Получив приглашение, нажмите кнопку **\*\*\* да \*\*\*** для обновления файла.  
  
 Обновить базу данных, вложенный к компоненту database engine LocalDB и больше не совместимый с [!INCLUDE[ssKatmai_exp](../data-tools/includes/sskatmai_exp_md.md)].  
  
 Можно также изменить подключение SQLExpress для использования LocalDB путем открытия контекстного меню для подключения, а затем выбрать **Изменение подключения**.  В **Изменение подключения** диалогового окна, измените имя сервера в LocalDB\) \(\\ v11.0.  В диалоговом окне **Дополнительные свойства**, убедитесь, что **\*\*\* пользовательский экземпляр \*\*\*** установлено в значение false.  
  
### Обновление до более новой версии SQL Server Express  
  
1.  В контекстном меню для подключения к базе данных выберите **Изменение подключения**.  
  
2.  В диалоговом окне **Изменение подключения**, нажмите кнопку **Дополнительно**.  
  
3.  В диалоговом окне **Дополнительные свойства**, нажмите кнопку **ОК**, не изменяя имя сервера.  
  
 Файл базы данных обновляется, чтобы соответствовать текущей версии [!INCLUDE[sql_Denali_exp](../data-tools/includes/sql_denali_exp_md.md)].  
  
### Работать с базой данных в [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], но сохранить совместимость с [!INCLUDE[ssKatmai_exp](../data-tools/includes/sskatmai_exp_md.md)]  
  
1.  В [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], откройте проект, не обновляя ее.  
  
    -   Чтобы запустить проект, выберите ключ F5.  
  
    -   Чтобы изменить базу данных, откройте файл mdf в **Обозреватель решений** и разверните узел в **Обозреватель серверов** для работы с базой данных так же, как и в [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)].  
  
### Сделать SQL Server Express обработчик базы данных по умолчанию  
  
1.  В строке меню выберите **Сервис**, **Параметры**.  
  
2.  В диалоговом окне **Параметры** " разверните узел параметры **\*\*\* средства данных \*\*\***, а затем выберите узел **\*\*\* подключения к данным \*\*\***.  
  
3.  В текстовом поле **\*\*\* имя экземпляра SQL Server \*\*\*** укажите имя экземпляра SQL Server Express, который необходимо использовать.  Если экземпляр не имеет имя, укажите `. \ SQLEXPRESS`.  
  
4.  Нажмите кнопку **ОК**.  
  
 SQL Server Express является обработчиком базы данных по умолчанию для приложений.  
  
## См. также  
 [Общие сведения о локальных данных](../data-tools/local-data-overview.md)   
 [Пошаговое руководство. Подключение к данным в локальном файле базе данных \(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20a%20Local%20Database%20File%20\(Windows%20Forms\).md)