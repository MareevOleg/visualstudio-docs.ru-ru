---
title: Создание проекта модульного теста
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: c217b2956f5bff2f8aa5f44b88033f7f74580d3c
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/07/2018
ms.locfileid: "53059052"
---
# <a name="create-a-unit-test-project"></a>Создание проекта модульного теста

Модульные тесты зачастую отражают структуру тестируемого кода. Например, отдельный проект модульного теста может быть создан для каждого проекта в продукте. Тестовый проект может находиться в том же решении, что и рабочий код, или в отдельном решении. В решении может быть несколько проектов модульных тестов.

> [!NOTE]
> Расположение модульных тестов для машинного кода и структура тестового проекта могут отличаться от структуры, описанной в этом разделе. Дополнительные сведения см. в разделе [Создание модульных тестов для C/C++](writing-unit-tests-for-c-cpp.md).

## <a name="to-create-a-unit-test-project"></a>Создание проекта модульного теста

1.  В меню **Файл** выберите **Создать**, а затем **Проект** (сочетание клавиш **CTRL**+**SHIFT**+**N**).

2.  В диалоговом окне **Новый проект** разверните узел **Установлено**, выберите требуемый язык для тестового проекта, а затем **Тест**.

3.  Чтобы использовать одну из платформ модульного тестирования Microsoft выберите **Проект модульного тестирования** из списка шаблонов проекта. В иных случаях выберите шаблон проекта платформы модульного тестирования, который необходимо использовать. Для тестирования проекта Accounts из нашего примера назовите тестовый проект **AccountsTests**.

4.  В проекте модульного теста добавьте ссылку на тестируемый код.  Создать ссылку на проект в том же решении можно указанным ниже образом.

    1.  Выберите проект в **обозревателе решений**.

    2.  В меню **Проект** выберите **Добавить ссылку**.

    3.  В диалоговом окне **Диспетчер ссылок** откройте узел **Решение** и выберите **Проекты**. Выберите имя проекта кода и закройте диалоговое окно.

5.  Если код, который требуется протестировать, находится в другом месте, сведения о добавлении ссылок см. в разделе [Управление ссылками в проекте](../ide/managing-references-in-a-project.md).

## <a name="next-steps"></a>Следующие шаги

 См. один из следующих разделов:

**Создание модульных тестов**

- [Модульное тестирование кода](../test/unit-test-your-code.md)

- [Создание модульных тестов для C/C++](writing-unit-tests-for-c-cpp.md)

- [Использование платформы MSTest в модульных тестах](using-microsoft-visualstudio-testtools-unittesting-members-in-unit-tests.md)

**Выполнение модульных тестов**

- [Выполнение модульных тестов с помощью обозревателя тестов](../test/run-unit-tests-with-test-explorer.md)