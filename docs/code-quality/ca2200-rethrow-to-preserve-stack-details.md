---
title: 'CA2200: следует повторно вызывать исключение для сохранения сведений о стеке'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- RethrowToPreserveStackDetails
- CA2200
helpviewer_keywords:
- CA2200
- RethrowToPreserveStackDetails
ms.assetid: 046e1b98-c4dc-4515-874f-9c0de2285621
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 1cc85931ed51bcd3df3a044452af59a530746805
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "45550894"
---
# <a name="ca2200-rethrow-to-preserve-stack-details"></a>CA2200: следует повторно вызывать исключение для сохранения сведений о стеке

|||
|-|-|
|TypeName|RethrowToPreserveStackDetails|
|CheckId|CA2200|
|Категория|Microsoft.Usage|
|Критическое изменение|Не критическое|

## <a name="cause"></a>Причина

Исключение создается снова, и явным образом задается исключение в `throw` инструкции.

## <a name="rule-description"></a>Описание правила

Когда создается исключение, часть сведений, содержащихся в нем показана трассировка стека. Трассировка стека приведен список иерархии вызовов метода, который начинается с методом, который создает исключение и заканчивается на метод, который перехватывает исключение. Если создано исключение повторно, указав исключение в `throw` инструкции, трассировка стека перезапускается в текущего метода и список вызовов метода между исходным методом, создавшим исключение и текущим методом будет утерян. Чтобы сохранить исходные сведения о трассировке стека с исключением, используйте `throw` инструкции без указания исключения.

## <a name="how-to-fix-violations"></a>Устранение нарушений

Чтобы устранить нарушение этого правила, заново создать исключение без явного указания исключения.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений

Для этого правила отключать вывод предупреждений не следует.

## <a name="example"></a>Пример

В следующем примере показан метод `CatchAndRethrowExplicitly`, который нарушает правило и метод, `CatchAndRethrowImplicitly`, которой соблюдается правило.

[!code-csharp[FxCop.Usage.Rethrow#1](../code-quality/codesnippet/CSharp/ca2200-rethrow-to-preserve-stack-details_1.cs)]
[!code-vb[FxCop.Usage.Rethrow#1](../code-quality/codesnippet/VisualBasic/ca2200-rethrow-to-preserve-stack-details_1.vb)]