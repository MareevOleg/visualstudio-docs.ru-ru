---
title: 'Практическое: Добавление пункта контекстного меню для типа элемента проекта SharePoint пользовательских | Документация Майкрософт'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint project items, defining your own types
- project items [SharePoint development in Visual Studio], defining your own types
- SharePoint development in Visual Studio, defining new project item types
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 580839936cfa42b4e76999809cd8917f3eb4f041
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755506"
---
# <a name="how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type"></a>Практическое: Добавление пункта контекстного меню в пользовательский тип элемента проекта SharePoint
  При определении настраиваемого типа элемента проекта SharePoint, можно добавить пункта контекстного меню к элементу проекта. Этот пункт меню отображается, когда пользователь щелкает правой кнопкой мыши элемент проекта в **обозревателе решений**.  
  
 Следующие шаги предполагают, что уже было определено собственный тип элемента проекта SharePoint. Дополнительные сведения см. в разделе [как: определить тип элемента проекта SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md).  
  
### <a name="to-add-a-shortcut-menu-item-to-a-custom-project-item-type"></a>Добавление пункта контекстного меню для пользовательского типа элемента проекта  
  
1.  В <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> метод вашей <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> реализации, дескриптор <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> событие *projectItemTypeDefinition* параметра.  
  
2.  В обработчике событий для <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> событий, добавьте новый <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> объект <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.ViewMenuItems%2A> или <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.AddMenuItems%2A> коллекцию параметра аргументов события.  
  
3.  В <xref:Microsoft.VisualStudio.SharePoint.IMenuItem.Click> обработчик событий для нового <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> объекта, выполнять задачи, которую требуется выполнить при выборе пункта контекстного меню.  
  
## <a name="example"></a>Пример  
 В следующем примере кода демонстрируется добавление пункта контекстного меню для пользовательского типа элемента проекта. Когда пользователь открывает контекстное меню с элементом проекта в **обозревателе решений** и выбирает **написать сообщение в окно вывода** пункта меню, Visual Studio отображает сообщение в **выходных данных**  окно.  
  
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#4](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemtypemenu.cs#4)]
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#4](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemtypemenu.vb#4)]  
  
 В этом примере используется служба проекта SharePoint для записи сообщения в **вывода** окна. Дополнительные сведения см. в разделе [использование службы проектов SharePoint](../sharepoint/using-the-sharepoint-project-service.md).  
  
## <a name="compile-the-code"></a>Компиляция кода  
 В этом примере требуется проект библиотеки классов с помощью ссылки на следующие сборки:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploy-the-project-item"></a>Развернуть элемент проекта  
 Чтобы другие разработчики могли использовать созданный элемент проекта, создайте шаблон проекта или шаблона элемента проекта. Дополнительные сведения см. в разделе [создание элементов, шаблоны и шаблоны проектов для элементов проектов SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
 Чтобы развернуть элемент проекта, создайте [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] пакет расширения (VSIX) для сборки, шаблон и другие файлы, которые вы хотите распространять вместе с элементом проекта. Дополнительные сведения см. в разделе [развертывания расширений для инструментов SharePoint в Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>См. также
 [Как: определить тип элемента проекта SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)   
 [Практическое: Добавление свойства пользовательского типа элемента проекта SharePoint](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)   
 [Определение пользовательских типов элементов проектов SharePoint](../sharepoint/defining-custom-sharepoint-project-item-types.md)  
  
 
