---
title: 'CA1804: удалите неиспользуемые локальные переменные'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1804
- RemoveUnusedLocals
helpviewer_keywords:
- RemoveUnusedLocals
- CA1804
ms.assetid: cc332e67-6543-4813-bd8a-6f6fc75bf22a
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: b1846c1b8d9173db6d1f4b5acd0544fd601da67a
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "45545467"
---
# <a name="ca1804-remove-unused-locals"></a>CA1804: удалите неиспользуемые локальные переменные

|||
|-|-|
|TypeName|RemoveUnusedLocals|
|CheckId|CA1804|
|Категория|Microsoft.Performance|
|Критическое изменение|Не критическое|

## <a name="cause"></a>Причина
 Метод объявляет локальную переменную, но не использует переменную, за исключением возможно как получатель части оператора присваивания. Для анализа этим правилом протестированных сборки должны быть построены с отладочной информацией и связанный PDB-файл должен быть доступен.

## <a name="rule-description"></a>Описание правила
 Неиспользуемые локальные переменные и ненужные присвоения увеличивают размер сборки и снижают производительность.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Чтобы устранить нарушение этого правила, удалите или использовать локальную переменную. Обратите внимание, что компилятор C#, входит в состав [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] удаляет неиспользуемые локальные переменные при `optimize` включен параметр.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Отключайте предупреждение из этого правила, если переменная создана компилятором. Можно также безопасно подавить предупреждение из этого правила, или отключить правило, если производительность и обслуживание кода не являются критичными моментами.

## <a name="example"></a>Пример
 В следующем примере показано несколько неиспользуемые локальные переменные.

 [!code-vb[FxCop.Performance.UnusedLocals#1](../code-quality/codesnippet/VisualBasic/ca1804-remove-unused-locals_1.vb)]
 [!code-csharp[FxCop.Performance.UnusedLocals#1](../code-quality/codesnippet/CSharp/ca1804-remove-unused-locals_1.cs)]

## <a name="related-rules"></a>Связанные правила
 [CA1809: избегайте чрезмерного использования локальных переменных](../code-quality/ca1809-avoid-excessive-locals.md)

 [CA1811: не используйте невызываемый закрытый код](../code-quality/ca1811-avoid-uncalled-private-code.md)

 [CA1812: не создавайте внутренние классы без экземпляров](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1801: проверьте неиспользуемые параметры](../code-quality/ca1801-review-unused-parameters.md)