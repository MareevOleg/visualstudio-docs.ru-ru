---
title: "Разбор примера: развертывание вручную приложения ClickOnce | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "развертывание ClickOnce, вручную"
  - "развертывание ClickOnce, SDK - средства"
  - "развертывание приложений [ClickOnce], развертывание ClickOnce вручную"
  - "Mage.exe, развертывание ClickOnce вручную"
  - "MageUI.exe, развертывание ClickOnce вручную"
  - "манифесты [ClickOnce]"
  - "развертывание ClickOnce вручную"
ms.assetid: ccee6551-a1b9-4ca2-8845-9c1cf4ac2560
caps.latest.revision: 49
caps.handback.revision: 47
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Разбор примера: развертывание вручную приложения ClickOnce
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Если Visual Studio невозможно использовать для развертывания приложения [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] или если необходимо использовать дополнительные функции развертывания \(например, развертывание доверенных приложений\), то для создания манифестов [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] следует использовать средство командной строки Mage.exe.  В этом пошаговом руководстве демонстрируется создание развертывания [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] с помощью средства создания и изменения манифеста: версии командной строки \(Mage.exe\) или графической версии \(MageUI.exe\).  
  
## Обязательные компоненты  
 Перед построением развертывания для данного руководства необходим выбор некоторых компонентов и параметров.  
  
-   Установите средства Mage.exe и MageUI.exe.  
  
     Mage.exe и MageUI.exe входят в состав [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)].  Необходимо установить [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] или версию [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)], которая включена в состав Visual Studio.  Дополнительные сведения см. на странице MSDN [Windows SDK](http://go.microsoft.com/fwlink/?LinkId=158044).  
  
-   Укажите приложение для развертывания.  
  
     Для данного руководства необходимо иметь готовое к развертыванию приложение Windows.  В данном руководстве это приложение будет называться AppToDeploy.  
  
-   Определите способ распределения развертывания.  
  
     Возможны следующие варианты: Интернет, общий ресурс или компакт\-диск.  Дополнительные сведения см. в разделе [Развертывание и безопасность технологии ClickOnce](../deployment/clickonce-security-and-deployment.md).  
  
-   Определите, необходим ли для приложения повышенный уровень доверия.  
  
     Если приложению требуется полное доверие \(например, полный доступ к системе пользователя\), используйте параметр `-TrustLevel` с помощью Mage.exe.  Если для приложения требуется определить настраиваемый набор разрешений, можно скопировать раздел разрешений Интернета или интрасети из другого манифеста, изменить их согласно конкретным требованиям и добавить этот раздел в манифест приложения, используя текстовый редактор или MageUI.exe.  Дополнительные сведения см. в разделе [Общие сведения о развертывании доверенных приложений](../deployment/trusted-application-deployment-overview.md).  
  
-   Получите сертификат Authenticode.  
  
     Необходимо подписать развертывание с помощью сертификата Authenticode.  Тестовый сертификат можно создать с помощью средств Visual Studio, MageUI.exe, MakeCert.exe и Pvk2Pfx.exe. Кроме того, сертификат также можно получить в центре сертификации.  Если для использования выбрана технология развертывания доверенных приложений, необходимо также выполнить одноразовую установку сертификата на все клиентские компьютеры.  Дополнительные сведения см. в разделе [Общие сведения о развертывании доверенных приложений](../deployment/trusted-application-deployment-overview.md).  
  
-   Убедитесь в том, что приложение не имеет манифеста со сведениями контроля учетных записей.  
  
     Следует определить, содержит ли приложение манифест со сведениями контроля учетных записей \(например, с элементом `<dependentAssembly>`\).  Чтобы просмотреть манифест приложения, используйте средство Windows Sysinternals [Sigcheck](http://go.microsoft.com/fwlink/?LinkId=158035).  
  
     Если приложение содержит манифест с подробной информацией о контроле учетных записей, следует повторно создать его без информации контроля учетных записей.  Для проекта C\# в Visual Studio откройте свойства проекта и перейдите на вкладку "Приложение".  В раскрывающемся списке **Манифест** выберите пункт **Создать приложение без манифеста**.  Для проекта Visual Basic в Visual Studio откройте свойства проекта, перейдите на вкладку "Приложение" и щелкните элемент **Просмотреть параметры контроля учетных записей**.  Удалите все элементы с одним элементом `<asmv1:assembly>` в открытом файле манифеста.  
  
-   Определите, требует ли приложение наличия определенных компонентов на клиентском компьютере.  
  
     Приложения [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], развертываемые из Visual Studio, могут содержать загрузчик установки необходимых компонентов \(setup.exe\) наряду с развертыванием.  В этом руководстве создаются два манифеста, необходимые для развертывания [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)].  Для создания загрузчика необходимых компонентов воспользуйтесь [Задача GenerateBootstrapper](../msbuild/generatebootstrapper-task.md).  
  
### Чтобы развернуть приложение с помощью средства командной строки Mage.exe  
  
1.  Создайте каталог, в котором будут храниться файлы развертывания [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)].  
  
