---
title: "Слишком много аргументов типа для &quot;&lt;genericMethodName&gt;&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc32043"
  - "vbc32043"
helpviewer_keywords: 
  - "BC32043"
ms.assetid: c4d8f67a-4317-461a-9446-6717cfa1d888
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Слишком много аргументов типа для &quot;&lt;genericMethodName&gt;&quot;
Универсальный метод был вызван с большим числом аргументов типа, чем число параметров типа.  
  
 При вызове универсального метода вы должны представить по одному аргументу типа для каждого параметра типа, определяемого этим методом.  
  
 **Идентификатор ошибки:** BC32043  
  
### Исправление ошибки  
  
-   Удалите аргументы типа из списка аргументов типа так, чтобы имелось по одному аргументу типа для каждого параметра типа в вызываемом универсальном методе.  
  
## См. также  
 [Универсальные типы в Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Список типов](/dotnet/visual-basic/language-reference/statements/type-list)