---
title: "Обновление сетевой установки Visual Studio | Документация Майкрософт"
description: "Сведения об обновлении сетевой установки Visual Studio с помощью команды --layout"
ms.date: 08/14/2017
ms.reviewer: tims
ms.suite: 
ms.technology:
- vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 1AF69C0E-0AC9-451B-845D-AE4EDBCEA65C
author: timsneath
ms.author: tims
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: f23906933add1f4706d8786b2950fb3b5d2e6781
ms.openlocfilehash: 55af5ee53ee49d83a301936a84c1aa3697568e3e
ms.contentlocale: ru-ru
ms.lasthandoff: 08/14/2017

---
# <a name="update-a-network-based-installation-of-visual-studio"></a>Обновление сетевой установки Visual Studio

Вы можете обновлять макет сетевой установки Visual Studio до последних обновлений продуктов, что позволяет использовать его не только в качестве точки установки обновлений Visual Studio, но и для поддержки уже развернутых установок на клиентских рабочих станциях.

## <a name="how-to-update-a-network-layout"></a>Обновление сетевого макета
Чтобы обновить общий ресурс сетевой установки и разместить в ней последние обновления, выполните команду --layout для инкрементного скачивания обновленных пакетов. 

Если при первоначальном создании сетевого макета вы выбрали частичный макет, эти параметры сохраняются.  Все будущие команды макета используют прежние параметры, а также любые указанные новые параметры.  (Это новая возможность в версии 15.3)  Если вы используете макет более ранней версии, обязательно используйте те же параметры командной строки, которые вы указали при первоначальном создании макета сетевой установки (другими словами, те же рабочие нагрузки и языковые параметры), чтобы обновить его содержимое.

Если макет размещается на общем файловом ресурсе, следует обновить закрытую копию макета (например, c:\vs2017offline) и только после скачивания всех обновлений скопировать обновленные данные в общую папку (например, \\server\products\VS2017). В противном случае повышается вероятность, что кто-то из пользователей запустит программу установки во время обновления макета и не сможет получить полное содержимое макета, так как его обновление не завершено. 

Рассмотрим процедуру создания и обновления макета.

* Ниже приведен пример создания макета с одной рабочей нагрузкой только для английского языка.

  ```
  vs_enterprise.exe --layout c:\VS2017Layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --lang en-US 
  ```

* Здесь показано, как можно обновить этот же макет до более новой версии. Дополнительные параметры командной строки указывать не нужно. Предыдущие параметры были сохранены и будут использоваться во всех последующих командах макета в этой папке макета.  

  ``` 
  vs_enterprise.exe --layout c:\VS2017Layout  
  ```

* Далее показано добавление дополнительной рабочей нагрузки и языка локализации.  (Эта команда добавляет рабочую нагрузку Azure.)  Теперь в этот макет включены управляемый рабочий стол и Azure.  Для всех этих рабочих нагрузок также будут включены языковые ресурсы для английского и немецкого языков.  И макет обновляется до последней доступной версии. 

  ``` 
  vs_enterprise.exe --layout c:\VS2017Layout --add Microsoft.VisualStudio.Workload.Azure --lang de-DE 
  ``` 

* Наконец, вот как можно добавить дополнительную нагрузку и язык локализации без обновления версии. (Эта команда добавляет рабочую нагрузку ASP.NET и Web.)  Теперь в этот макет включены рабочие нагрузки управляемого рабочего стола, Azure и ASP.NET и Web.  Для всех этих рабочих нагрузок также включены языковые ресурсы для английского, немецкого и французского языков.  Но при выполнении этой команды макет не был обновлен до последней доступной версии.  Он остается в существующей версии. 

  ``` 
  vs_enterprise.exe --layout c:\VS2017Layout --add Microsoft.VisualStudio.Workload.NetWeb --lang fr-FR --keepLayoutVersion 
  ```

## <a name="how-to-deploy-an-update-to-client-machines"></a>Как развернуть обновление на клиентских компьютерах
В зависимости от настроек сетевой среды обновление могут разворачивать администраторы предприятия или пользователи с клиентского компьютера.

* Пользователи могут обновлять экземпляр Visual Studio, установленный из папки установки в автономном режиме.
  * Запустите установщик Visual Studio.
  * Затем нажмите кнопку **Обновить**.

* Администраторы могут обновлять клиентские развертывания Visual Studio без взаимодействия с пользователем, выполняя две отдельные команды.
  * Сначала нужно обновить установщик Visual Studio: <br>```vs_enterprise.exe --quiet --update```
  * Теперь обновите само приложение Visual Studio: <br>```vs_enterprise.exe update --installPath "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise" --quiet --wait --norestart```

> [!NOTE]
> Используйте [команду vswhere.exe](tools-for-managing-visual-studio-instances.md), чтобы узнать путь установки существующего экземпляра Visual Studio на клиентском компьютере.