2.  Создайте вложенный каталог версий в созданном каталоге развертывания.  Если приложение развертывается в первый раз, назовите этот вложенный каталог 1.0.0.0.  
  
    > [!NOTE]
    >  Версия развертывания может отличаться от версии файлов приложения.  
  
3.  Скопируйте все файлы приложения в каталог версии, в том числе исполняемые файлы, сборки, ресурсы и файлы данных.  При необходимости можно создать дополнительные вложенные каталоги, содержащие другие файлы.  
  
4.  Откройте [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] или командную строку Visual Studio и перейдите во вложенный каталог версии.  
  
5.  Создайте манифест приложения посредством вызова Mage.exe.  Следующий оператор создает манифест приложения для кода, который скомпилирован для выполнения на процессоре Intel x86.  
  
    ```  
    mage -New Application -Processor x86 -ToFile AppToDeploy.exe.manifest -name "My App" -Version 1.0.0.0 -FromDirectory .   
    ```  
  
    > [!NOTE]
    >  Не забудьте поставить точку \(.\) после параметра `-FromDirectory`. Точка указывает на текущий каталог.  Если точка не поставлена, необходимо указать путь к файлам приложения.  
  
6.  Подпишите манифест приложения сертификатом Authenticode.  Замените *mycert.pfx* на путь к файлу сертификата.  Замените *passwd* паролем для файла сертификата.  
  
    ```  
    mage -Sign AppToDeploy.exe.manifest -CertFile mycert.pfx -Password passwd  
    ```  
  
7.  Перейдите в корневой каталог развертывания.  
  
8.  Создайте манифест развертывания, вызвав программное средство Mage.exe.  По умолчанию программное средство Mage.exe пометит развертывание [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] как установленное приложение, чтобы оно могло выполняться как в интерактивном, так и в автономном режиме.  Чтобы сделать приложение доступным только в том случае, если пользователь находится в интерактивном режиме, используйте параметр `-Install` со значением `false`.  Если используется значение по умолчанию, а пользователи устанавливают приложение с веб\-сайта или общего ресурса, убедитесь в том, что значение параметра `-ProviderUrl` указывает на расположение манифеста приложения на веб\-сервере или общем ресурсе.  
  
    ```  
    mage -New Deployment -Processor x86 -Install true -Publisher "My Co." -ProviderUrl "\\myServer\myShare\AppToDeploy.application" -AppManifest 1.0.0.0\AppToDeploy.exe.manifest -ToFile AppToDeploy.application  
    ```  
  
9. Подпишите манифест развертывания сертификатом Authenticode.  
  
    ```  
    mage -Sign AppToDeploy.application -CertFile mycert.pfx -Password passwd  
    ```  
  
10. Скопируйте все файлы из каталога развертывания в целевое расположение или на носитель развертывания.  Это может быть папка на веб\-сайте или FTP\-сайте, общий файловый ресурс или компакт\-диск.  
  
