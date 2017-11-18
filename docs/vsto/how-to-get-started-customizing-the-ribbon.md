---
title: "Практическое руководство. Работа с настройкой ленты"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "настраиваемая лента, добавление ленты в проект"
  - "настройка ленты, добавление ленты в проект"
  - "лента [разработка решений Office в Visual Studio], добавление"
  - "лента [разработка решений Office в Visual Studio], настройка"
ms.assetid: 9eb6b8b3-1842-4cb3-8229-273ce35c64fb
caps.latest.revision: 22
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 21
---
# Практическое руководство. Работа с настройкой ленты
  Чтобы настроить ленту приложения Microsoft Office, добавьте функцию **Лента \(визуальный конструктор\)** или элемент **Лента \(XML\)** в проект Office.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### Для того чтобы добавить ленту в проект, выполните следующее.  
  
1.  В меню **Проект** выберите команду **Добавить новый элемент**.  
  
2.  В диалоговом окне **Добавить новый элемент** выберите функцию **Лента \(визуальный конструктор\)** или **Лента \(XML\)**.  Дополнительные сведения об этих шаблонах см. в разделе [Обзор ленты](../vsto/ribbon-overview.md).  
  
3.  В окне **Имя** введите имя элемента ленты.  
  
     Имена не должны содержать следующие символы:  
  
    -   Решетка \(\#\)  
  
    -   Процент \(%\)  
  
    -   Амперсанд \(&\)  
  
    -   Звездочка \(\*\)  
  
    -   Вертикальная черта \(|\)  
  
    -   обратная косая черта \(\\\).  
  
    -   Двоеточие \(:\)  
  
    -   Двойные кавычки \("\)  
  
    -   Знак уменьшения \(\<\)  
  
    -   Знак увеличения \(\>\)  
  
    -   Вопросительный знак \(?\)  
  
    -   Косая черта \(\/\)  
  
    -   Пробелы в конце и в начале текстовой строки \(' '\)  
  
    -   Зарезервированные слова Windows и DOS, такие как "nul", "aux", "con", "com1", "lpt1" и другие.  
  
4.  Нажмите кнопку **ОК**.  
  
 Элемент ленты отобразится в разделе **Обозреватель решений**.  Дополнительные сведения о следующих этапах см. в разделе [Обзор ленты](../vsto/ribbon-overview.md).  
  
## См. также  
 [Доступ к ленте во время выполнения](../vsto/accessing-the-ribbon-at-run-time.md)   
 [Конструктор лент](../vsto/ribbon-designer.md)   
 [XML-ленты](../vsto/ribbon-xml.md)   
 [Пошаговое руководство. Создание настраиваемой вкладки с помощью конструктора лент](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [Пошаговое руководство. Создание настраиваемой вкладки с помощью XML-лент](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)  
  
  