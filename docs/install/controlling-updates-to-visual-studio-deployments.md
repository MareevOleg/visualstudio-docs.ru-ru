---
title: Управление обновлением развертываний
description: Узнайте, как изменить расположение, в котором Visual Studio ищет обновления при установке из сети.
ms.date: 08/14/2017
ms.technology: vs-acquisition
ms.custom: seodec18
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 35C7AB05-07D5-4B38-BCAC-AB88444E7368
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c6f5170b0838e51fb03e17c2f627665c7e64dfd7
ms.sourcegitcommit: 0cdd8e8a53fb4fd5e869f07c35204419fa12783d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53159767"
---
# <a name="control-updates-to-network-based-visual-studio-deployments"></a>Управление обновлением сетевых развертываний Visual Studio

Администраторы предприятий часто создают макеты и размещают их на общих сетевых ресурсах, чтобы затем развертывать их для конечных пользователей.

## <a name="controlling-where-visual-studio-looks-for-updates"></a>Определение места, в котором Visual Studio будет искать обновления

По умолчанию Visual Studio продолжает искать обновления в Интернете, даже если установка была развернута из общей сетевой папки. Если обновление доступно, пользователь может установить его. Обновленное содержимое, которое не найдено в автономном макете, скачивается из Интернета.

Чтобы напрямую контролировать места, в которых Visual Studio выполняет поиск обновлений, можно изменить расположения для поиска. Также можно контролировать версию, до которой пользователи выполняют обновление. Для этого выполните следующие действия.

1. Создайте автономный макет.
   ```cmd
   vs_enterprise.exe --layout C:\vs2017offline --lang en-US
   ```
2. Скопируйте его в общую сетевую папку, в которой будете его размещать.
   ```cmd
   xcopy /e C:\vs2017offline \\server\share\VS2017
   ```
3. Измените в этом макете файл response.json, указав для параметра `channelUri` значение, указывающее на управляемую администратором копию файла channelManifest.json.

   Не забудьте экранировать все символы обратной косой черты в этом значении, как показано в следующем примере:

   ```json
   "channelUri":"\\\\server\\share\\VS2017\\ChannelManifest.json"
   ```

   Теперь конечные пользователи могут выполнять установку Visual Studio из этой папки.
   ```cmd
   \\server\share\VS2017\vs_enterprise.exe
   ```

Когда администратор предприятия решит, что нужно обновить установки пользователей до новой версии Visual Studio, ему нужно [обновить расположение макета](update-a-network-installation-of-visual-studio.md), разместив в нем обновленные файлы, как показано далее.

1. Используйте команду, аналогичную следующей:
   ```cmd
   vs_enterprise.exe --layout \\server\share\VS2017 --lang en-US
   ```
2. Убедитесь, что файл response.json в обновленном макете содержит все измененные вами значения параметров, в частности channelUri:
   ```json
   "channelUri":"\\\\server\\share\\VS2017\\ChannelManifest.json"
   ```
   Все существующие копии Visual Studio, установленные из этого макета, ищут обновления в `\\server\share\VS2017\ChannelManifest.json`. Если файл channelManifest.json новее, чем существующий в пользовательской установке, Visual Studio уведомит пользователя о наличии доступного обновления.

   Новые установки автоматически используют обновленную версию Visual Studio непосредственно из макета.

## <a name="controlling-notifications-in-the-visual-studio-ide"></a>Управление уведомлениями в интегрированной среде разработки Visual Studio

Как описано выше, среда разработки Visual Studio проверяет расположение, из которого она была установлена (например, общую сетевую папку или Интернет), чтобы определить наличие доступных обновлений. Когда Visual Studio обнаруживает обновление, она уведомляет пользователя с помощью флага уведомления в правом верхнем углу окна.

 ![Флаг уведомления о наличии обновлений](media/notification-flag.png)

Если вы не хотите, чтобы конечные пользователи получали уведомления об обновлениях, уведомления можно отключить. (Например, может потребоваться отключить уведомления при доставке обновлений через централизованный механизм распространения программного обеспечения.)

Так как Visual Studio 2017 [сохраняет параметры в частном реестре](tools-for-managing-visual-studio-instances.md#editing-the-registry-for-a-visual-studio-instance), вы не можете изменить реестр обычным способом. Но Visual Studio предоставляет служебную программу `vsregedit.exe`, с помощью которой вы можете изменить параметры Visual Studio. Чтобы отключить уведомления, выполните следующую команду:

```cmd
vsregedit.exe set "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise" HKCU ExtensionManager AutomaticallyCheckForUpdates2Override dword 0
```

(Не забудьте заменить каталог в соответствии с установленным экземпляром, который нужно изменить.)

> [!TIP]
> Используйте [vswhere.exe](tools-for-managing-visual-studio-instances.md#detecting-existing-visual-studio-instances) , чтобы найти определенный экземпляр Visual Studio на клиентской рабочей станции.

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>См. также

* [Установка Visual Studio](install-visual-studio.md)
* [Руководство администратора Visual Studio](visual-studio-administrator-guide.md)
* [Использование параметров командной строки для установки Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
* [Средства для управления экземплярами Visual Studio](tools-for-managing-visual-studio-instances.md)
