---
title: "Построение ClickOnce-приложений из командной строки | Документы Microsoft"
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
- ClickOnce deployment, from command line
- publishing
- publishing, ClickOnce
ms.assetid: d9bc6212-c584-4f72-88c9-9a4b998c555e
caps.latest.revision: "23"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 86dba79e6e8b7e3f3b2837e494cfeddd2692d0cf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2017
---
# <a name="building-clickonce-applications-from-the-command-line"></a>Построение ClickOnce-приложений из командной строки
В [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)], можно создавать проекты из командной строки, даже если они созданы в интегрированной среде разработки (IDE). На самом деле можно перестроить проект, созданный с [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] на другом компьютере, имеющем только [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] установлен. Это позволяет воспроизвести сборки с помощью автоматизированного процесса, например, в центре сборки лаборатории или с помощью дополнительных методы написания сценариев вне области построения самого проекта.  
  
## <a name="using-msbuild-to-reproduce-clickonce-application-deployments"></a>Использование MSBuild для воспроизведения развертывания приложения ClickOnce  
 При вызове/target: Publish msbuild, в командной строке, система MSBuild для сборки проекта и создания [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] приложения в папке публикации. Это равносильно выбору **публикации** в Интегрированной среде разработки.  
  
 Эта команда выполняет msbuild.exe, который находится на пути в среде командной строки Visual Studio.  
  
 «target» является индикатор для MSBuild о том, как обработать команду. Ключевыми целевыми объектами являются целевой объект «сборка» и «публикация» целевой объект. Целевой объект построения является эквивалентом выбору построения команды (или нажав клавишу F5), в Интегрированной среде разработки. Если требуется выполнить сборку проекта, можно добиться, введя `msbuild`. Эта команда работает, поскольку целевой объект построения является целевым объектом по умолчанию для всех проектов, созданных [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]. Это означает, что не необходимо явно указать целевой объект построения. Таким образом, введя `msbuild` выполняется та же операция, если ввести `msbuild /target:build`.  
  
 `/target:publish` Команда определяет MSBuild для вызова назначения публикации. Целевой объект публикации зависит от целевой сборки. Это означает, что операция публикации является надмножеством операции построения. Например если вы внесли изменения в один из исходных файлов Visual Basic или C#, соответствующую сборку автоматически выполняется перестройка операцией публикации.  
  
 Сведения о формировании полного [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] развертывания с помощью средства командной строки Mage.exe для создания вашего [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] манифеста см. в разделе [Пошаговое руководство: развертывание вручную приложения ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
## <a name="creating-and-building-a-basic-clickonce-application-using-msbuild"></a>Создание и построение основные ClickOnce-приложения с помощью MSBuild  
  
#### <a name="to-create-and-publish-a-clickonce-project"></a>Для создания и публикации проекта ClickOnce  
  
1.  Нажмите кнопку **новый проект** из **файл** меню. Откроется диалоговое окно **Новый проект** .  
  
2.  Выберите **приложение Windows** и назовите его `CmdLineDemo`.  
  
3.  Из **построения** меню, нажмите кнопку **публикации** команды.  
  
     Это действие гарантирует, что проект настроен для создания [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] развертывания приложения.  
  
     Откроется Мастер публикации.  
  
4.  В мастере публикации нажмите кнопку **Готово**.  
  
     Visual Studio создает и отображает веб-страницу по умолчанию, называется Publish.htm.  
  
5.  Сохраните проект и запишите расположение папки, в которой хранится.  
  
 Описанные выше шаги создания [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] проекта, опубликованный в первый раз. Теперь можно воспроизвести построение вне интегрированной среды разработки.  
  
#### <a name="to-reproduce-the-build-from-the-command-line"></a>Воспроизведение построения из командной строки  
  
1.  Выйдите из [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)].  
  
2.  С Windows **запустить** меню, нажмите кнопку **все программы**, затем **Microsoft Visual Studio**, затем **набора средств Visual Studio**, то **Командной строки visual Studio**. Это следует открывать командную строку в корневом каталоге текущего пользователя.  
  
3.  В **командной строки Visual Studio**, изменения в папку проекта, который вы только что выполнили выше текущего каталога. Например, введите `chdir My Documents\Visual Studio\Projects\CmdLineDemo`.  
  
