---
title: Устранение неполадок, связанных с расширениями для схем зависимостей
ms.date: 11/04/2016
ms.topic: troubleshooting
helpviewer_keywords:
- dependency diagrams, extension errors
- dependency diagrams, troubleshooting extensions
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 8acde589ebf47d4a67609e847a84bd7c7acd8482
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49899647"
---
# <a name="troubleshoot-extensions-for-dependency-diagrams"></a>Устранение неполадок, связанных с расширениями для схем зависимостей

В этом разделе рассматриваются некоторые проблемы, которые могут возникнуть при создании расширений модели слоев.

## <a name="when-i-press-f5-to-debug-my-extension-my-commands-gesture-handlers-validation-extensions-or-custom-properties-do-not-appear-on-dependency-diagrams-in-the-experimental-instance-of-visual-studio"></a>При нажатии клавиши F5 для отладки расширения, команды, обработчики жестов, расширения проверки или пользовательские свойства не отображаются на диаграммах зависимостей в экспериментальном экземпляре Visual Studio

1. Откройте решение расширения в экспериментальном экземпляре Visual Studio, а на **построения** меню, щелкните **Перестроить решение**.

2. Нажмите клавишу **F5** или **CTRL + F5** запустить экспериментальный экземпляр Visual Studio. Откройте схему зависимостей и протестируйте расширение.

   При необходимости выполните описанную ниже процедуру.

## <a name="an-old-version-of-my-extension-runs"></a>Запускается старая версия расширения.

1. Убедитесь, что запущена не экспериментальный экземпляр Visual Studio.

2. Удалите следующую папку: %LocalAppData%\Microsoft\VisualStudio\\\ComponentModelCache [версия]

   > [!NOTE]
   > % LocalAppData % — *DriveName*: \Users\\*UserName*\AppData\Local.

   При необходимости выполните описанную ниже процедуру.

## <a name="an-old-version-of-my-validation-results-appears-or-my-validation-method-is-not-called"></a>Отображается старая версия результатов проверки, либо не вызывается метод проверки.

1.  В экспериментальном экземпляре Visual Studio на **построения** меню, щелкните **Очистить решение**. Она позволяет очистить кэшированные результаты предыдущего анализа проверки.

2.  Убедитесь в том, что слои в модели связаны с элементами кода и что в модели есть хотя бы одна связь зависимости. Проверка не вызывается, если нет элементов для проверки.

3.  Стандартные точки останова могут не работать в методе проверки, так как он выполняется в отдельном процессе. Для пошагового выполнения метода нужно вставить вызов метода `System.Diagnostics.Debugger.Launch()`.

4.  В **source.extension.vsixmanifest** проекта проверки слоев убедитесь, что добавлены оба **компонент MEF** элемента и **пользовательский тип расширения** в меню **Содержимого**.

## <a name="see-also"></a>См. также

- [Расширение схем зависимостей](../modeling/extend-layer-diagrams.md)
