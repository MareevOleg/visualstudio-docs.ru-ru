---
title: Написание кода JavaScript в Visual Studio без решения или проекта
description: Visual Studio поддерживает создание кода без зависимости от файла проекта или файла решения
ms.custom: ''
ms.date: 06/06/2018
ms.technology: vs-nodejs
ms.topic: conceptual
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: douge
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 7d56030b78abe57c80d816881991b9819ed6456b
ms.sourcegitcommit: db680e8fa8066f905e7f9240342ece7ab9259308
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2018
ms.locfileid: "37924744"
---
# <a name="develop-javascript-and-typescript-code-in-visual-studio-without-solutions-or-projects"></a>Разработка кода JavaScript и TypeScript в Visual Studio без решений или проектов

Visual Studio 2017 представляет возможность [разрабатывать код без проектов и решений](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md). Вы можете открыть папку кода и сразу же приступить к работе в полнофункциональном редакторе, используя IntelliSense, поиск, рефакторинг, отладку и многое другое.
Помимо этих функций, в инструменты Node.js для Visual Studio добавлена поддержка сборки файлов TypeScript, управления пакетами npm и выполнения сценариев npm.

Чтобы приступить к работе, нажмите **Открыть папку** на начальной странице, которая отображается при открытии Visual Studio, или выберите **Файл** > **Открыть** > **Папка** на панели инструментов. Обозреватель решений отображает все файлы в папке, и можно открыть любой из файлов, чтобы начать редактирование. В фоновом режиме Visual Studio индексирует файлы, предоставляя функции npm, сборки и отладки.

> [!IMPORTANT]
> Многие функции, описанные в этой статье, включая интеграцию npm, требуют Visual Studio 2017 версии 15.8, предварительная версия 3.

## <a name="npm-integration"></a>Интеграция npm

Если открытая папка содержит файл *package.json*, щелкните правой кнопкой мыши *package.json*, чтобы открыть контекстное меню для npm. 

![меню npm в обозревателе решений](../javascript/media/solution-explorer-npm-ctx.png) 

В контекстном меню вы можете управлять пакетами, установленными npm, так же, как вы [управляете пакетами npm](npm-package-management.md) при использовании файла проекта.

Кроме того, в меню можно выполнять сценарии, определенные в элементе `scripts` в *package.json*. Эти скрипты будут использовать версию Node.js, доступную в переменной среды `PATH`. Скрипты выполняются в новом окне. Это отличный способ сборки и выполнения скриптов.

## <a name="build-and-debug"></a>Сборка и отладка

### <a name="packagejson"></a>package.json
Если *package.json* в папке указывает элемент `main`, команда **отладки** будет доступна в контекстном меню для *package.json*. При нажатии этой кнопки запускается *node.exe* с указанным скриптом в качестве аргумента.

### <a name="javascript-files"></a>Файлы JavaScript
Вы можете отлаживать файлы JavaScript, щелкнув файл правой кнопкой мыши и выбрав **Отладка** в контекстном меню. Запустится *node.exe* с этим файлом JavaScript в качестве аргумента.

### <a name="typescript-files-and-tsconfigjson"></a>Файлы TypeScript и tsconfig.json
Если в папке нет файла *tsconfig.json*, щелкните правой кнопкой мыши файл TypeScript, чтобы открыть команды контекстного меню и скомпилировать и отладить этот файл. При использовании этих команд сборка и отладка выполняются с помощью *tsc.exe* с параметрами по умолчанию. (Вам нужно создать файл до отладки.)

> [!NOTE]
> При создании кода TypeScript мы используем последнюю версию, установленную в `C:\Program Files (x86)\Microsoft SDKs\TypeScript`.

Если в папке есть файл *tsconfig.json*, щелкните правой кнопкой мыши файл TypeScript, чтобы открыть команду меню для отладки этого файла TypeScript. Этот параметр отображается только в том случае, если в *tsconfig.json* не указан `outFile`. Если `outFile` указан, для отладки этого файла щелкните правой кнопкой мыши *tsconfig.json* и выберите нужный параметр. Файл `tsconfig.json` также предоставляет параметр сборки для указания параметров компилятора.

> [!NOTE]
> Дополнительные сведения о файле *tsconfig.json* см. на [странице руководства по tsconfig.json в TypeScript](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html).