11. Предоставьте пользователям URL\-адрес, UNC\-имя или физический носитель, необходимые для установки приложения.  Если указывается URL\-адрес или UNC\-имя, необходимо предоставить пользователям полный путь к манифесту развертывания.  Например, если AppToDeploy развертывается на веб\-узле http:\/\/webserver01\/ в каталог AppToDeploy, то полный URL\-путь будет равняться http:\/\/webserver01\/AppToDeploy\/AppToDeploy.application.  
  
### Развертывание приложения с помощью графического средства MageUI.exe  
  
1.  Создайте каталог, в котором будут храниться файлы развертывания [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)].  
  
2.  Создайте вложенный каталог версий в созданном каталоге развертывания.  Если приложение развертывается в первый раз, назовите этот вложенный каталог 1.0.0.0.  
  
    > [!NOTE]
    >  Версия развертывания может отличаться от версии приложения.  
  
3.  Скопируйте все файлы приложения в каталог версии, в том числе исполняемые файлы, сборки, ресурсы и файлы данных.  При необходимости можно создать дополнительные вложенные каталоги, содержащие другие файлы.  
  
4.  Запустите графическое средство MageUI.exe.  
  
    ```  
    MageUI.exe  
    ```  
  
5.  Создайте новый манифест приложения, последовательно выбрав в меню **Файл** команды **Создать** и **Манифест приложения**.  
  
6.  На вкладке по умолчанию **Имя** введите имя и номер версии для данного развертывания.  Кроме того, укажите **Процессор**, для которого разработано приложение \(например, x86\).  
  
7.  Перейдите на вкладку **Файлы** и нажмите кнопку с многоточием \(**...**\) рядом с текстовым полем **Каталог приложения**.  Откроется диалоговое окно "Обзор папок".  
  
8.  Выберите вложенный каталог версии, содержащий файлы приложения, а затем нажмите кнопку **ОК**.  
  
9. При развертывании из служб IIS установите флажок **При наполнении добавлять расширение DEPLOY ко всем файлам, не имеющим его**.  
  
10. Нажмите кнопку **Заполнить**, чтобы добавить все файлы приложения в список файлов.  Если приложение содержит более одного исполняемого файла, пометьте главный исполняемый файл для этого приложения как приложение, активизируемое при запуске, выбрав пункт **Точка входа** в раскрывающемся списке **Тип файла**.  \(Если приложение содержит только один исполняемый файл, средство MageUI.exe пометит его автоматически\).  
  
11. Перейдите на вкладку **Требуемые разрешения** и выберите уровень доверия, который должно доказать приложение.  Значение по умолчанию — **Полное доверие**, которое подойдет для большинства приложений.  
  
12. В меню **Файл** выберите команду **Сохранить как**.  Отобразится диалоговое окно "Параметры подписи", в котором необходимо подписать манифест приложения.  
  
13. При наличии сертификата, хранящегося в виде файла в файловой системе, выберите вариант **Подписывать с файлом сертификата** и выберите сертификат в файловой системе, нажав кнопку с многоточием \(**...**\).  Затем введите пароль сертификата.  
  
     \-или\-  
  
     Если сертификат содержится в хранилище сертификатов, доступном с компьютера, установите параметр **Подписывать с сохраненным сертификатом** и выберите сертификат из предоставленного списка.  
  
14. Нажмите кнопку **ОК**, чтобы подписать манифест приложения.  Откроется диалоговое окно "Сохранить как".  
  
15. Укажите каталог версии в диалоговом окне "Сохранение файла", а затем нажмите кнопку **Сохранить**.  
  
16. Последовательно выберите в меню **Файл** команды **Создать** и **Манифест развертывания**, чтобы создать манифест развертывания.  
  
17. На вкладке **Имя** укажите имя и номер версии для этого развертывания \(в данном примере —1.0.0.0\).  Кроме того, укажите **Процессор**, для которого разработано приложение \(например, x86\).  
  
18. Перейдите на вкладку **Описание** и укажите значения для параметров **Издатель** и **Продукт**.  \(**Продукт** — это имя, присвоенное приложению в меню "Пуск" Windows при установке приложения на клиентский компьютер для использования в автономном режиме\).  
  
