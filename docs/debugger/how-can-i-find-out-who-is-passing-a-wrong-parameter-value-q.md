---
title: "Как определить, откуда передается неправильное значение параметра? | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.parameters"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "отладка [C++], параметры"
  - "функции [отладчик], обнаружение неверных значений параметров"
  - "значения параметров, устранение неполадок"
  - "параметры [отладчик]"
  - "передача параметров, устранение неполадок при неверных значениях"
ms.assetid: 1f1ae455-0e25-4e9d-b33f-53908f5bd6ce
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Как определить, откуда передается неправильное значение параметра?
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

## Описание проблемы  
 Одной из функций передается неправильное значение параметра.  Эта функция вызывается по всей программе.  Как определить, откуда передается неправильное значение?  
  
## Решение  
  
#### Устранение неполадки  
  
1.  Установите точку останова в начале функции.  
  
2.  Щелкните правой кнопкой мыши точку останова и выберите пункт **Условие**.  
  
3.  В диалоговом окне **Условие для точек останова** установите флажок **Условие**.  Подробнее см. раздел [Улучшенные точки останова](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression).  
  
4.  Введите в текстовое поле выражение, например `Var==3`, где `Var` представляет собой имя параметра, который содержит неправильное значение, а `3` — это неправильное значение, переданное параметру.  
  
5.  Установите переключатель в положение **верно** и нажмите кнопку **ОК**.  
  
6.  Запустите программу повторно.  Точка останова заставит программу прервать выполнение на начале функции, когда параметр `Var` получит значение `3`.  
  
7.  Затем в окне "Стек вызовов" можно найти вызывающую функцию, чтобы перейти к ее исходному коду.  Дополнительные сведения см. в разделе [Практическое руководство. Использование окна стека вызова](../debugger/how-to-use-the-call-stack-window.md).  
  
## См. также  
 [Вопросы и ответы по отладке машинного кода](../debugger/debugging-native-code-faqs.md)   
 [Breakpoints](http://msdn.microsoft.com/ru-ru/fe4eedc1-71aa-4928-962f-0912c334d583)   
 [Отладка машинного кода](../debugger/debugging-native-code.md)