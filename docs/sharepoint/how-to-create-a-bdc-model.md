---
title: "Практическое руководство. Создание модели подключения к бизнес-данным"
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
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "подключение к бизнес-данным [разработка приложений SharePoint в Visual Studio], создание модели"
  - "служба подключения к бизнес-данным [разработка приложений SharePoint в Visual Studio], создание модели"
ms.assetid: e8b888d4-a531-4d13-9ebf-efbbd33eebc6
caps.latest.revision: 15
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 14
---
# Практическое руководство. Создание модели подключения к бизнес-данным
  Можно создать модель подключения к бизнес\-данным \(BDC\) с помощью шаблона для данного типа элементов и последующим добавлением модели в любой проект SharePoint.  Для получения дополнительной информации см. [Создание модели подключения к бизнес-данным](../sharepoint/creating-a-business-data-connectivity-model.md).  Дополнительные сведения о способах проектирования модели см. в разделе [Проектирование модели подключения к бизнес-данным](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
### Создание проекта BDC  
  
1.  В строке меню **Файл** выберите пункты **Создать**, **Проект**.  
  
    > [!NOTE]  
    >  Если интерфейс IDE настроен для использования параметров разработки Visual Basic, выберите **Файл**, **Создать проект**.  
  
     Откроется диалоговое окно **Новый проект**.  
  
2.  В узле **Visual Basic** или **Visual C\#** выберите **Office\/SharePoint**, **Решения SharePoint**.  
  
3.  В панели **Шаблоны** выберите элемент **SharePoint 2013 — пустой проект**, а затем нажмите кнопку **ОК**.  
  
     Появится окно **Мастер настройки SharePoint**.  
  
4.  На странице **Укажите сайт и уровень безопасности для отладки** укажите URL\-адрес сайта SharePoint на локальном компьютере, выберите переключатель **Развернуть как решение фермы**, а затем нажмите кнопку **Готово**.  
  
     Вы протестируете модель на указанном вами сайте SharePoint.  
  
    > [!IMPORTANT]  
    >  Следует развертывать проект в решение фермы, поскольку модели подключения к бизнес\-данным поддерживают только решения фермы.  
  
     Создается пустой проект SharePoint.  
  
5.  В строке меню выберите **Проект**, **Добавить новый элемент**.  
  
6.  В диалоговом окне **Добавление нового элемента** выберите узел **Office\/SharePoint** .  
  
7.  В списке шаблонов SharePoint выберите **Модель подключения к бизнес\-данным \(только для решения фермы\)**.  
  
8.  В поле **Имя** введите имя для модели BDC и нажмите кнопку **Добавить**.  
  
     Элемент **Модель подключения к бизнес\-данным** добавляется в проект.  По умолчанию модель отображается в конструкторе BDC.  Для получения дополнительной информации см. [Создание модели подключения к бизнес-данным](../sharepoint/creating-a-business-data-connectivity-model.md).  
  
## См. также  
 [Создание модели подключения к бизнес-данным](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [Практическое руководство. Добавление существующего файла модели подключения к бизнес-данным в проект SharePoint](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)   
 [Практическое руководство. Использование файла ресурсов для задания локализованных имен, свойств и разрешений](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)   
 [Практическое руководство. Добавление пользовательской сборки в функцию BDC](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)   
 [Интеграция бизнес-данных в SharePoint](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
  