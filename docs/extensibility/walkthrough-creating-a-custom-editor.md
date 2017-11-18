---
title: "Пошаговое руководство: Создание специализированного редактора | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Создание пользовательских - редакторы [Visual Studio SDK]"
ms.assetid: d090abb6-d99f-4083-a3db-cd16bf81ce7d
caps.latest.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 17
---
# Пошаговое руководство: Создание специализированного редактора
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Шаблон проекта VSPackage можно создать простой пользовательский редактор в C\+\+.  Шаблон проекта VSPackage больше не поддерживает проекты C\# или Visual Basic. Для получения дополнительной информации см. [SDK для Visual Studio](../extensibility/visual-studio-sdk.md).  
  
## Обязательные компоненты  
 Для выполнения этого пошагового руководства необходимо установить пакет SDK для Visual Studio. Дополнительные сведения см. в разделе [Установка Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## Шаблон проекта Visual Studio пакета  
 Шаблон проекта Visual Studio пакета можно найти в **Новый проект** диалоговое окно в папке расширения C\+\+  
  
### Создание с помощью шаблона Visual Studio пакета VSPackage  
  
1.  Создание проекта с помощью шаблона пакета Visual Studio.  
  
2.  Выберите **специализированного редактора** и нажмите кнопку **Далее**.**Параметры редактора** \-страница.  
  
3.  Введите имя редактора в **имени редактор** поле. Введите расширение файла, которое вы хотите ассоциироваться с помощью редактора в **расширение файла** поле. Редактор для файлов с этим расширением. Расширение файла, зарегистрированного для Visual Studio не для Windows. Введите имя файла по умолчанию для новых документов, создаваемых с помощью редактора в **имя файла по умолчанию** поле.  
  
4.  Нажмите кнопку **Готово**, чтобы создать VSPackage в указанной папке.  
  
### Чтобы проверить пользовательский редактор  
  
1.  На **файл** наведите указатель мыши на **New** и нажмите кнопку **файл**.  
  
2.  В **Установленные шаблоны** области **новый файл** установите флажок вы только что зарегистрированных введите шаблон файла, то файл.  
  
3.  Щелкните **Откройте** для просмотра и редактирования документа.  
  
     Редактор поддерживает операции вырезания и вставки, поиска и замены и открыть нагрузки.  
  
## См. также  
 [Пакеты VSPackage](../extensibility/internals/vspackages.md)