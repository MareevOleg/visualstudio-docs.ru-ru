---
title: "Приоритет проекта | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "При открытии элементов проектов [Visual Studio SDK]"
ms.assetid: 9f707592-2fb6-4f75-9269-f6d4700a998e
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# Приоритет проекта
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Элемент проекта обычно является членом только одного проекта в решении.  Следовательно, интегрированная среда разработки может легко определить используется, проект открыть элемент.  Однако если элемент является членом нескольких проектов, интегрированная среда разработки используется схема приоритета определить лучший проект для открытия элемента.  
  
 В следующем списке перечислены схемы приоритета проекта:  
  
-   Интегрированная среда разработки вызывает <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject2.IsDocumentInProject%2A> метод для каждого проекта в решении определить, является ли документ элемент проекта.  
  
-   Если документ является членом проекта, проект с приоритетом отвечает, проект будет присвоено в соответствии с его обработке этого документа.  Например, проект языка с высоким приоритетом отвечает для своих исходных файлов языка, но отвечает с более низким приоритетом, нераспознанного типа файла, который не используется как часть процесса построения.  
  
-   Проекты, которые предоставляют конструкторы, редакторы пользовательских проектов или документа также получают самый важный.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> перечисление предоставляет значения приоритета документа.  
  
-   Получает проект, который определяется наивысшим приоритетом контекст для открытия документа.  Если project 2 возвращают одинаковые значения приоритета активно проект предпочтен.  Если проект в решении не отвечает, что он может открыть документ, интегрированная среда разработки помещает документ в проекте " прочие файлы ".  Дополнительные сведения см. в разделе [Проект прочих файлов](../../extensibility/internals/miscellaneous-files-project.md).  
  
## См. также  
 [Проект прочих файлов](../../extensibility/internals/miscellaneous-files-project.md)   
 [Практическое руководство: открытие редакторов для открытых документов](../../extensibility/how-to-open-editors-for-open-documents.md)   
 [Добавление проекта и шаблоны элементов проекта](../../extensibility/internals/adding-project-and-project-item-templates.md)