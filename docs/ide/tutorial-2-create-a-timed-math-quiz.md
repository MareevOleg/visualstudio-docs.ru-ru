---
title: Руководство 2. Создание ограниченной по времени математической головоломки
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: d7165d08-ace3-457d-b57d-fb8f80760a6f
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 38a0cef2600234be17b80fc53ac40a828ad6e2f7
ms.sourcegitcommit: be938c7ecd756a11c9de3e6019a490d0e52b4190
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50672643"
---
# <a name="tutorial-2-create-a-timed-math-quiz"></a>Руководство 2. Создание ограниченной по времени математической головоломки

В этом учебнике вам предстоит создать головоломку, в которой игрок должен решить четыре арифметические задачи со случайными числами за определенное время. Вы научитесь:

-   Создавать случайные числа с помощью класса <xref:System.Random>.

-   Активировать события, чтобы они происходили в определенное время, с помощью элемента управления <xref:System.Windows.Forms.Timer>.

-   Управлять выполнением программы с помощью операторов `if else`.

-   Выполнять простые арифметические операции в коде.

По завершении урока задача будет выглядеть так, как показано на следующем рисунке, только с другими цифрами:

![Математическая головоломка с четырьмя задачами](../ide/media/express_finishedquiz.png)

## <a name="tutorial-links"></a>Ссылки на руководства

Скачать готовую версию головоломки можно на странице с [полным примером руководства по созданию математической головоломки](https://code.msdn.microsoft.com/Complete-Math-Quiz-8581813c).

> [!NOTE]
> В этом учебнике приведены примеры как на Visual C#, так и на Visual Basic, поэтому обращайте внимание на информацию, которая относится к используемому вами языку программирования.

## <a name="related-topics"></a>См. также

|Заголовок|Описание:|
|-----------|-----------------|
|[Шаг 1. Создание проекта и добавление в форму элементов управления Label](../ide/step-1-create-a-project-and-add-labels-to-your-form.md)|Начало работы: создание проекта, изменение свойств и добавление элементов управления `Label`.|
|[Шаг 2. Создание задачи на сложение случайных чисел](../ide/step-2-create-a-random-addition-problem.md)|Создание задачи на сложение с использованием класса `Random` для генерации случайных чисел.|
|[Шаг 3. Добавление таймера с обратным отсчетом](../ide/step-3-add-a-countdown-timer.md)|Добавление таймера обратного отсчета, чтобы головоломка была ограничена по времени.|
|[Шаг 4. Добавление метода CheckTheAnswer()](../ide/step-4-add-the-checktheanswer-parens-method.md)|Добавление метода для проверки того, правильный ли ответ на задачу ввел игрок.|
|[Шаг 5. Добавление обработчиков событий входа для элементов управления NumericUpDown](../ide/step-5-add-enter-event-handlers-for-the-numericupdown-controls.md)|Добавление обработчиков событий, чтобы сделать головоломку удобнее.|
|[Шаг 6. Добавление задачи на вычитание](../ide/step-6-add-a-subtraction-problem.md)|Добавление задачи на вычитание с генерацией случайных чисел, использованием таймера и проверкой правильности ответов.|
|[Шаг 7. Добавление задач на умножение и деление](../ide/step-7-add-multiplication-and-division-problems.md)|Добавление задач на умножение и деление с генерацией случайных чисел, использованием таймера и проверкой правильности ответов.|
|[Шаг 8. Настройка головоломки](../ide/step-8-customize-the-quiz.md)|Изучение других возможностей, например, изменение цветов и добавление подсказки.|
