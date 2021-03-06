---
title: Знакомство с IntelliTest
ms.date: 05/02/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- IntelliTest, Get started
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 3e33bab90c32ca1b7cd92714218e5694daa22aed
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2018
ms.locfileid: "51000743"
---
# <a name="get-started-with-microsoft-intellitest"></a>Приступая к работе с Microsoft IntelliTest

* Если вы сталкиваетесь с IntelliTest впервые:
  * посмотрите [видео на Channel 9](https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Intellitest);
  * прочитайте этот [обзор в журнале MSDN](https://msdn.microsoft.com/magazine/dn904672.aspx);
  * ознакомьтесь с [документацией](../../test/generate-unit-tests-for-your-code-with-intellitest.md).
* Задайте вопрос на сайте [Stack Overflow](http://stackoverflow.com/questions/tagged/intellitest).
* Прочитайте остальную часть этого справочного руководства.
* Распечатайте эту страницу в качестве краткого справочника.

## <a name="important-attributes"></a>Важные атрибуты

* [PexClass](attribute-glossary.md#pexclass) помечает тип, содержащий **PUT**.
* [PexMethod](attribute-glossary.md#pexmethod) помечает **PUT**.
* [PexAssumeNotNull](attribute-glossary.md#pexassumenotnull) помечает параметр, отличный от NULL.

```csharp
using Microsoft.Pex.Framework;

[..., PexClass(typeof(Foo))]
public partial class FooTest {
    [PexMethod]
    public void Bar([PexAssumeNotNull]Foo target, int i) {
        target.Bar(i);
    }
}
```

* [PexAssemblyUnderTest](attribute-glossary.md#pexassemblyundertest) привязывает тестовый проект к проекту.
* [PexInstrumentAssembly](attribute-glossary.md#pexinstrumentassemblyattribute) указывает сборку для инструментирования.

```csharp
[assembly: PexAssemblyUnderTest("MyAssembly")] // also instruments "MyAssembly"
[assembly: PexInstrumentAssembly("Lib")]
```

## <a name="helper-classes"></a> Важные статические вспомогательные классы

* [PexAssume](static-helper-classes.md#pexassume) вычисляет предположения (фильтрация ввода).
* [PexAssert](static-helper-classes.md#pexassert) вычисляет утверждения.
* [PexChoose](static-helper-classes.md#pexchoose) создает новые варианты (дополнительные входные данные).
* [PexObserve](static-helper-classes.md#pexobserve) регистрирует динамические значения для созданных тестов.

```csharp
[PexMethod]
void StaticHelpers(Foo target) {
    PexAssume.IsNotNull(target);

    int i = PexChoose.Value<int>("i");
    string result = target.Bar(i);

    PexObserve.ValueForViewing<string>("result", result);
    PexAssert.IsNotNull(result);
}
```

## <a name="got-feedback"></a>Хотите оставить отзыв?

Делитесь своими идеями и пожеланиями относительно новых функций в [сообществе разработчиков](https://developercommunity.visualstudio.com/content/idea/post.html?space=8).
