---
title: 'CA1502: избегайте чрезмерной сложности'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidExcessiveComplexity
- CA1502
helpviewer_keywords:
- CA1502
- AvoidExcessiveComplexity
ms.assetid: d735454b-2f8f-47ce-907d-f7a5a5391221
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: bfa12a2a1ade8d32c5518660c46ce79bc997d776
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49819307"
---
# <a name="ca1502-avoid-excessive-complexity"></a>CA1502: избегайте чрезмерной сложности

|||
|-|-|
|TypeName|AvoidExcessiveComplexity|
|CheckId|CA1502|
|Категория|Microsoft.Maintainability|
|Критическое изменение|Не критическое|

## <a name="cause"></a>Причина

Метод имеет чрезмерной цикломатической сложностью.

## <a name="rule-description"></a>Описание правила

*Сложность организации циклов* измеряет число линейно независимых путей в методе, который определяется числом и сложностью условных ветвей. Как правило, низкая сложность указывает метод, который проще воспринимать, тестировать и поддерживать. Сложность организации циклов вычисляется на основе диаграммы потока управления метода и задается следующим образом:

сложность организации циклов = количеству краев - количество узлов + 1

где узел представляет логическую точку ветвления и ребро представляет линию между узлами.

Правило сообщает о нарушение при более чем 25 цикломатической сложности.

Дополнительные сведения о метриках кода в [Оценка сложности и удобства сопровождения управляемого кода](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md),

## <a name="how-to-fix-violations"></a>Устранение нарушений

Чтобы устранить нарушение этого правила, выполнить рефакторинг метода, чтобы снизить его сложность организации циклов.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений

Его можно безопасно подавить предупреждение из этого правила, если трудно уменьшить сложность и проще воспринимать, тестировать и поддерживать метод. В частности, метод, который содержит большой `switch` (`Select` в [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) инструкция является кандидатом для исключения. Риском нарушения стабильности кодовая база, позднее в цикле разработки или внесения непредвиденных изменений в поведение во время выполнения в ранее выпущенном коде может перевесить преимущества удобства поддержки оптимизации кода.

## <a name="how-cyclomatic-complexity-is-calculated"></a>Как вычисляется сложность организации циклов

Сложность организации циклов рассчитывается путем сложения 1 следующим:

- Количество ветвей (таких как `if`, `while`, и `do`)

- Число `case` инструкций в `switch`

## <a name="example"></a>Пример

Ниже приведены примеры методов, имеющих различные цикломатической сложности.

**Сложность организации циклов 1**

[!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_1.cpp)]
[!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_1.vb)]
[!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_1.cs)]

## <a name="example"></a>Пример

**Сложность организации циклов 2**

[!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_2.cpp)]
[!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_2.vb)]
[!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_2.cs)]

## <a name="example"></a>Пример

**Сложность организации циклов 3**

[!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_3.cpp)]
[!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_3.vb)]
[!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_3.cs)]

## <a name="example"></a>Пример

**Сложность организации циклов 8**

[!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_4.cpp)]
[!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_4.vb)]
[!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_4.cs)]

## <a name="related-rules"></a>Связанные правила

[CA1501: избегайте излишнего наследования](../code-quality/ca1501-avoid-excessive-inheritance.md)

## <a name="see-also"></a>См. также

- [Оценка сложности и удобства сопровождения управляемого кода](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)