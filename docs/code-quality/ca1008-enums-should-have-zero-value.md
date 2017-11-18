---
title: 'CA1008: Enums should have zero value | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1008
- EnumsShouldHaveZeroValue
helpviewer_keywords:
- CA1008
- EnumsShouldHaveZeroValue
ms.assetid: 3503a73c-360c-416d-8ee4-c2aa44365a05
caps.latest.revision: 21
author: stevehoag
ms.author: shoag
manager: wpickett
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: eb5c9550fd29b0e98bf63a7240737da4f13f3249
ms.openlocfilehash: e361d2406b3b2d8e54d9436d316e42dbb5221a8c
ms.contentlocale: ru-ru
ms.lasthandoff: 08/30/2017

---
# <a name="ca1008-enums-should-have-zero-value"></a>CA1008: Enums should have zero value
|||  
|-|-|  
|TypeName|EnumsShouldHaveZeroValue|  
|CheckId|CA1008|  
|Category|Microsoft.Design|  
|Breaking Change|Non-breaking - When you are prompted to add a **None** value to a non-flag enumeration.Breaking - When you are prompted to rename or remove any enumeration values.|  
  
## <a name="cause"></a>Cause  
 An enumeration without an applied <xref:System.FlagsAttribute?displayProperty=fullName> does not define a member that has a value of zero; or an enumeration that has an applied <xref:System.FlagsAttribute> defines a member that has a value of zero but its name is not 'None', or the enumeration defines multiple zero-valued members.  
  
## <a name="rule-description"></a>Rule Description  
 The default value of an uninitialized enumeration, just like other value types, is zero. A non-flags-attributed enumeration should define a member that has the value of zero so that the default value is a valid value of the enumeration. If appropriate, name the member 'None'. Otherwise, assign zero to the most frequently used member. Note that, by default, if the value of the first enumeration member is not set in the declaration, its value is zero.  
  
 If an enumeration that has the <xref:System.FlagsAttribute> applied defines a zero-valued member, its name should be 'None' to indicate that no values have been set in the enumeration. Using a zero-valued member for any other purpose is contrary to the use of the <xref:System.FlagsAttribute> in that the AND and OR bitwise operators are useless with the member. This implies that only one member should be assigned the value zero. Note that if multiple members that have the value zero occur in a flags-attributed enumeration, `Enum.ToString()` returns incorrect results for members that are not zero.  
  
## <a name="how-to-fix-violations"></a>How to Fix Violations  
 To fix a violation of this rule for non-flags-attributed enumerations, define a member that has the value of zero; this is a non-breaking change. For flags-attributed enumerations that define a zero-valued member, name this member 'None' and delete any other members that have a value of zero; this is a breaking change.  
  
## <a name="when-to-suppress-warnings"></a>When to Suppress Warnings  
 Do not suppress a warning from this rule except for flags-attributed enumerations that have previously shipped.  
  
## <a name="example"></a>Example  
 The following example shows two enumerations that satisfy the rule and an enumeration, `BadTraceOptions`, that violates the rule.  
  
 [!code-cpp[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/CPP/ca1008-enums-should-have-zero-value_1.cpp)] [!code-csharp[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/CSharp/ca1008-enums-should-have-zero-value_1.cs)] [!code-vb[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/VisualBasic/ca1008-enums-should-have-zero-value_1.vb)]  
  
## <a name="related-rules"></a>Related Rules  
 [CA2217: Do not mark enums with FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
 [CA1700: Do not name enum values 'Reserved'](../code-quality/ca1700-do-not-name-enum-values-reserved.md)  
  
 [CA1712: Do not prefix enum values with type name](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)  
  
 [CA1028: Enum storage should be Int32](../code-quality/ca1028-enum-storage-should-be-int32.md)  
  
 [CA1027: Mark enums with FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)  
  
## <a name="see-also"></a>See Also  
 <xref:System.Enum?displayProperty=fullName>