---
title: Публикация в Azure посредством импорта параметров публикации
description: Создание и импорт профиля публикации для развертывания приложения из Visual Studio в службе приложений Azure
ms.date: 05/07/2018
ms.technology: vs-ide-deployment
ms.topic: tutorial
helpviewer_keywords:
- deployment, publish settings
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 804965df5142ddb18c1857a2540c5c69c08c4f9a
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/07/2018
ms.locfileid: "53058504"
---
# <a name="publish-an-application-to-azure-app-service-by-importing-publish-settings-in-visual-studio"></a>Публикация приложения в Службу приложений Azure посредством импорта параметров публикации в Visual Studio

Вы можете использовать средство **публикации** для импорта параметров публикации, а затем развернуть приложение. В этой статье мы используем параметры публикации для Службы приложений Azure, однако аналогичные действия можно использовать, чтобы импортировать параметры публикации из [IIS](../deployment/tutorial-import-publish-settings-iis.md). В некоторых случаях использование профиля параметров публикации может оказаться быстрее, чем ручная настройка развертывания в службу для каждой установки Visual Studio.

Эти шаги применимы к приложениям ASP.NET, ASP.NET Core и .NET Core в Visual Studio. Вы также можете импортировать параметры публикации для приложений [Python](../python/publishing-python-web-applications-to-azure-from-visual-studio.md). Эти действия соответствуют Visual Studio 2017 версии 15.6.

В этом руководстве рассмотрены следующие задачи:

> [!div class="checklist"]
> * Создание файла параметров публикации из Службы приложений Azure.
> * Импорт файла параметров публикации в Visual Studio.
> * Развертывание приложения в Службе приложений Azure.

Файл параметров публикации (*\*.publishsettings*) отличается от профиля публикации (*\*.pubxml*), созданного в Visual Studio. Файл параметров публикации создается Службой приложений Azure, после чего его можно импортировать в Visual Studio.

> [!NOTE]
> Если вам нужно только скопировать профиль публикации Visual Studio (файл *\*.pubxml*) из одной установки Visual Studio в другую, можно найти профиль публикации *\<имя_профиля\>.pubxml* в папке *\\<имя_проекта\>\Properties\PublishProfiles* для управляемых типов проектов. Для веб-сайтов см. в папке *\App_Data*. Профили публикации являются XML-файлами MSBuild.

## <a name="prerequisites"></a>Предварительные требования

* У вас должна быть установлена среда Visual Studio 2017 и иметься рабочая нагрузка **ASP.NET** и **.NET Framework**. Для приложения .NET Core также требуется рабочая нагрузка **.NET Core**.

    Установите Visual Studio бесплатно со страницы  [скачиваемых материалов Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) , если вы еще не сделали этого.

* Создайте Службу приложений Azure. Подробные инструкции см. в разделе [Развертывание веб-приложения ASP.NET Core в Azure с помощью Visual Studio](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs).

## <a name="create-a-new-aspnet-project-in-visual-studio"></a>Создание проекта ASP.NET в Visual Studio

1. На компьютере, где выполняется Visual Studio, последовательно выберите **Файл** > **Создать проект**.

1. В разделе **Visual C#** или **Visual Basic** выберите **Интернет**, а затем в средней области выберите **Веб-приложение ASP.NET (.NET Framework)** или (только C#) **Веб-приложение ASP.NET Core** и нажмите кнопку **ОК**.

    Если указанные шаблоны проекта отсутствуют, выберите ссылку **Открыть Visual Studio Installer** в левой области диалогового окна **Создать проект**. Запускается Visual Studio Installer. Ознакомьтесь с предварительными требованиями в этой статье, чтобы определить рабочие нагрузки Visual Studio, которые необходимо установить.

1. Выберите **MVC** (.NET Framework) или **Веб-приложение (модель-представление-контроллер)** (для .NET Core), убедитесь, что выбран параметр **Без проверки подлинности**, а затем нажмите кнопку **ОК**.

1. Введите имя, например **MyWebApp**, и нажмите кнопку **ОК**.

    Visual Studio создаст проект.

1. Выберите **Сборка** > **Собрать решение** для сборки проекта.

## <a name="create-the-publish-settings-file-in-azure-app-service"></a>Создание файла параметров публикации в Службе приложений Azure

1. Откройте Службу приложений Azure на портале Azure.

1. Нажмите кнопку **Скачать профиль публикации** и сохраните профиль локально.

    ![Скачать профиль публикации](../deployment/media/tutorial-azure-app-service-get-publish-profile.png)

    Файл с расширением *PUBLISHSETTINGS* был создан в расположении, куда вы его сохранили. В следующем коде показан частичный пример файла (в более удобном для чтения формате).

    ```xml
    <publishData>
      <publishProfile
        profileName="DeployASPDotNetCore - Web Deploy"
        publishMethod="MSDeploy"
        publishUrl="deployaspdotnetcore.scm.azurewebsites.net:443"
        msdeploySite="DeployASPDotNetCore"
        userName="$DeployASPDotNetCore"
        userPWD="abcdefghijklmnopqrstuzwxyz"
        destinationAppUrl="http://deployaspdotnetcore20180508031824.azurewebsites.net"
        SQLServerDBConnectionString=""
        mySQLDBConnectionString=""
        hostingProviderForumLink=""
        controlPanelLink="http://windows.azure.com"
        webSystem="WebSites">
        <databases />
      </publishProfile>
    </publishData>
    ```
    Обычно предыдущий файл PUBLISHSETTINGS содержит два профиля публикации, которые можно использовать в Visual Studio — один для развертывания с помощью веб-развертывания, а другой для развертывания с помощью протокола FTP. Предыдущий код показывает профиль веб-развертывания. Оба профиля будут импортированы позже при импорте профиля.

## <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>Импорт параметров публикации в Visual Studio и развертывание

[!INCLUDE [import publish settings](../deployment/includes/import-publish-settings-vs.md)]

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы создали файл параметров публикации, импортировали его в Visual Studio и развернули приложение ASP.NET в Службе приложений Azure. Рекомендуем вам ознакомиться с общими сведениями о параметрах публикации в Visual Studio.

> [!div class="nextstepaction"]
> [Первое знакомство с развертыванием](../deployment/deploying-applications-services-and-components.md)
