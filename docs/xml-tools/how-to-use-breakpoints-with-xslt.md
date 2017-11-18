---
title: "Практическое руководство. Использование точек останова в XSLT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bf7bbc2c-71dc-4cac-a6fc-add6b27d92ed
caps.latest.revision: 2
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 2
---
# Практическое руководство. Использование точек останова в XSLT
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Точки останова вы можете задать в таблице стилей XSLT или в исходном XML\-документе.Если задать точку останова на теге, то при выполнении точка останова переходит к следующему оператору, у которого есть сведения исходной строки.  
  
 Дополнительные сведения см. в разделе [Debugging Basics: Breakpoints](http://msdn.microsoft.com/ru-ru/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e).  
  
## Задание точки останова в таблице стилей  
 Точки останова можно задать на открывающих тегах, закрывающих тегах и текстовых узлах таблицы стилей XSLT.Точки останова можно также задать в коде блока скрипта.  
  
#### Задание точки останова в таблице стилей  
  
1.  Откройте таблицу стилей в редакторе XML.  
  
2.  Установите курсор в положение точки останова, щелкните правой кнопкой, укажите пункт **Точка останова**, затем выберите пункт **Вставить точку останова**.  
  
3.  Нажмите кнопку обзора \(**...**\) в поле **Ввод** окна свойств документа.  
  
4.  Выберите исходный XML\-документ и нажмите кнопку **Открыть**.  
  
     Таким образом задается файл исходного документа, используемого в XSLT\-преобразовании.  
  
5.  На панели инструментов редактора XML нажмите кнопку **Отладка XSL**.  
  
## Задание точки останова в исходном XML\-документе  
 В исходном XML\-документе точки останова можно задать на элементах, атрибутах, узле пространства имен, комментариях, инструкции по обработке и текстовых узлах исходного XML\-документа.Невозможно задать точку останова на узле документа или на узле пространства имен, который наследуется от родительского элемента.  
  
#### Задание точки останова в исходном XML\-документе  
  
1.  Откройте XML\-документ в редакторе XML.  
  
2.  Установите курсор в положение точки останова, щелкните правой кнопкой, укажите пункт **Точка останова**, затем выберите пункт **Вставить точку останова**.  
  
3.  Нажмите кнопку обзора \(**...**\) в поле **Таблица стилей** окна свойств документа.  
  
4.  Выберите исходный XML\-документ и нажмите кнопку **Открыть**.  
  
     Таким образом задается файл исходного документа, используемого в XSLT\-преобразовании.  
  
5.  На панели инструментов редактора XML нажмите кнопку **Отладка XSL**.  
  
## См. также  
 [Пошаговое руководство: отладка таблицы стилей XSLT](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md)