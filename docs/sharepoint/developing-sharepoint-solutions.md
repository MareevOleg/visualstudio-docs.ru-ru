---
title: "Разработка решений SharePoint"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.SharePointTools.Project.ProjectProperties"
  - "VS.SharePointTools.Project.ProjectItemProperties"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Разработка приложений SharePoint в Visual Studio, Обзор"
ms.assetid: 059bce0f-c301-4234-a0b4-9c14b7cdfa3e
caps.latest.revision: 36
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 34
---
# Разработка решений SharePoint
  В [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] имеется несколько шаблонов типов проектов SharePoint для создания сайтов SharePoint и элементов сайтов. Список доступных типов проектов см. в разделе [проектов и шаблонов элементов проектов SharePoint](../sharepoint/sharepoint-project-and-project-item-templates.md). Далее следует описание элементов и свойств проекта SharePoint.

 Сведения о SharePoint 2013 и SharePoint добавьте\-модули, в разделе [SharePoint 2013](http://msdn.microsoft.com/library/jj162979.aspx) и [Добавьте сборки SharePoint\-модули](http://msdn.microsoft.com/library/office/apps/jj163230%28v=office.15%29.aspx).

## <a name="elements-of-a-sharepoint-project"></a>Элементы проекта SharePoint
 Узлы в проекте SharePoint называются *элементами SharePoint*. Элементы SharePoint также могут содержать один или несколько вложенных файлов, называемых *файлами элементов SharePoint*, например файлы конфигурации [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] , формы ASPX и другие.

 Вместо создания проекта с помощью шаблона с уже имеющимися файлами элементов проекта можно воспользоваться шаблоном **Пустой проект** , чтобы создать новый проект SharePoint и затем добавить элементы проекта вручную. Проекты SharePoint также может содержаться один или несколько файлов компонентов \(для активации в SharePoint\) и файл пакета для распространения проекта.

### <a name="special-nodes"></a>Особые узлы
 Каждый проект SharePoint содержит два узла, которые нельзя переименовывать, удалять, вырезать, копировать и перетаскивать из проекта. Это узлы:

-   Компоненты

-   Пакет

 Оба эти узла всегда присутствуют в проекте SharePoint, даже если никакие другие компоненты и пакеты не определены в проекте.

#### <a name="features-node"></a>Узел «Функции»
 Узел **Функции** содержит одну или несколько функций проекта SharePoint. Функция — это контейнер расширений для SharePoint. После развертывания функции на сервере SharePoint она может быть включена в список определений сайтов или активирована индивидуально администраторами SharePoint на сайтах SharePoint. Дополнительные сведения см. в разделе [Работа с компонентами](http://go.microsoft.com/fwlink/?LinkID=147704).

 При добавлении элемента, например типа содержимого или экземпляра списка, в проект SharePoint он добавляется в функцию в узле **Функции** . Область элемента определяет, куда добавляется элемент: в новую или существующую функцию. Если область нового элемента совпадает с областью существующей функции, он добавляется в эту функцию. В противном случае элемент добавляется в новую функцию.

 Чтобы добавить функцию вручную, выберите команду **Добавить функцию** из контекстного меню узла функции. Вы можете просмотреть или изменить содержимое функции с помощью конструктора функций. Дополнительные сведения см. в разделе [Практическое руководство: Настройка компонента SharePoint](../sharepoint/how-to-customize-a-sharepoint-feature.md).

 Когда функция добавляется в проект SharePoint, она появляется в **обозревателе решений** в виде узла с заданным по умолчанию именем Feature*x*.feature, где *x* — уникальный номер. После развертывания функции на сервере SharePoint администратор SharePoint может активировать ее, тем самым сделав ее доступной для пользователей сайта SharePoint.

#### <a name="package-node"></a>Узел «Пакет»
 Узел **Пакет** содержит один файл, который реализует механизм распространения проекта SharePoint. Этот файл называется *решение**пакет*, является. CAB-ФАЙЛ\-с. Расширение WSP. Пакет решения является файлом развертывания и повторного использования, который содержит набор функций, определений сайтов и сборок, применимых к сайтам SharePoint, которые можно включать и отключать индивидуально. Узел **Пакет** также всегда содержит файл с именем Package.wspdef — файл определения [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] для пакета. После развертывания пакета на сервере, где выполняется SharePoint, администратор SharePoint может установить его и активировать его функции.

 Можно просмотреть или изменить содержимое пакета в конструкторе пакетов, двойной\-щелкнув узел пакета или открыв его контекстное меню и выбрав **Открыть**. Дополнительные сведения см. в разделе [создания пакетов решений SharePoint](../sharepoint/creating-sharepoint-solution-packages.md).

## <a name="sharepoint-project-and-project-item-properties"></a>Свойства проектов и элементов проектов SharePoint
 Свойства проектов SharePoint, так же как и свойства других проектов [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] , отображаются в окне «Свойства» и на странице свойств. Отображаемые свойства зависят от того, какой узел выбран.

 При выборе проекта SharePoint, элемента проекта или узла файла элемента проекта в **обозревателе решений**в окне «Свойства» или на странице свойств отображаются следующие свойства:

### <a name="project-properties"></a>Свойства проекта

|Имя свойства|Описание|
|-------------------|-----------------|
|Активная конфигурация развертывания|Указывает ряд шагов, выполненных в процессе развертывания. Для получения дополнительной информации см. [How to: Edit a SharePoint Deployment Configuration](../sharepoint/how-to-edit-a-sharepoint-deployment-configuration.md).|
|Место развертывания сборки|Определяет, где находятся *сборки приложения SharePoint* . Допустимые расположения сборок: либо *GlobalAssemblyCache* \(по умолчанию\), или *WebApplication*.<br /><br /> Если свойству *Sandboxed Solution* присвоено значение **true**, это свойство отключается.|
|Автоматическое\-отозвать после отладки|Указывает, должно ли развернутое решение автоматически отзываться из SharePoint после выполнения приложения в режиме отладки в [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Если параметр выбран, решение отзывается, когда интегрированная среда разработки возвращается в режим конструктора после отладки. Если параметр не выбран, решение не отзывается. Дополнительные сведения см. в разделе [Отзыв решения](http://go.microsoft.com/fwlink/?LinkId=183819).|
|Изменить конфигурации|Задает конфигурацию развертывания для проекта. Дополнительные сведения см. в разделе [Практическое руководство: изменение конфигурации развертывания SharePoint](../sharepoint/how-to-edit-a-sharepoint-deployment-configuration.md) и [развертывание, публикация и обновление пакетов решений SharePoint](../sharepoint/deploying-publishing-and-upgrading-sharepoint-solution-packages.md).|
|Включить отладку Silverlight \(вместо отладки скриптов\)|Если выбран этот параметр, к процессу отладки присоединяется отладчик Silverlight. Если параметр не выбран, к процессу отладки присоединяется отладчик скриптов. Дополнительные сведения см. в разделе [Общие сведения об отладке Silverlight](http://go.microsoft.com/fwlink/?LinkId=179826).|
|Включить сборку в пакет|Указывает, должна ли сборка проекта включаться в пакет во время построения.|
|POST\-развертывания командной строки|Задает команды, выполняемые после развертывания решения SharePoint. Эта строка поддерживает любые пакетные команды, а также разрешение переменных MSBuild. Для получения дополнительной информации см. [How to: Set SharePoint Deployment Commands](../sharepoint/how-to-set-sharepoint-deployment-commands.md).|
|Pre\-развертывания командной строки|Задает команды, выполняемые до развертывания решения SharePoint. Эта строка поддерживает любые пакетные команды, а также разрешение переменных MSBuild. Для получения дополнительной информации см. [How to: Set SharePoint Deployment Commands](../sharepoint/how-to-set-sharepoint-deployment-commands.md).|
|Файл проекта|Имя файла, содержащего сведения о сборке и конфигурации, а также другую информацию о проекте.|
|Папка проекта|Расположение файла проекта в системе. \(Чтение\-только.\)|
|Sandboxed Solution|Указывает, следует ли развертывать проект как *изолированное решение*, также известный как *пользователь\-создается решение*. Изолированные решения не всегда являются доверенными. Значение **true** означает, что проект развертывается как изолированное решение, значение **false** означает, что проект развертывается как решение фермы. Дополнительные сведения см. в разделах [Sandboxed Solution Considerations](../sharepoint/sandboxed-solution-considerations.md) и [Differences Between Sandboxed and Farm Solutions](../sharepoint/differences-between-sandboxed-and-farm-solutions.md).|
|URL-адрес сайта|Указывает [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] конечного сайта для этого проекта.|
|Автозапускаемый элемент|Указывает первый элемент в проекте, который должен быть запущен.|

 При выборе файла элемента SharePoint \(как рабочий процесс или компонент в узле компоненты\), в окне «Свойства» отображаются следующие свойства:

### <a name="project-item-properties"></a>Свойства элемента проекта

|Имя свойства|Описание|
|-------------------|-----------------|
|Устранение конфликта развертывания|Указывает действие к исполнению при развертывании элемента проекта, свойства которого идентичны свойствам элемента, уже существующего на сервере. Для получения дополнительной информации см. [Troubleshooting SharePoint Packaging and Deployment](../sharepoint/troubleshooting-sharepoint-packaging-and-deployment.md).|
|Свойства компонента|Задает набор значений \(хранится как ключ\/значение пары\) поставляемый с компонентом при его развертывании в SharePoint. После развертывания функции значения свойств можно использовать в коде. Дополнительные сведения см. в разделе [Providing Packaging and Deployment Information in Project Items](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).|
|Приемник компонента|Предоставляет код, который выполняется при возникновении определенных событий для элемента проекта, содержащего функцию. Дополнительные сведения см. в разделе [Providing Packaging and Deployment Information in Project Items](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).|
|Имя папки|Имя папки элемента проекта SharePoint.|
|Выходные ссылки проекта|Задает зависимость, например сборку, которую должен запустить элемент проекта. Дополнительные сведения см. в разделе [Providing Packaging and Deployment Information in Project Items](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).|
|Записи безопасных элементов управления|Задает элементы управления, к которым можно безопасно открыть доступ для редактирования пользователям, не являющимся доверенными. Дополнительные сведения см. в разделе [Providing Packaging and Deployment Information in Project Items](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).|

### <a name="project-item-file-properties"></a>Свойства файла элемента проекта

|Имя свойства|Описание|
|-------------------|-----------------|
|Действие при сборке|Определяет, как файл связан с процессами сборки и развертывания. Дополнительные сведения см. в разделе [Свойства файлов](http://msdn.microsoft.com/library/0c6xyb66(v=vs.100).aspx).|
|Копировать в выходной каталог|Указывает, является ли исходный файл\(s\) будут копироваться в выходной каталог. Может принимать одно из следующих значений:<br /><br /> -   *Не копировать*<br />-   *Всегда копировать*<br />-   *Копировать, если новее*<br /><br /> Дополнительные сведения см. в разделе [Свойства файлов](http://msdn.microsoft.com/library/0c6xyb66(v=vs.100).aspx).|
|Пользовательский инструмент|Задает имя инструмента, если таковой имеется, преобразующего файл во время разработки и помещающего результат преобразования в другой файл. Например, набор данных \(.[!INCLUDE[TLA2#tla_xsd](../sharepoint/includes/tla2sharptla-xsd-md.md)]\) файл имеет пользовательский инструмент по умолчанию. Дополнительные сведения см. в разделе [Свойства файлов](http://msdn.microsoft.com/library/0c6xyb66(v=vs.100).aspx).|
|Пространство имен пользовательского инструмента|Пространство имен, в которое копируются выходные данные пользовательского инструмента. Дополнительные сведения см. в разделе [Свойства файлов](http://msdn.microsoft.com/library/0c6xyb66(v=vs.100).aspx).|
|Местоположение развертывания|Полностью\-полный путь файла на сервере SharePoint. Этот путь состоит из корневого каталога развертывания и путь развертывания sub\-Свойства.|
|Путь развертывания|Относительный путь файла в файле SharePoint Server, например Workflow1\\. Полностью\-полный путь к файлу создается путем объединения *путь развертывания* значение в конец *корневого каталога развертывания* значение.<br /><br /> При выборе значения из *RootFile* для *типа развертывания* изменения свойств *корневого каталога развертывания* на {SharePointRoot}\\, в результате чего полностью\-полный путь {SharePointRoot}\\Workflow1\\. Дополнительные сведения см. в разделе [Упаковка и развертывание решений SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md).|
|Deployment Root|Строка. Корневая папка, в которой файл развертывается на сервере SharePoint. Например, {SharePointRoot}\\шаблона\\функции\\{FeatureName}\\.<br /><br /> Значение свойства *Deployment Root* определяется параметром *Deployment Type* .|
|Deployment Type|Тип развертывания файла, определяющий его значение *Deployment Root* . Может принимать одно из следующих значений:<br /><br /> NoDeployment: \<Нет значения\><br /><br /> ElementManifest: {SharePointRoot}\\шаблона\\функции\\{FeatureName}\\<br /><br /> ElementFile: {SharePointRoot}\\шаблона\\функции\\{FeatureName}\\<br /><br /> TemplateFile: {SharePointRoot}\\шаблона\\<br /><br /> RootFile: {SharePointRoot}\\<br /><br /> GlobalResource: {SharePointRoot}\\ресурсы\\<br /><br /> ClassResource: {ClassResourcePath}\\<br /><br /> Дополнительные сведения см. в разделе <xref:Microsoft.VisualStudio.SharePoint.DeploymentType>.|
|Имя файла|Имя файла или папки для файла элемента.|
|Полный путь|Расположение файла для элемента. \(Чтение\-только.\)|

## <a name="related-topics"></a>Связанные разделы

|Заголовок|Описание|
|-----------|-----------------|
|[Проектов и шаблонов элементов проектов SharePoint](../sharepoint/sharepoint-project-and-project-item-templates.md)|Описание шаблонов проектов и элементов проектов SharePoint, доступных в [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].|
|[Практическое руководство: Добавление элементов в проект SharePoint](../sharepoint/how-to-add-items-to-a-sharepoint-project.md)|Описание процедуры добавления новых или существующих элементов в проект SharePoint [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] .|
|[Пошаговое руководство: Создание столбца сайта, тип содержимого и списка для SharePoint](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md)|Интересы пошаговом\-по\-шаг создания настраиваемого поля, типа содержимого, определения списка и экземпляра списка.|
|[Практическое руководство: Создание приемника событий](../sharepoint/how-to-create-an-event-receiver.md)|Описывает, как добавить приемник событий для проекта, созданного в [Пошаговое руководство: Создание столбца сайта, тип содержимого и списка для SharePoint](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md).|
|[Создание решений рабочих процессов SharePoint](../sharepoint/creating-sharepoint-workflow-solutions.md)|Описание процедуры создания проектов рабочих процессов, включающее формы сопоставления и формы запуска рабочих процессов.|
|[Создание страниц для SharePoint](../sharepoint/creating-pages-for-sharepoint.md)|Описание процедуры создания страниц, например страниц приложений, страниц сайтов, эталонных страниц и макетов страниц для SharePoint.|
|[Создание веб-частей для SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md)|Описание процедуры добавления элементов управления, позволяющих пользователям напрямую изменять содержимое, внешний вид и поведение страниц сайта SharePoint с помощью браузера.|
|[Создание многократно используемых элементов управления для веб-частей или страниц приложений](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)|Описание процедуры создания пользовательских элементов управления, которые можно размещать на страницах приложений и в веб-частях, используемых в SharePoint.|
|[Интеграция бизнес-данные в SharePoint](../sharepoint/integrating-business-data-into-sharepoint.md)|Описывает, как интегрировать данные из веб-служб и обратно\-сервера приложений в приложения SharePoint.|
|[Создание определений сайтов SharePoint](../sharepoint/creating-site-definitions-for-sharepoint.md)|Описание процедуры создания определений сайтов — шаблонов, которые используются для создания сайтов SharePoint.|
|[Импорт элементов из существующего сайта SharePoint](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)|Описание процедуры импорта элементов, например типов содержимого и модулей, из существующего сайта SharePoint в проект SharePoint [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] .|
|[Использование модулей для включения файлов в решение](../sharepoint/using-modules-to-include-files-in-the-solution.md)|Описание способа использования модулей для развертывания файлов из проекта [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] на сайт SharePoint.|
|[Просмотр подключений SharePoint с помощью обозревателя серверов](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md)|Описание способа просмотра локальных сайтов SharePoint с помощью обозревателя серверов.|
|[Предоставление упаковке и сведения о развертывании в элементах проекта](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)|Описание способа использования свойств элементов проекта для предоставления сведений об упаковке и развертывании для проектов, например записей безопасных элементов управления, выходных ссылок проекта и свойств функций.|
|[Практическое руководство: Добавление и удаление сопоставленных папок](../sharepoint/how-to-add-and-remove-mapped-folders.md)|Описание процедуры добавления в проект сопоставленных папок для более удобного доступа к ресурсам SharePoint.|
|[Замечания об обезвреженных решениях](../sharepoint/sandboxed-solution-considerations.md)|Описание проблем, связанных с изолированными решениями.|
|[Безопасность решений SharePoint](../sharepoint/security-for-sharepoint-solutions.md)|Рассмотрение вопросов безопасности при разработке решений SharePoint в [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].|
|[Диалоговое окно выбора URL-АДРЕСА &#40; Разработка приложений SharePoint в Visual Studio &#41;](../sharepoint/url-picker-dialog-box-sharepoint-development-in-visual-studio.md)|Описание диалогового окна, которое можно использовать для добавления ссылок в виде путей к ресурсам в проекте или на локальном сервере SharePoint.|

## <a name="see-also"></a>См. также
 [Приступая к работе &#40; Разработка приложений SharePoint в Visual Studio &#41;](../sharepoint/getting-started-sharepoint-development-in-visual-studio.md) 
 [Просмотр подключений SharePoint с помощью обозревателя серверов](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md) 
 [Построение и отладка решений SharePoint](../sharepoint/building-and-debugging-sharepoint-solutions.md) 
 [Упаковка и развертывание решений SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)

  