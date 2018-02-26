---
title: "Создание поля, свойства или локальной переменной в Visual Studio | Документы Майкрософт"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 8de048928286017d4e6f79bda6aff804b49d3150
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2018
---
# <a name="generate-a-field-property-or-local-variable-in-visual-studio"></a>Создание поля, свойства или локальной переменной в Visual Studio

Область применения этого формирования кода:

- C#

- Visual Basic

**Что?** Вы можете сразу же создать код для ранее необъявленного поля, свойства или локальной переменной.

**Когда?** Вы представляете новое поле, свойство или локальную переменную при вводе и хотите правильно объявить их автоматически.

**Зачем?** Вы можете объявить поле, свойство или локальную переменную перед их использованием, но эта функция позволяет создать объявление и тип автоматически.

## <a name="how-to"></a>Практические советы

1. Поместите курсор в строку с красной волнистой линией. Она указывает на поле, локальную переменную или свойство, которые не существуют.

   - C#:

    ![Выделенный код C#](media/field-highlight-cs.png)

   - Visual Basic:

    ![Выделенный код VB](media/field-highlight-vb.png)

1. Затем выполните одно из следующих действий:

   - **Клавиатура**
     - Нажмите клавиши **CTRL + .**, чтобы открыть меню **Быстрые действия и рефакторинг**.
   - **Мышь**
     - Щелкните правой кнопкой мыши и выберите меню **Быстрые действия и рефакторинг**.
     - Наведите указатель мыши на красную волнистую линию и щелкните появившийся значок ![Значок лампочки](media/bulb-cs.png) .
     - Нажмите кнопку ![Значок лампочки](media/bulb-cs.png) который отображается в левом поле, если текстовый курсор уже находится в строке выбора с красной волнистой линией.

    ![Предварительный просмотр создаваемого поля, свойства или локальной переменной](media/field-preview-cs.png)

1. В раскрывающемся списке выберите один из параметров создания.

   > [!TIP]
   > Щелкните ссылку **Просмотреть изменения** в нижней части окна предварительного просмотра, [чтобы просмотреть все будущие изменения](../../ide/preview-changes.md), прежде чем выбрать элементы.

   Поле, свойство или локальная переменная создаются с типом, выводимым из их использования.

   - C#:

      ![Результат создания метода C#](media/field-result-cs.png)

   - Visual Basic:

      ![Результат создания метода VB](media/field-result-vb.png)

## <a name="see-also"></a>См. также

[Создание кода](../code-generation-in-visual-studio.md)  
[Просмотр изменений](../../ide/preview-changes.md)