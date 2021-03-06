---
title: Создание первого консольного приложения на Visual Basic
description: Ознакомьтесь с пошаговыми инструкциями по созданию простого консольного приложения "Hello World" на Visual Basic в Visual Studio.
ms.date: 12/10/2017
ms.prod: visual-studio-dev15
ms.custom: seodec18
ms.technology: vs-acquisition
ms.topic: quickstart
ms.devlang: vb
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- vb
ms.workload:
- multiple
ms.openlocfilehash: 67a990b98b385cacab89bfa8270d8409f9e9aa5f
ms.sourcegitcommit: 0cdd8e8a53fb4fd5e869f07c35204419fa12783d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53159611"
---
# <a name="quickstart-create-your-first-console-app-in-visual-studio-with-visual-basic"></a>Краткое руководство. Создание первого консольного приложения на Visual Basic в Visual Studio

В рамках этого краткого (на 5–10 минут) знакомства с возможностями интегрированной среды разработки Visual Studio (IDE) вы создадите простое приложение на Visual Basic, выполняющееся в консоли.

Установите Visual Studio бесплатно со страницы [скачиваемых материалов Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), если еще не сделали этого.

## <a name="create-a-project"></a>Создание проекта

Сначала вы создадите проект приложения Visual Basic. Для этого типа проекта уже имеются все нужные файлы шаблонов, что избавляет вас от лишней работы.

1. Откройте Visual Studio 2017.

2. В верхней строке меню выберите **Файл** > **Создать** > **Проект**.

3. В левой области диалогового окна **Новый проект** разверните узел **Visual Basic** и выберите **.NET Core**. На средней панели выберите **Консольное приложение (.NET Core)**. Назовите проект *HelloWorld*.

   ![Шаблон проекта "Консольное приложение (.NET Core)" в диалоговом окне "Новый проект" в интегрированной среде разработки Visual Studio](../ide/media/new-project-vb-dotnetcore-helloworld-console-app.png)

     Если шаблон проекта **Консольное приложение (.NET Core)** отсутствует, выберите ссылку **Открыть Visual Studio Installer** в левой области диалогового окна **Новый проект**.

   ![Выбор ссылки "Открыть Visual Studio Installer" в диалоговом окне "Новый проект"](../ide/media/vb-open-visual-studio-installer-hello-world.png)

     Запускается Visual Studio Installer. Выберите рабочую нагрузку **Кроссплатформенная разработка .NET Core** и затем элемент **Изменить**.

     ![Рабочая нагрузка "Кроссплатформенная разработка .NET Core" в Visual Studio Installer](../ide/media/dot-net-core-xplat-dev-workload.png)

## <a name="create-the-application"></a>Создание приложения

Когда вы выберете шаблон проекта Visual Basic и зададите имя проекта, Visual Studio создает простое приложение "Hello World". Он вызывает метод <xref:System.Console.WriteLine%2A> для отображения литеральной строки "Hello World!" в окне консоли.

![Просмотр кода "Hello World" по умолчанию на основе шаблона](../ide/media/vb-console-helloworld-template.png)

Вы можете запустить программу в режиме отладки, нажав кнопку **HelloWorld** в интегрированной среде разработки.

  ![Нажмите кнопку "HelloWorld", чтобы запустить программу в режиме отладки](../ide/media/vb-console-hello-world-button.png)

При этом окно консоли отображается на короткое время и затем сразу же закрывается. Это происходит потому, что метод `Main` завершается после выполнения его единственного оператора, после чего завершается работа приложения.

### <a name="add-some-code"></a>Добавление кода

Давайте добавим код, чтобы приостановить выполнение приложения и запросить ввод данных пользователем.

1. Добавьте следующий код сразу после вызова метода <xref:System.Console.WriteLine%2A>:

   ```vb
   Console.Write("Press any key to continue...")
   Console.ReadKey(true)
   ```

    Это приостанавливает выполнение программы до нажатия клавиши.

2. В строке меню выберите **Сборка** > **Собрать решение**.

   При этом программа компилируется в промежуточный язык IL, который затем преобразуется в двоичный код JIT-компилятором.

## <a name="run-the-application"></a>Запуск приложения

1. В панели инструментов нажмите кнопку **HelloWorld**.

   ![Нажмите кнопку "HelloWorld", чтобы запустить программу из панели инструментов](../ide/media/vb-console-hello-world-button.png)

2. Для закрытия консольного окна нажмите любую клавишу.

   ![Окно консоли с фразой "Hello World" и надписью "Чтобы продолжить, нажмите любую клавишу"](../ide/media/vb-console-hello-world-press-any-key.png)

## <a name="next-steps"></a>Следующие шаги

Поздравляем с завершением этого краткого руководства! Надеемся, что вы узнали нечто новое о Visual Basic и интегрированной среде разработки Visual Studio. Для получения дополнительных сведений перейдите к следующему учебнику.

> [!div class="nextstepaction"]
> [Начало работы с Visual Basic в Visual Studio](tutorial-visual-basic-console.md)
