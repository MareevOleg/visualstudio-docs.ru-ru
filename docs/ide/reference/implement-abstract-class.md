---
title: Реализация абстрактного класса
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: dfa2c6692ddcef9e41454bf902580f354c32f861
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/07/2018
ms.locfileid: "53047607"
---
# <a name="implement-an-abstract-class-in-visual-studio"></a>Реализация абстрактного класса в Visual Studio

Область применения этого формирования кода:

- C#

- Visual Basic

**Что?** Вы можете сразу же создать код, необходимый для реализации абстрактного класса.

**Когда?** Если нужно наследовать абстрактный класс.

**Зачем?** Вы можете вручную реализовать все абстрактные элементы по одному, но этот компонент позволяет автоматически создать все сигнатуры метода.

## <a name="how-to"></a>Практические советы

1. Поместите курсор в строку с красной волнистой линией. Она указывает, что вы ссылаетесь на абстрактный класс, но не реализовали все необходимые элементы.

   - C#:

       ![Выделенный код C#](media/abstract-highlight-cs.png)

   - Visual Basic:

       ![Выделенный код VB](media/abstract-highlight-vb.png)

2. Затем выполните одно из следующих действий:

   - **Клавиатура**
      - Нажмите клавиши **CTRL**+**.** чтобы открыть меню **Быстрые действия и рефакторинг**.
   - **Мышь**
      - Щелкните правой кнопкой мыши и выберите меню **Быстрые действия и рефакторинг**.
      - Наведите указатель мыши на красную волнистую линию и щелкните появившийся значок ![Значок лампочки](media/bulb-cs.png) , который отображается.
      - Нажмите кнопку ![Значок лампочки](media/bulb-cs.png) , который отображается в левом поле, если текстовый курсор уже находится в строке выбора с красной волнистой линией.

   ![Предварительный просмотр реализации класса](media/abstract-preview-cs.png)

3. Выберите **Реализовать абстрактный класс** в раскрывающемся меню.

   > [!TIP]
   > - Щелкните ссылку **Просмотреть изменения** в нижней части окна предварительного просмотра, [чтобы просмотреть все будущие изменения](../../ide/preview-changes.md), прежде чем выбрать элементы.
   > - Используйте ссылки **Документ**, **Проект** и **Решение** в нижней части окна предварительного просмотра, чтобы создать правильные сигнатуры методов в нескольких классах, которые наследуют от абстрактного класса.

   Сигнатуры методов абстрактного класса создаются уже готовыми для реализации.

   - C#:

       ![Результат реализации класса в C#](media/abstract-result-cs.png)

   - Visual Basic:

       ![Результат реализации класса в VB](media/abstract-result-vb.png)

## <a name="see-also"></a>См. также

- [Создание кода](../code-generation-in-visual-studio.md)
- [Просмотр изменений](../../ide/preview-changes.md)