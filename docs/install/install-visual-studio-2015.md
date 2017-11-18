---
title: "Установка Visual Studio | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-install"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
f1_keywords: 
  - "vs.about"
helpviewer_keywords: 
  - "Visual Studio, установка"
  - "установка Visual Studio"
  - "серверные установки [Visual Studio]"
  - "Установка [Visual Studio]"
  - "установка Visual Studio"
ms.assetid: da049020-cfda-40d7-8ff4-7492772b620f
caps.latest.revision: 177
caps.handback.revision: 150
author: "TerryGLee"
ms.author: "tglee"
manager: "ghogen"
---
# Установка Visual Studio
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Эта страница содержит подробные сведения, которые помогут вам в установке Visual Studio 2015 — нашего интегрированного набора инструментов для повышения производительности разработчиков. Также включены ссылки на сведения о [компонентах](https://www.visualstudio.com/en-us/news/vs2015-vs.aspx), [выпусках](http://go.microsoft.com/fwlink/?LinkID=242142), [требованиях к системе](https://www.visualstudio.com/products/visual-studio-2015-compatibility-vs), [скачиваемых материалах](http://go.microsoft.com/fwlink/?LinkId=517106) и многом другом.  
  
> [!TIP]
>  Чтобы просмотреть сведения об установке предыдущих версий Visual Studio, щелкните ссылку "Другие версии" в верхней части этой страницы.  
  
## Полезные ссылки  
 Прежде чем мы углубимся в детали, см. список наиболее часто запрашиваемых ссылок, приведенный ниже.  
  
|Компоненты|  
|----------------|  
|Дополнительные сведения о новых и обновленных возможностях Visual Studio 2015 см. в заметках о выпуске для [Visual Studio 2015 RTM](https://www.visualstudio.com/en-us/news/vs2015-vs.aspx) и для [Visual Studio 2015 с обновлением 1](https://www.visualstudio.com/news/vs2015-update1-vs).|  
|Чтобы узнать, какие компоненты и функции доступны в каждом выпуске Visual Studio 2015, посетите страницу [Сравнение предложений Visual Studio](http://go.microsoft.com/fwlink/?LinkID=242142).|  
|Чтобы просмотреть требования к системе для каждого выпуска Visual Studio 2015, посетите страницу [Совместимость Visual Studio 2015](https://www.visualstudio.com/products/visual-studio-2015-compatibility-vs).|  
|Чтобы установить среду Visual Studio 2015, скачайте ее на странице [файлов для загрузки Visual Studio](http://go.microsoft.com/fwlink/?LinkId=517106) или воспользуйтесь установочным носителем из коробочного продукта.|  
|Инструкции по обнаружению ключа продукта см. в разделе [Практическое руководство. Как найти ключ продукта для Visual Studio](../install/how-to-locate-the-visual-studio-product-key.md).|  
|Чтобы ознакомиться с вариантами лицензирования для отдельных пользователей и корпоративных клиентов, обратитесь к документу [Лицензирование Visual Studio и MSDN](https://www.microsoft.com/download/details.aspx?id=13350).|  
  
##  <a name="custom"></a> Установка по умолчанию и Выборочная установка  
 При установке Visual Studio 2015 можно включать или исключать компоненты в зависимости от того, насколько часто вы предполагаете их использовать. Это означает, что установка по умолчанию, как правило, требует меньше места и происходит быстрее, чем выборочная установка. Кроме того, это означает, что многие компоненты, которые устанавливались в предыдущих версиях по умолчанию, в этой версии считаются настраиваемыми компонентами, которые требуется явно выбирать для установки.  
  
 ![Диалоговое окно установки Visual Studio 2015](~/ide/media/vs2015_setup_screen.png "VS2015\_Setup\_screen")  
  
 Настраиваемые компоненты включают Visual C\+\+, Visual F\#, SQL Server Data Tools, пакеты SDK и средства разработки кроссплатформенных мобильных приложений, а также сторонние пакеты SDK и расширения. Если вы не выбрали эти компоненты во время начальной установки, вы можете установить их позднее.  
  
> [!NOTE]
>  Выборочная установка автоматически включает компоненты установки по умолчанию.  
  
 Ниже приведен полный список настраиваемых компонентов.  
  
-   **Языки программирования**  
  
    -   Компиляторы, библиотеки и средства Visual C\+\+  
  
    -   Visual F\#  
  
    -   Python Tools for Visual Studio  
  
-   **Разработка для Windows и веб\-разработка**  
  
    -   Средства публикации ClickOnce  
  
    -   Microsoft SQL Server Data Tools  
  
    -   Веб\-инструменты Майкрософт для разработчиков  
  
    -   Инструменты PowerShell для Visual Studio  
  
    -   Набор разработки для Silverlight  
  
    -   Средства разработки универсальных приложений Windows  
  
    -   Средства и пакеты SDK Windows 10  
  
    -   Средства Windows 8.1 и Windows Phone 8.0\/8.1  
  
    -   Средства и пакеты SDK Windows 8.1  
  
-   **Разработка кроссплатформенных мобильных приложений**  
  
    -   Xamarin \(C\#\/.NET\)  
  
    -   Apache Cordova \(HTML\/JavaScript\)  
  
    -   Разработка мобильных приложений Visual C\+\+ для iOS и Android  
  
-   **Общие средства и пакеты SDK**  
  
    -   Набор Android Native Development Kit \(R10E, 32\-разрядный\)  
  
    -   Android SDK  
  
    -   Программа установки Android SDK \(уровни API 19 и 21\)  
  
    -   Программа установки Android SDK \(уровень API 22\)  
  
    -   Apache Ant \(1.9.3\)  
  
    -   Java SE Development Kit \(7.0.550.13\)  
  
    -   Joyent Node.js  
  
-   **Общие средства**  
  
    -   Git для Windows  
  
    -   Расширения GitHub для Visual Studio  
  
    -   Средства расширения Visual Studio  
  
##  <a name="installing"></a> Установка Visual Studio  
 Установка [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] должна выполняться от имени учетной записи администратора. Тем не менее для работы с [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] после установки они не нужны.  
  
 Для установки всех компонентов Visual Studio учетной записи локального администратора необходимо предоставить следующие права.  
  
|Отображаемое имя объекта локальной политики|Право пользователя|  
|-------------------------------------------------|------------------------|  
|Резервное копирование файлов и каталогов|SeBackupPrivilege|  
|Отладка программ|SeBackupPrivilege|  
|Управление аудитом и журналом безопасности|SeSecurityPrivilege|  
  
 Более подробную информацию о требованиях к учетной записи локального администратора см. в статье базы знаний [Установка SQL Server завершается ошибкой, если учетная запись для установки не имеет определенных прав пользователя](https://support.microsoft.com/en-us/kb/2000257).  
  
###  <a name="BKMK_Media"></a> Установка с использованием установочного носителя  
  
-   Чтобы установить [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], в корневом каталоге установочного носителя [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] запустите файл установки для нужного выпуска:  
  
    |Выпуск|Файл установки|  
    |------------|--------------------|  
    |Visual Studio Enterprise|vs\_enterprise.exe|  
    |Visual Studio Professional|vs\_professional.exe|  
    |Visual Studio Community|vs\_community.exe|  
  
###  <a name="BKMK_Website"></a> Установка путем загрузки с веб\-сайта продукта  
  
-   Посетите раздел [файлов для загрузки Visual Studio](http://go.microsoft.com/fwlink/?LinkId=517106) на веб\-сайте VisualStudio.com.  
  
###  <a name="BKMK_Offline"></a> Загрузка Visual Studio для установки без подключения к сети  
 В большинстве случаев Visual Studio можно без проблем установить с сайта загрузки. Однако в некоторых случаях может потребоваться загрузить все пакеты обновления до установки, например для их установки на нескольких компьютерах или на компьютере, не подключенном к сети. Ниже приведены инструкции по загрузки всех пакетов обновлений, необходимых для установки без подключения к сети.  
  
1.  После загрузки исполняемого файла обновления с веб\-сайта MSDN в папку в файловой системе, выполните следующую команду из командной строки: `<executable name> /layout`.  
  
     Эта команда загружает все пакеты для установки.  
  
     Используя параметр `/layout`, можно скачать почти все основные пакеты установки, а не только те, которые применимы к компьютеру, на котором выполняется скачивание. Такой подход обеспечивает получение всех файлов, необходимых для запуска обновления на любом компьютере, и может быть полезным, если требуется установить компоненты, которые не были установлены изначально.  
  
2.  После выполнения команды должен появиться запрос расположения загружаемых файлов. Введите расположение и нажмите **Загрузить**.  
  
3.  В случае успешной загрузки пакета пользователь видит экран Visual Studio с надписью **Установка успешно завершена\! Все указанные компоненты успешно получены.**  
  
4.  В указанном расположении файла найдите исполняемый файл и папку пакета. Это все, что необходимо скопировать в общее расположение или на установочный носитель.  
  
    > [!CAUTION]
    >  В настоящее время пакет SDK для Android не поддерживает автономную установку. Если попытаться установить компоненты пакета SDK для Android на компьютере, который не подключен к Интернету, может произойти сбой установки.  
  
5.  Теперь можно запустить установку из расположения файла или с установочного носителя.  
  
###  <a name="BKMK_Virtualized"></a> Установка Visual Studio в виртуальных средах  
 **Проблемы, связанные с видео, при использовании Hyper\-V**  
  
 В случае использования Windows Server 2008 R2 с Hyper\-V и графическим ускорителем, система может работать медленнее, чем обычно.  
  
 Более подробную информацию см. на следующей странице веб\-сайта Майкрософт: [Видео может снизить производительность на компьютерах с Windows Server 2008 и Windows Server 2008 R2 с включенной ролью Hyper\-V и установленным ускорителем адаптера дисплея](http://go.microsoft.com/fwlink/?LinkID=231084).  
  
 **Эмуляция устройств с помощью Hyper\-V**  
  
 При установке Visual Studio 2015 на реальном оборудовании без виртуализации можно выбрать компоненты, обеспечивающие эмуляцию устройств Windows и Android с помощью Hyper\-V. При установке в Hyper\-V эмуляция устройств Windows или Android недоступна. Это связано с тем, что эмуляторы являются виртуальными машинами сами по себе, а размещать одну виртуальную машину внутри другой на данный момент нельзя. Эту проблему можно решить, развернув и отладив приложение на реальном устройстве Windows или Android.  
  
## Использование параметров командной строки  
 При запуске приложения установки можно использовать следующие параметры командной строки \(без учета регистра\).  
  
|Параметр|Описание|  
|--------------|--------------|  
|**\/?**<br /><br /> **\/help**<br /><br /> **\/h**|Отображение параметров командной строки.|  
|**\/AddRemoveFeatures**|Задание функций, которые должны быть добавлены в установленный продукт или удалены из него.|  
|**\/AdminFile** *AdminDeployment.xml*|Установка Visual Studio с использованием файла данных, который был указан для административной установки.|  
|**\/CEIPConsent**|Подтверждение согласия на сбор сведений, повышающих качество программного обеспечения, в соответствии с политикой конфиденциальности продукта.|  
|**\/ChainingPackage** *BundleName*|Задание набора, следующего за этим набором. Также может использоваться для указания группы Программы улучшения качества программного обеспечения.|  
|**\/CreateAdminFile \<filename\>**|Указание расположения для создания файла управления, который можно использовать с помощью параметра \/AdminFile.|  
|**\/CustomInstallPath** *InstallationDirectory*|Установка всех пакетов, поддерживающих изменение целевой платформы, в указанный каталог.|  
|**\/ForceRestart**|Компьютер всегда перезапускается после установки.|  
|**\/full**|Установка всех компонентов продукта.|  
|**\/InstallSelectableItems \<item name 1\>\[;\<item name 2\>\]**|Список элементов в дереве выбора для выбора на экране выбора мастера установки.|  
|**\/l**<br /><br /> **\/Log** *Filename*|Задание расположения файла журнала.|  
|**\/layout** *Directory*|Копирование файлов на установочном носителе в указанный каталог.|  
|**\/NoCacheOnlyMode**|Предотвращает предварительное заполнение кэша пакета.|  
|**\/NoRefresh**|Блокировка проверки новых версий продукта для обязательных или рекомендуемых обновленных версий.|  
|**\/norestart**|Блокировка перезапуска компьютера приложением установки во время или после установки. Соответствующие коды возврата см. в разделе "Коды возврата" [Руководство администратора Visual Studio](../install/visual-studio-administrator-guide.md).|  
|**\/noweb**|Блокировка установки из Интернета.|  
|**\/OverrideFeedUri \<path to feed file\>**|Путь к локальному внешнему каналу, описывающему элементы программного обеспечения.|  
|**\/ProductKey**<br /><br /> *КлючПродукта*|Задание пользовательского ключа продукта, который не содержит тире и имеет длину не более 25 символов.|  
|**\/PromptRestart**|Пользователь получит запрос перед перезагрузкой компьютера.|  
|**\/q**<br /><br /> **\/quiet**<br /><br /> **\/s**<br /><br /> **\/silent**|Отключение пользовательского интерфейса для приложения установки. Если ПО Visual Studio уже установлено и не указаны другие параметры, кроме этого, приложение установки работает в режиме обслуживания.|  
|**\/qb**<br /><br /> **\/passive**|Отображение хода выполнения без запроса ввода данных пользователем.|  
|**\/repair**|Восстановление Visual Studio.|  
|**\/SuppressRefreshPrompt**|Блокировка отображения диалогового окна "Доступно обновление" в мастере установки: таким образом обеспечивается автоматическое принятие мастером установки любых обязательных или рекомендуемых обновленных версий.|  
|**\/u**<br /><br /> **\/Uninstall**|Удаление [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|**\/Uninstall \/Force**<br /><br /> **\/u \/force**|Удаление ПО Visual Studio и всех его компонентов, используемых совместно с другими продуктами. **Warning:**  При использовании этого параметра могут перестать правильно работать другие продукты, установленные на этом компьютере.|  
  
 При запуске программы установки из командной строки может потребоваться запись и обработка кода возврата для более удобной работы с командной строкой.  Более подробную информацию см. в разделе [Руководство администратора Visual Studio](../install/visual-studio-administrator-guide.md).  
  
##  <a name="troubleshooting"></a> Устранение неполадок установки  
 Используйте следующие ресурсы, чтобы получить помощь в разрешении проблем настройки и установки:  
  
-   Форум по [установке и настройке Visual Studio](http://go.microsoft.com/fwlink/?LinkID=151190). Просмотрите вопросы и ответы от других пользователей сообщества Visual Studio. Если вы не нашли нужную информацию, задайте собственные вопросы.  
  
-   Веб\-сайт [службы поддержки Майкрософт для Visual Studio](http://go.microsoft.com/fwlink/?LinkID=251019). Прочтите статьи базы знаний \(KB\) и узнайте, как связаться со службой поддержкой корпорации Майкрософт по вопросам установки Visual Studio.  
  
-   В выпусках Visual Studio 2015 о проблеме можно сообщить с помощью сайта Connect по адресу [https:\/\/connect.microsoft.com\/visualstudio](https://connect.microsoft.com/visualstudio).  
  
     Рекомендуется отправить вместе с вопросом журналы установки. Подготовить журналы для отчета о проблеме можно с помощью средства сбора журналов Microsoft Visual Studio и .NET Framework, как описано в следующей процедуре.  
  
    1.  Скачайте средство диагностики установки со страницы [http:\/\/aka.ms\/vscollect](http://aka.ms/vscollect).  
  
    2.  В командной строке с повышенными привилегиями запустите программу collect.exe.  
  
    3.  После выполнения программы collect.exe найдите файл vslogs.cab в каталоге Temp и включите его в отчет о проблеме.  
  
##  <a name="enterprise"></a> Развертывание в корпоративной сети  
 Информацию о развертывании [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] в сети см. в разделе [Руководство администратора Visual Studio](../install/visual-studio-administrator-guide.md).  
  
##  <a name="afterInstalling"></a> Действия после установки Visual Studio  
 После установки [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] рекомендуется зарегистрировать установленный экземпляр программного продукта.  
  
###  <a name="register"></a> Регистрация Visual Studio  
  
##### Регистрация Visual Studio  
  
1.  В строке меню выберите **Справка**, **О программе**.  
  
     Диалоговое окно **О программе** содержит идентификационный номер продукта \(PID\). Для регистрации продукта необходимо указать PID и данные учетной записи Windows \(например, адрес и пароль электронной почты на Hotmail или Outlook.com\).  
  
2.  В меню **Справка** выберите команду **Зарегистрировать продукт**.  
  
###  <a name="helpContent"></a> Установка содержимого автономной справки  
 После установки [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] можно скачать дополнительное содержимое справки, чтобы сделать его доступным в автономном режиме.  
  
##### Установка и удаление содержимого справки  
  
1.  В строке меню [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] выберите **Справка**, **Добавление и удаление содержимого справки**.  
  
2.  На вкладке **Управление содержимымсредства просмотра справки \(Майкрософт\)** выберите источник установки для содержимого справки.  
  
3.  При поиске определенной коллекции справки введите ключевое слово или имя в текстовое поле **Поиск** и нажмите клавишу ВВОД.  
  
4.  Щелкните ссылку **Добавить** или **Удалить** рядом с именем нужной коллекции справки.  
  
5.  Нажмите кнопку **Обновить**.  
  
 Дополнительные сведения об автономной справке см. в статье [Справка по окну справки \(Майкрософт\) версии 2.2](../ide/microsoft-help-viewer.md)  
  
###  <a name="repair"></a> Восстановление среды разработки Visual Studio  
  
##### Восстановление Visual Studio  
  
1.  На странице **Программы и компонентыпанели управления** выберите выпуск продукта, который необходимо восстановить, и нажмите кнопку **Изменить**.  
  
2.  В мастере установки выберите **Восстановить**, нажмите кнопку **Далее**, а затем следуйте инструкциям.  
  
##### Восстановление Visual Studio в режиме без вывода сообщений или в пассивном режиме \(то есть восстановление из источника\)  
  
1.  На компьютере, на котором установлена среда Visual Studio, откройте командную строку Windows.  
  
2.  Введите следующие параметры:  
  
     *КореньDVD* \\\<файл установки\> \<\/quiet&#124;\/passive\> \[\/norestart\]\/Repair  
  
###  <a name="optionalComponents"></a> Установка отдельных элементов  
  
##### Установка отдельных элементов  
  
1.  На странице **Программы и компонентыпанели управления** выберите выпуск продукта, в который требуется добавить один или более компонентов, и нажмите кнопку **Изменить**.  
  
2.  В мастере установки выберите **Изменить**, а затем выберите компоненты, которые необходимо установить.  
  
3.  Нажмите кнопку **Далее**, а затем следуйте инструкциям.  
  
###  <a name="serviceReleases"></a> Проверка наличия исправлений и обновлений  
 Visual Studio не обновляет расширения автоматически при обновлении с предыдущих версий, так как не все расширения совместимы. Необходимо переустановить расширения из [коллекции Visual Studio](http://go.microsoft.com/fwlink/?LinkId=178891) или с помощью средств издателя программного обеспечения.  
  
##### Автоматическая проверка наличия наборов исправлений  
  
1.  В строке меню выберите **Сервис**, **Параметры**.  
  
2.  В диалоговом окне **Параметры** раскройте элемент **Среда**, а затем выберите **Расширения и обновления**. Убедитесь, что установлен флажок **Автоматически проверять наличие обновлений** и нажмите кнопку **ОК**.  
  
##  <a name="uninstalling"></a> Удаление Visual Studio  
 Для удаления Visual Studio 2015 используйте описанные ниже процедуры.  
  
#### Удаление Visual Studio  
  
1.  На странице **Программы и компонентыпанели управления** выберите выпуск продукта, который требуется удалить, и нажмите кнопку **Изменить**.  
  
2.  В мастере установки выберите **Удалить**, нажмите кнопку **Да**, а затем следуйте инструкциям мастера.  
  
#### Удаление Visual Studio в режиме без вывода сообщений или в пассивном режиме \(то есть удаление из источника\)  
  
1.  На компьютере, на котором установлена среда Visual Studio, откройте командную строку Windows.  
  
2.  Введите следующие параметры:  
  
     *Корень\_DVD* \\\<файл установки\> \<\/quiet&#124;\/passive\> \[\/norestart\]\/uninstall  
  
 Если не удается удалить [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] с помощью служебной программы удаления, можно выполнить удаление вручную, удалив [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] и связанные компоненты. Более подробную информацию см. в статье [Удаление Visual Studio](https://support.microsoft.com/en-us/kb/2771441) в базе знаний Майкрософт или в записи [Удаление компонентов Visual Studio, оставшихся после удаления](http://blogs.msdn.com/b/heaths/archive/2015/07/17/removing-visual-studio-components-left-behind-after-an-uninstall.aspx) блога по серверам и средствам Майкрософт.  
  
##  <a name="relatedTopics"></a> Связанные разделы  
  
|Заголовок|Описание|  
|---------------|--------------|  
|[Параллельная установка версий Visual Studio](../Topic/Installing%20Visual%20Studio%20Versions%20Side-by-Side.md)|Сведения об установке и использовании нескольких версий Visual Studio на одном компьютере.|  
|[Библиотека изображений Visual Studio](../designers/the-visual-studio-image-library.md)|Сведения об установке графики, которая может использоваться в приложениях Visual Studio.|  
|[Руководство администратора Visual Studio](../install/visual-studio-administrator-guide.md)|Сведения о вариантах развертывания Visual Studio.|  
|[Установка нескольких языковых версий Visual Studio](../Topic/Installing%20Multiple%20Language%20Versions%20of%20Visual%20Studio.md)|Сведения об установке различных языковых версий Visual Studio.|  
|[Практическое руководство. Как найти ключ продукта для Visual Studio](../install/how-to-locate-the-visual-studio-product-key.md)|Сведения том, как найти ключ продукта для установки Visual Studio.|  
|[Начало работы](../ide/get-started-developing-with-visual-studio.md)|Ссылки на документы, помогающие эффективно использовать Visual Studio.|  
  
## См. также  
 [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3)