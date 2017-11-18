---
title: "Как создать консольное приложение рабочего процесса | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 51a2eea7-921c-49f1-b358-68afc27f1ee9
caps.latest.revision: 16
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Как создать консольное приложение рабочего процесса
Маркер [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] позволяет создавать рабочие процессы для выполнения системных или пользовательских процессов.Маркер [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] позволяет создать область конструктора для создания таких рабочих процессов.[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] позволяет создавать рабочие процессы в среде [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], а также интегрируется в другие приложения, где размещается конструктор.  
  
 В этом разделе описывается использование [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] в среде [!INCLUDE[vs2010](../modeling/includes/vs2010_md.md)] для создания рабочего процесса в консольном приложении.  
  
### Создание приложения командной строки рабочего процесса  
  
1.  Запустите среду [!INCLUDE[vs2010](../modeling/includes/vs2010_md.md)].  
  
2.  В меню **Файл** укажите пункт **Создать** и выберите пункт **Проект**.  
  
     Откроется диалоговое окно **Новый проект**.  
  
3.  В области **Установленные шаблоны** выберите категорию **Рабочий процесс** из группы проектов **Visual C\#** или **Visual Basic** \(в зависимости от языка программирования\).  
  
4.  В средней области выберите **Приложение командной строки рабочего процесса**.  
  
5.  В поле **Имя** введите описательное имя проекта, чтобы облегчить его определение.  
  
6.  В поле **Расположение** введите путь к папке, где будет сохранен проект, или нажмите кнопку **Обзор**, чтобы перейти в эту папку.  
  
7.  В поле **Решение** введите имя нового решения.Нажмите кнопку **ОК**, чтобы создать приложение.  
  
    > [!NOTE]
    >  Чтобы добавить консольное приложение рабочего процесса в существующее решение, откройте это решение в среде [!INCLUDE[vs2010](../modeling/includes/vs2010_md.md)], щелкните правой кнопкой мыши решение в окне **обозревателя решений**, выберите команду **Добавить** и выберите пункт **Новый проект...**. Откроется диалоговое окно **Создание проекта**.Продолжайте действия, описанные ранее в этой процедуре.  
  
8.  Этот шаблон проекта создает определение рабочего процесса XAML, а также определение приложения командной строки в исходном коде.Маркер [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] открывает и отображает полотно для созданного рабочего процесса.  
  
9. Чтобы составить рабочий процесс, перетащите действия или другие элементы рабочего процесса из **области элементов** в рабочий процесс в области конструктора.  
  
## См. также  
 [Создание проекта рабочего процесса](../workflow-designer/creating-a-workflow-project.md)