19. Перейдите на вкладку **Параметры развертывания** и укажите расположение манифеста приложения на веб\-сервере или общем ресурсе в поле **Местоположение запуска**.  Например, \\\\myServer\\myShare\\AppToDeploy.application.  
  
20. Если на предыдущем этапе было добавлено расширение DEPLOY, следует также выбрать параметр **Использовать расширение имени файла .deploy**.  
  
21. Перейдите на вкладку **Параметры обновления** и укажите требуемую периодичность обновления приложения.  Если приложение использует <xref:System.Deployment.Application.UpdateCheckInfo> для самостоятельной проверки обновлений, снимите флажок **Это приложение должно проверять наличие обновлений**.  
  
22. Перейдите на вкладку **Ссылка приложения** и нажмите кнопку **Выбрать манифест**.  Отобразится диалоговое окно открытия.  
  
23. Выберите созданный манифест приложения и нажмите кнопку **Открыть**.  
  
24. В меню **Файл** выберите команду **Сохранить как**.  Отобразится диалоговое окно "Параметры подписи", в котором необходимо подписать манифест развертывания.  
  
25. При наличии сертификата, хранящегося в виде файла в файловой системе, выберите вариант **Подписывать с файлом сертификата** и выберите сертификат в файловой системе, нажав кнопку с многоточием \(**...**\).  Затем введите пароль сертификата.  
  
     \-или\-  
  
     Если сертификат содержится в хранилище сертификатов, доступном с компьютера, установите параметр **Подписывать с сохраненным сертификатом** и выберите сертификат из предоставленного списка.  
  
26. Нажмите кнопку **ОК**, чтобы подписать манифест развертывания.  Откроется диалоговое окно "Сохранить как".  
  
27. В диалоговом окне **Сохранение файла** перейдите на один уровень выше в корневой каталог развертывания и нажмите кнопку **Сохранить**.  
  
28. Скопируйте все файлы из каталога развертывания в целевое расположение или на носитель развертывания.  Это может быть папка на веб\-сайте или FTP\-сайте, общий файловый ресурс или компакт\-диск.  
  
29. Предоставьте пользователям URL\-адрес, UNC\-имя или физический носитель, необходимые для установки приложения.  Если указывается URL\-адрес или UNC\-имя, необходимо предоставить пользователям полный путь к манифесту развертывания.  Например, если AppToDeploy развертывается на веб\-узле http:\/\/webserver01\/ в каталог AppToDeploy, то полный URL\-путь будет равняться http:\/\/webserver01\/AppToDeploy\/AppToDeploy.application.  
  
## Следующие действия  
 При необходимости развертывания новой версии приложения необходимо создать новый каталог, называемый по новой версии \(например, 1.0.0.1\), и переместить файлы нового приложения в папку \\bin в этом новом каталоге.  Затем необходимо выполнить описанные выше действия для создания и подписания нового манифеста приложения, а также обновить и подписать манифест развертывания.  Убедитесь в том, что новая версия указана в вызовах Mage.exe `-New` и `–Update`, так как [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] обновляет только новые версии \(при этом наибольшее значение имеет крайнее левое целое число\).  Пользователи MageUI.exe могут обновить манифест развертывания, открыв его, выбрав вкладку **Ссылка приложения**, нажав кнопку **Выбрать манифест** и выбрав обновленный манифест приложения.  
  
## См. также  
 [Mage.exe \(средство создания и редактирования манифеста\)](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md)   
 [MageUI.exe \(Manifest Generation and Editing Tool, Graphical Client\)](../Topic/MageUI.exe%20\(Manifest%20Generation%20and%20Editing%20Tool,%20Graphical%20Client\).md)   
 [Публикация ClickOnce\-приложений](../deployment/publishing-clickonce-applications.md)   
 [Манифест развертывания ClickOnce](../deployment/clickonce-deployment-manifest.md)   
 [Манифест приложения ClickOnce](../deployment/clickonce-application-manifest.md)