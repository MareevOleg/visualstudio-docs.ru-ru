---
title: Удаленный отладчик загрузки
description: Ссылки на скачивание для удаленного отладчика
services: ''
author: mikejo5000
ms.service: ''
ms.topic: include
ms.date: 05/23/2018
ms.author: mikejo
ms.custom: include file
ms.openlocfilehash: 6c429614a094ceefc4f9a1e358ebc8ee26c40773
ms.sourcegitcommit: 1df0ae74af03bcf0244129a29fd6bd605efc9f61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2018
ms.locfileid: "50915248"
---
На удаленном устройстве или сервер, который требуется отладить на, а не компьютера с Visual Studio Загрузите и установите правильную версию инструментов удаленной отладки по ссылкам в следующей таблице.

- Скачайте последние инструменты удаленной отладки для вашей версии Visual Studio. Последнюю версию инструментов удаленной отладки совместим с более ранними версиями Visual Studio, но более ранние версии инструментов удаленной отладки не совместимы с более поздними версиями Visual Studio. 
- Загрузите инструменты удаленной отладки с ту же архитектуру, что и их установке на. Например если необходимо выполнить отладку 32-разрядное приложение на удаленном компьютере под управлением 64-разрядной операционной системы, установите средства удаленного 64-разрядной. 

|Версия|Ссылка|Примечания|
|-|-|-|
|Visual Studio 2017 (последняя версия)|[Инструменты удаленной отладки](https://visualstudio.microsoft.com/downloads/?q=remote+tools#remote-tools-for-visual-studio-2017)|Совместимость со всеми версиями Visual Studio 2017. Скачайте версию, которая соответствует операционной системе устройства (x 86, x64 или ARM64). В Windows Server, см. в разделе [разблокировать на загрузку файла](../../debugger/remote-debugging-unblock-file-download.md) загрузить инструменты удаленной отладки.|
|Visual Studio 2015|[Инструменты удаленной отладки](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202015)|Инструменты удаленной отладки для Visual Studio 2015 доступны из My.VisualStudio.com. При появлении присоединиться к бесплатным [Visual Studio Dev Essentials](https://visualstudio.microsoft.com/dev-essentials/) программы или войдите с помощью идентификатор вашей подписки Visual Studio. В Windows Server, см. в разделе [разблокировать на загрузку файла](../../debugger/remote-debugging-unblock-file-download.md) загрузить инструменты удаленной отладки.|
|Visual Studio 2013|[Инструменты удаленной отладки](/previous-versions/visualstudio/visual-studio-2013/bt727f1t(v=vs.120)#Installing_the_Remote_Tools)|Загрузить страницу в документации по Visual Studio 2013|
|Visual Studio 2012|[Инструменты удаленной отладки](/previous-versions/visualstudio/visual-studio-2012/bt727f1t(v=vs.110)#BKMK_Installing_the_Remote_Tools)|Загрузить страницу в документации по Visual Studio 2012|

Можно запускать удаленный отладчик, скопировав *msvsmon.exe* для удаленного компьютера, а не выполнять установку инструментов удаленной отладки. Тем не менее мастер настройки удаленного отладчика (*rdbgwiz.exe*) доступен только при установке инструментов удаленной отладки. Необходимо использовать мастер для конфигурации, если вы хотите запустить удаленный отладчик как службу. Дополнительные сведения см. в разделе [(необязательно) Настройка удаленного отладчика как службы](../../debugger/remote-debugging.md#bkmk_configureService).

>[!NOTE]
>- Чтобы выполнить отладку приложений Windows 10 на устройствах ARM, используйте ARM64, которая доступна в последнюю версию инструментов удаленной отладки.  
>- Для отладки приложений Windows 10 в Windows RT используйте ARM, который доступен только в Visual Studio 2015, скачайте инструменты удаленной отладки.