> [!TIP]
> Дополнительные сведения о настройке уведомлений пользователям об обновлениях есть в статье [Control updates to network-based Visual Studio deployments](controlling-updates-to-visual-studio-deployments.md) (Управление обновлениями для сетевых развертываний Visual Studio).

## <a name="how-to-verify-a-layout"></a>Проверка макета 
Используйте команду `--verify` для выполнения проверки в предоставленном автономном кэше. Она проверяет отсутствующие или недопустимые файлы пакетов. В конце проверки выводится список отсутствующих и недопустимых файлов. 

``` 
vs_enterprise.exe --layout <layoutDir> --verify 
``` 

vs_enterprise.exe можно вызвать внутри layoutDir. 


> [!NOTE] 
> В автономном кэше макета должны находиться некоторые важные файлы метаданных, которые требуются параметру `--verify`. Если эти файлы метаданных отсутствуют, команду "--verify" выполнить невозможно, и программа установки сообщит об ошибке. При возникновении этой ошибки повторно создайте автономный макет в другой папке (или в той же папке автономного кэша). Для этого выполните ту же команду макета, которая использовалась для создания первоначального автономного макета. Например, `Vs_enterprise.exe --layout <layoutDir>`.

Корпорация Майкрософт периодически предоставляет обновления для Visual Studio, поэтому версия нового создаваемого макета может отличаться от версии первоначального макета.  

## <a name="how-to-fix-a-layout"></a>Исправление ошибок макета 
Используйте команду `--fix` для выполнения той же проверки, что и `--verify`, а также попытайтесь устранить выявленные проблемы. Для процесса `--fix` требуется подключение к Интернету, поэтому перед вызовом `--fix` убедитесь, что компьютер подключен к Интернету. 

``` 
vs_enterprise.exe --layout <layoutDir> --fix 
``` 

vs_enterprise.exe можно вызвать внутри layoutDir. 

## <a name="how-to-remove-older-versions-from-a-layout"></a>Удаление предыдущих версий из макета
После применения обновлений макета к автономному кэшу в папке кэша макета может находиться ряд устаревших пакетов, которые больше не требуются в последней установке Visual Studio. Используйте параметр `--clean`, чтобы удалить устаревшие пакеты из папки автономного кэша. 

Для этого вам потребуются пути к файлам к манифестам каталога, содержащим эти устаревшие пакеты. Манифесты каталога можно найти в папке "Archive" в автономном кэше макета. Они сохраняются там при обновлении макета. В папке "Archive" находится одна или несколько папок "GUID", каждая из которых содержит устаревший манифест каталога. Количество папок "GUID" должно совпадать с количеством обновлений, внесенных в автономный кэш. 

Внутри каждой папки "GUID" сохранено несколько файлов. Наибольший интерес представляют два файла — файл "version.txt" и файл "catalog.json". Файл "catalog.json" является устаревшим манифестом каталога, который потребуется для передачи в параметр `--clean`. Другой файл ("version.txt") содержит версию этого устаревшего манифеста каталога. На основе номера версии можно решить, следует ли удалять устаревшие пакеты из этого манифеста каталога. То же самое можно сделать при переходе по другим папкам "GUID". Приняв решение по поводу каталогов, которые необходимо очистить, выполните команду `--clean`, указав пути к файлам в этих каталогах.  

Далее приведены несколько примеров использования параметра --clean.   

``` 
vs_enterprise.exe --layout <layoutDir> --clean <file-path-of-catalog1> <file-path-of-catalog2> … 
``` 

``` 
vs_enterprise.exe --layout <layoutDir> --clean <file-path-of-catalog1> --clean <file-path-of-catalog2> … 
``` 

vs_enterprise.exe можно также вызвать внутри &lt;layoutDir&gt;. Ниже приведен пример:

```  
c:\VS2017Layout\vs_enterprise.exe --layout c:\VS2017Layout --clean c:\VS2017Layout\Archive\1cd70189-fc55-4583-8ad8-a2711e928325\Catalog.json --clean c:\VS2017Layout\Archive\d420889f-6aad-4ba4-99e4-ed7833795a10\Catalog.json 
```  

При выполнении этой команды программа установки анализирует папку автономного кэша, чтобы найти список файлов, которые будут удалены. Затем вы сможете просмотреть файлы, которые будут удалены, и подтвердить удаление. 

## <a name="see-also"></a>См. также
* [Установка Visual Studio](install-visual-studio.md)
* [Руководство администратора Visual Studio](visual-studio-administrator-guide.md)
* [Использование параметров командной строки для установки Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
* [Средства для обнаружения экземпляров Visual Studio и управления ими](tools-for-managing-visual-studio-instances.md)
* [Управление обновлением сетевых развертываний Visual Studio](controlling-updates-to-visual-studio-deployments.md)