4.  Чтобы удалить существующие файлы, созданные в «для создания и публикации [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] проект, «тип `rmdir /s publish`.  
  
     Этот шаг необязателен, но это гарантирует, что новые файлы все созданные сборки из командной строки.  
  
5.  Введите `msbuild /target:publish`.  
  
 Указанные выше шаги создадут полное [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] развертывания приложения во вложенной папке проекта с именем P**публиковать**. — CmdLineDemo.application [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] манифест развертывания. Папка CmdLineDemo_1.0.0.0 содержит файлы CmdLineDemo.exe и CmdLineDemo.exe.manifest, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] манифеста приложения. Setup.exe является загрузчиком, который по умолчанию настроен для установки [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Папка DotNetFX содержит распространяемые компоненты для [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Это весь набор файлов, необходимых для развертывания приложения в Интернете или с помощью UNC-путь или компакт-диска или DVD-ДИСКОВ.  
  
## <a name="publishing-properties"></a>Свойства публикации  
 При публикации приложения в описанных выше процедур, следующие свойства будут вставлены в файле проекта с помощью мастера публикации. Эти свойства непосредственно влияют на способ [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] создается приложение.  
  
 В CmdLineDemo.vbproj / CmdLineDemo.csproj:  
  
```  
<AssemblyOriginatorKeyFile>WindowsApplication3.snk</AssemblyOriginatorKeyFile>  
<GenerateManifests>true</GenerateManifests>  
<TargetZone>LocalIntranet</TargetZone>  
<PublisherName>Microsoft</PublisherName>  
<ProductName>CmdLineDemo</ProductName>  
<PublishUrl>http://localhost/CmdLineDemo</PublishUrl>  
<Install>true</Install>  
<ApplicationVersion>1.0.0.*</ApplicationVersion>  
<ApplicationRevision>1</ApplicationRevision>  
<UpdateEnabled>true</UpdateEnabled>  
<UpdateRequired>false</UpdateRequired>  
<UpdateMode>Foreground</UpdateMode>  
<UpdateInterval>7</UpdateInterval>  
<UpdateIntervalUnits>Days</UpdateIntervalUnits>  
<UpdateUrlEnabled>false</UpdateUrlEnabled>  
<IsWebBootstrapper>true</IsWebBootstrapper>  
<BootstrapperEnabled>true</BootstrapperEnabled>  
```  
  
 Можно переопределить любого из этих свойств в командной строке, не изменяя сам файл проекта. Например, следующая команда выполняет построение [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] развертывания приложения без загрузчика:  
  
```  
msbuild /target:publish /property:BootstrapperEnabled=false  
```  
  
 Свойства публикации контролируются в [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] из **публикации**, **безопасности**, и **подписывание** страниц свойств **конструктор проектов** . Далее приводится описание свойств публикации, а также значение, указывающее, как каждый задается на различных страницах свойств конструктора приложений:  
  
-   `AssemblyOriginatorKeyFile`Определяет файл ключа, используемого для подписания вашей [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] манифесты приложений. Этот же ключ также может использоваться для назначения строгого имени сборки. Это свойство задается на **подписывание** страница **конструктора проектов**.  
  
 Следующие свойства устанавливаются на **безопасности** страницы:  
  
-   **Включение параметров безопасности ClickOnce** определяет, является ли [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] манифестов. При создании проекта, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] создания манифеста отключено по умолчанию. Мастер автоматически устанавливает этот флаг при публикации в первый раз.  
  
-   **TargetZone** определяет уровень доверия, передаваемый в вашей [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] манифеста приложения. Возможные значения: «Интернет», «Локальная интрасеть» и «Custom». Интернет и интрасеть вызовет набор разрешений по умолчанию передаются в вашей [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] манифеста приложения. Значение по умолчанию — локальная интрасеть и по существу означает полное доверие. Настройка указывает, что только разрешения, явно указанного в файле app.manifest должны предоставляться в [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] манифеста приложения. Файл app.manifest является файлом частичного манифеста, который содержит только определения сведений о доверии. Он является скрытым, автоматически добавляется в проект при настройке разрешений на **безопасности** страницы.  
  
 Следующие свойства устанавливаются на **публикации** страницы:  
  
-   `PublishUrl`— Это расположение, где приложение будет опубликовано в Интегрированной среде разработки. Он будет вставлен в [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] манифест приложения, если ни одна из `InstallUrl` или `UpdateUrl` указано свойство.  
  
-   `ApplicationVersion`Указывает версию [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] приложения. Это номер версии из четырех цифр. Если последний знак «*», а затем `ApplicationRevision` заменяется значением, вставленным в манифест во время построения.  
  
-   `ApplicationRevision`Указывает редакцию. Это целое число, которое увеличивается каждый раз при публикации в Интегрированной среде разработки. Обратите внимание, что оно не увеличивается автоматически для сборок, выполнить в командной строке.  
  
-   `Install`Определяет, является ли приложение установленным приложением или выполнения из веб-приложения.  
  
-   `InstallUrl`(не показано) является местом, где пользователи будут устанавливать приложение из. Если указано, это значение оно записывается в загрузчик setup.exe, если `IsWebBootstrapper` включено свойство. Он также вставляется в манифест приложения, если `UpdateUrl` не указан.  
  
-   `SupportUrl`(не показано) расположение связана в **Установка и удаление программ** диалоговое окно для установленного приложения.  
  
 Следующие свойства задаются в **обновления приложения** диалоговое окно, открывается из **публикации** страницы.  
  
-   `UpdateEnabled`Указывает, является ли приложение должно проверять наличие обновлений.  
  
-   `UpdateMode`Указывает, выполняются обновления или обновления в фоновом режиме.  
  
-   `UpdateInterval`Указывает, как часто приложение должно проверять наличие обновлений.  
  
-   `UpdateIntervalUnits`Указывает, является ли `UpdateInterval` значение измеряется в часов, дней или недель.  
  
-   `UpdateUrl`(не показано) — расположение, из которой приложение будет получать обновления. Если указано, оно вставляется в манифест приложения.  
  
-   Следующие свойства задаются в **параметры публикации** диалоговое окно, открывается из **публикации** страницы.  
  
-   `PublisherName`Указывает имя издателя, отображаемое в командной строке при установке или выполнении приложения. В случае установленного приложения оно также используется для указания имя папки на **запустить** меню.  
  
-   `ProductName`Задает имя продукта, отображаемое в командной строке при установке или выполнении приложения. В случае установленного приложения оно также используется для указания ярлыка на **запустить** меню.  
  
-   Следующие свойства задаются в **необходимые компоненты** диалоговое окно, открывается из **публикации** страницы.  
  
-   `BootstrapperEnabled`Определяет, следует ли создавать загрузчика setup.exe.  
  
-   `IsWebBootstrapper`Определяет, работает ли загрузчик setup.exe через Интернет или в режиме на диске.  
  
## <a name="installurl-supporturl-publishurl-and-updateurl"></a>InstallURL, SupportUrl, PublishURL и UpdateURL  
 Ниже приведены четыре варианта URL-адрес для развертывания ClickOnce.  
  
|Параметр URL-адреса|Описание|  
|----------------|-----------------|  
|`PublishURL`|Требуется при публикации приложения ClickOnce на веб-сайт.|  
|`InstallURL`|Необязательно. Задайте этот параметр URL-адрес, если сайта установки отличается от `PublishURL`. Например, можно задать `PublishURL` путь FTP и установите `InstallURL` для URL-адрес.|  
|`SupportURL`|Необязательно. Задайте этот параметр URL-адрес, если сайта поддержки отличается от `PublishURL`. Например, можно задать `SupportURL` для веб-сайта поддержки пользователей компании.|  
|`UpdateURL`|Необязательно. Задайте этот параметр URL-адрес, если расположение обновлений отличается от `InstallURL`. Например, можно задать `PublishURL` путь FTP и установите `UpdateURL` для URL-адрес.|  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.Build.Tasks.GenerateBootstrapper>   
 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest>   
 <xref:Microsoft.Build.Tasks.GenerateDeploymentManifest>   
 [Развертывание и безопасность технологии ClickOnce](../deployment/clickonce-security-and-deployment.md)   
 [Разбор примера: развертывание вручную приложения ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)