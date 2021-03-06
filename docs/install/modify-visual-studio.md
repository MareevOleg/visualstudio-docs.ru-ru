---
title: Изменение Visual Studio
titleSuffix: ''
description: Сведения о поэтапном изменении среды Visual Studio.
ms.custom: H1Hack27Feb2017,seodec18
ms.date: 06/12/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- modify Visual Studio
- change visual studio
- changing Visual Studio
- customize Visual Studio
ms.assetid: 3399ea7b-a291-4a9e-80a1-b861a21afa1d
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: efb52ebc55126fa167144803afc373317d735aae
ms.sourcegitcommit: 0cdd8e8a53fb4fd5e869f07c35204419fa12783d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53160066"
---
# <a name="modify-visual-studio-2017-by-adding-or-removing-workloads-and-components"></a>Изменение Visual Studio 2017 путем добавления или удаления рабочих нагрузок и компонентов

Мы упростили не только персонализацию Visual Studio в соответствии с выполняемыми задачами, но и настройку самой среды Visual Studio. Для этого запустите установщик Visual Studio и внесите нужные изменения.

Ниже описывается порядок действий.

## <a name="modify-workloads"></a>Изменение рабочих нагрузок

 Рабочие нагрузки содержат функции, которые требуются для используемого языка программирования или платформы. С помощью рабочих нагрузок можно изменить среду Visual Studio так, чтобы она поддерживала выполнение нужных задач в любое время.

>[!IMPORTANT]
>Чтобы установить, обновить или изменить среду Visual Studio, необходимо войти в учетную запись с правами администратора. Дополнительные сведения см. в разделе [Разрешения пользователей и Visual Studio](../ide/user-permissions-and-visual-studio.md).

1. Найдите установщик Visual Studio на своем компьютере.

     Например, на компьютере с Windows 10 нажмите кнопку **Пуск** и прокрутите список до буквы **V**, где расположен пункт **Visual Studio Installer**.

     ![Установщик Visual Studio](media/vs2017-locate-the-visual-studio-installer.PNG "Поиск установщика Microsoft Visual Studio")

     >[!NOTE]
     >На некоторых компьютерах установщик Visual Studio может быть указан под буквой **"M"**  — для **Microsoft Visual Studio**.<br/><br/> Кроме того, Visual Studio Installer можно найти в следующем расположении: `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

2. Щелкните установщик (или коснитесь его), чтобы запустить, и выберите команду **Изменить**.

     ![Запустите или измените Visual Studio](media/modify-visual-studio.png "Изменение Visual Studio 2017")

     При наличии ожидающих обновлений кнопка "Изменить" будет находиться в другом месте. Таким образом, вы можете изменить Visual Studio без обновления, если захотите. Нажмите кнопку **Дополнительно**, затем кнопку **Изменить**.

     ![Обновление или изменение Visual Studio](media/modify-or-update-visual-studio.png "Обновление или изменение Visual Studio 2017")

3. На экране **Рабочие нагрузки** выберите рабочие нагрузки, которые нужно установить, или отмените выбор тех, которые нужно удалить.

    ![Диалоговое окно программы установки Visual Studio 2017](media/vs2017-modify-workloads.PNG "Выбор рабочей нагрузки в Visual Studio 2017")

4. Снова выберите команду **Изменить**.

5. После установки новых рабочих нагрузок и компонентов выберите команду **Запуск**.

## <a name="modify-individual-components"></a>Изменение отдельных компонентов

Если вы не хотите пользоваться удобной функцией рабочих нагрузок для настройки установленного экземпляра Visual Studio, выберите в установщике Visual Studio вариант **Отдельные компоненты**, затем включите нужные компоненты и следуйте указаниям.

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>См. также

* [Установка Visual Studio 2017](install-visual-studio.md)
* [Обновление Visual Studio 2017](update-visual-studio.md)
* [Удаление Visual Studio 2017](uninstall-visual-studio.md)
