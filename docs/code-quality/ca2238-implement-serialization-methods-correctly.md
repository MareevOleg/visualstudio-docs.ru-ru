---
title: 'CA2238: следует правильно реализовывать методы сериализации'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ImplementSerializationMethodsCorrectly
- CA2238
helpviewer_keywords:
- ImplementSerializationMethodsCorrectly
- CA2238
ms.assetid: 00882cf9-e10d-4d40-9126-3e6753e3c934
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: c6f25aa6aa574f856bcce7601602ed2f195e785a
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49949543"
---
# <a name="ca2238-implement-serialization-methods-correctly"></a>CA2238: следует правильно реализовывать методы сериализации

|||
|-|-|
|TypeName|ImplementSerializationMethodsCorrectly|
|CheckId|CA2238|
|Категория|Microsoft.Usage|
|Критическое изменение|Критическое, если метод является видимым извне.<br /><br /> Не критическое, если метод не видимый за пределами сборки.|

## <a name="cause"></a>Причина
 Метод, обрабатывающий событие сериализации, не имеет правильной сигнатуры, типа возвращаемого значения или отображения.

## <a name="rule-description"></a>Описание правила
 Метод назначается обработчику событий сериализации, применив один из следующих атрибутов сериализации события:

- <xref:System.Runtime.Serialization.OnSerializingAttribute?displayProperty=fullName>

- <xref:System.Runtime.Serialization.OnSerializedAttribute?displayProperty=fullName>

- <xref:System.Runtime.Serialization.OnDeserializingAttribute?displayProperty=fullName>

- <xref:System.Runtime.Serialization.OnDeserializedAttribute?displayProperty=fullName>

  Обработчики событий сериализации принимать один параметр типа <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>, возвращают `void`и иметь `private` видимости.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Чтобы устранить нарушение данного правила, исправьте подпись, тип возвращаемого значения или видимость обработчика событий сериализации.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Для этого правила отключать вывод предупреждений не следует.

## <a name="example"></a>Пример
 Следующий пример показывает правильное объявление сериализации обработчики событий.

 [!code-vb[FxCop.Usage.SerializationEventHandlers#1](../code-quality/codesnippet/VisualBasic/ca2238-implement-serialization-methods-correctly_1.vb)]
 [!code-csharp[FxCop.Usage.SerializationEventHandlers#1](../code-quality/codesnippet/CSharp/ca2238-implement-serialization-methods-correctly_1.cs)]

## <a name="related-rules"></a>Связанные правила
 [CA2236: вызывайте методы базового класса для типов ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

 [CA2240: правильно реализуйте ISerializable](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229: применяйте конструкторы сериализации](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2235: помечайте все несериализуемые поля](../code-quality/ca2235-mark-all-non-serializable-fields.md)

 [CA2237: пометьте типы ISerializable атрибутом SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

 [CA2239: обеспечьте наличие методов десериализации в необязательных полях](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

 [CA2120: обеспечьте безопасность конструкторов сериализации](../code-quality/ca2120-secure-serialization-constructors.md)