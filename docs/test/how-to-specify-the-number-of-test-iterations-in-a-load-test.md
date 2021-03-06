---
title: Указание числа повторов теста в параметрах выполнения нагрузочного теста
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, properties
- load tests, run settings
ms.assetid: 45a625db-b3e7-4d64-beda-b9a76248096d
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: e250096a99cfc272cd23b58bf0f7b70eeb3a7c9d
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/07/2018
ms.locfileid: "53059844"
---
# <a name="how-to-specify-the-number-of-test-iterations-in-a-load-test-run-setting"></a>Как выполнить Указание числа повторов теста в параметрах выполнения нагрузочного теста

После создания нагрузочного теста с помощью **мастера тестовой нагрузки** можно с помощью **редактора тестовой нагрузки** изменять свойства сценариев в соответствии с требованиями и целями тестирования. Дополнительные сведения см. в разделе [Пошаговое руководство: создание и запуск нагрузочного теста](../test/walkthrough-create-and-run-a-load-test.md).

Используя **редактор тестовой нагрузки**, можно изменить в окне **Свойства** значение свойства **Итерации теста** для параметров запуска. Свойство **Итерации теста** определяет число итераций веб-теста производительности или модульного теста во всех сценариях нагрузочного теста, запускаемого из **редактора тестовой нагрузки**.

> [!NOTE]
> Полный список свойств параметров запуска и их описание см. в статье [Свойства параметров запуска нагрузочного теста](../test/load-test-run-settings-properties.md).

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="to-specify-the-number-of-test-iterations-in-a-run-setting"></a>Указание числа повторов теста в параметрах запуска

1.  Откройте нагрузочный тест.

     Откроется **мастер тестовой нагрузки**, в котором будет показано дерево нагрузочного теста.

2.  В дереве нагрузочного теста разверните папку **Параметры запуска** и выберите параметр запуска.

3.  В меню **Вид** выберите пункт **Окно свойств**, чтобы просмотреть категории и свойства параметра запуска нагрузочного теста.

4.  Задайте для свойства **Использовать итерации теста** значение **Да**.

5.  В поле **Итерации теста** введите число, определяющее количество итераций, которое необходимо выполнить в рамках нагрузочного теста.

6.  По завершении изменения свойства в меню **Файл** выберите команду **Сохранить**. После этого нагрузочный тест можно запускать с новым значением параметра **Итерации теста**.

## <a name="see-also"></a>См. также

- [Настройка параметров запуска нагрузочных тестов](../test/configure-load-test-run-settings.md)
- [Свойства сценария тестовой нагрузки](../test/load-test-scenario-properties.md)