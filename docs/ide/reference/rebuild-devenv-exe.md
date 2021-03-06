---
title: -Rebuild (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /rebuild switch
- rebuild Devenv switch (/rebuild)
- projects [Visual Studio], rebuilding
- /rebuild Devenv switch
- applications [Visual Studio], rebuilding
ms.assetid: c5a8a4bf-0e2b-46eb-a44a-8aeb29b92c32
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b0946137cb259386648b7b3ac2883c33f5724352
ms.sourcegitcommit: 54c65f81a138fc1e8ff1826f7bd9dcec710618cc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2018
ms.locfileid: "51948613"
---
# <a name="rebuild-devenvexe"></a>/Rebuild (devenv.exe)
Удаляет и затем выполняет сборку заданной конфигурации решения.

## <a name="syntax"></a>Синтаксис

```cmd
devenv SolutionName /rebuild SolnConfigName [/project ProjName] [/projectconfig ProjConfigName]
```

## <a name="arguments"></a>Аргументы
 `SolnConfigName`

 Обязательно. Имя конфигурации решения, которая будет применяться для перестроения решения, указанного в `SolutionName`.

 `SolutionName`

 Обязательно. Полный путь и имя для файла решения.

 /project `ProjName`

 Необязательный. Путь и имя для файла проекта в решении. Можно ввести относительный путь из папки `SolutionName` к файлу проекта, отображаемое имя проекта либо полный путь и имя для файла проекта.

 /projectconfig `ProjConfigName`

 Необязательный. Имя конфигурации сборки проекта, которая применяется при перестроении указанного `/project`.

## <a name="remarks"></a>Примечания

-   Этот параметр выполняет те же функции, что и команда меню **Перестроить решение** в интегрированной среде разработки (IDE).

-   Строки с пробелами заключаются в двойные кавычки.

-   Сводные данные для удаления и сборки, включая ошибки, могут отображаться в окне **Команда** или любом файле журнала, указанном с помощью параметра `/out`.

## <a name="example"></a>Пример
 В этом примере выполняется удаление и перестроение проекта `CSharpWinApp` с помощью конфигурации сборки `Debug` в конфигурации решения `Debug` `MySolution`.

```cmd
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /rebuild Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug
```

## <a name="see-also"></a>См. также

- [Параметры командной строки для devenv](../../ide/reference/devenv-command-line-switches.md)
- [/Build (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)
- [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)