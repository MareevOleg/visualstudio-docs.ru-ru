---
title: "Ошибка компилятора CS0026 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0026"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0026"
ms.assetid: 8767fbc1-8ba7-4e88-a9f9-7e620411882b
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Ошибка компилятора CS0026
Ключевое слово "this" не может использоваться в инициализаторах статических свойств, методов или полей.  
  
 Ключевое слово [this](/dotnet/csharp/language-reference/keywords/this) относится к объекту, который является экземпляром типа. Так как статические методы не зависят от экземпляров содержащего их класса, ключевое слово "this" не имеет смысла и использовать его не разрешено. Дополнительные сведения см. в разделах [Статические классы и члены статических классов](/dotnet/csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members) и [Объекты](/dotnet/csharp/programming-guide/classes-and-structs/objects).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки CS0026:  
  
```  
// CS0026.cs public class A { public static int i = 0; public static void Main() { // CS0026 this.i = this.i + 1; // Try the following line instead: // i = i + 1; } }  
```