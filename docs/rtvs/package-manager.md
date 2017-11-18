---
title: "Диспетчер пакетов в инструментах R для Visual Studio | Документация Майкрософт"
ms.custom: 
ms.date: 06/29/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93accb9a-1ef8-4806-baa4-02477c2d7ef0
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 87f4c97941a55bd378a72681200748f28e8dd236
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
---
# <a name="package-manager"></a>Диспетчер пакетов

Диспетчер пакетов в инструментах R для Visual Studio (RTVS) — это пользовательский интерфейс для управления пакетами R. Чтобы открыть его, выберите **Инструменты R > Окна > Пакеты** или нажмите клавиши CTRL + 7.

В диспетчере пакетов имеется три вкладки. На каждой отображаются списки соответствующих пакетов (слева) и определенные сведения о выбранном пакете (справа), включая версию пакета, описание, сведения о лицензии, расположении установки пакета, а также ссылки на другие важные сведения. С помощью поля поиска в правом верхнем углу можно сортировать список.

> [!Tip]
> Текст в поле поиска сохраняется при переключении между вкладками.

- **Доступные** — список пакетов для установки. Если пакет уже установлен, кнопка **Установить** справа изменяется на **Удалить**.

    ![Вкладка доступных пакетов в диспетчере пакетов в инструментах R для Visual Studio](media/package-manager-available.png)

- **Установленные** — список всех установленных и загруженных пакетов. Зеленая точка рядом с пакетом указывает на то, что пакет загружен в сеанс R. Чтобы удалить пакет, воспользуйтесь красным значком X слева или кнопкой **Удалить** справа. Если доступна более новая версия установленного пакета, расположенная справа синяя стрелка вверх позволяет обновить его.

    ![Вкладка установленных пакетов в диспетчере пакетов в инструментах R для Visual Studio](media/package-manager-installed.png)

- На вкладке **Загруженные** отображаются только те пакеты, которые загружены в сеанс R, поэтому для всех таких пакетов отображаются зеленые точки. Здесь можно также удалить и обновить пакеты.

    ![Вкладка загруженных пакетов в диспетчере пакетов в инструментах R для Visual Studio](media/package-manager-loaded.png)

## <a name="package-locations"></a>Расположения пакетов

Пакеты устанавливаются в следующие расположения.

- Основные пакеты, которые входят в состав RTVS, устанавливаются в каталог `C:\Program Files\Microsoft\R Client\R_SERVER\library`
- Дополнительные пакеты устанавливаются в каталог `%userprofile%\Documents\R\win-library\3.3`