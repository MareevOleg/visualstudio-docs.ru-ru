---
title: Добавление элементов, чтобы добавить новый элемент диалоговым окнам | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Add New Item dialog box, adding items
ms.assetid: 2f70863b-425b-4e65-86b4-d6a898e29dc7
caps.latest.revision: 19
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ca9ae7d9e4f0ffc031d2dc8db3e940c9b844c57e
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51778557"
---
# <a name="adding-items-to-the-add-new-item-dialog-boxes"></a>Добавление элементов в диалоговые окна "Добавить новый элемент"
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Процесс добавления элементов к **Добавление нового элемента** запускает диалоговое окно с разделами реестра. Как показано в следующем разделе реестра, в разделе AddItemTemplates содержит путь и имя каталога, в какие элементы доступны в **Добавление нового элемента** помещаются диалоговое окно.  
  
> [!NOTE]
>  Следующий сегмент кода сразу таблицы содержит дополнительные сведения о параметре реестра.  
  
 Этот раздел находится в разделе [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0Exp\Projects].  
  
 Первый идентификатор GUID является CLSID для проектов этого типа; второй идентификатор GUID указывает тип зарегистрированного проекта для шаблонов добавить элементы.  
  
 \\\1 \AddItemTemplates\TemplateDirs\ {ACEF4EB2-57CF-11D2-96F4-000000000000} {C061DB26-5833-11D2-96F5-000000000000}  
  
 @="#6"  
  
 «TemplatesDir «=»\<путь установки Visual Studio SDK\\\VSIntegration\\\SomeFolder\\\SomePackage\\\SomeProject\\\SomeProjectItems»  
  
 «SortPriority» = dword:00000064  
  
|name|Тип|Данные (RGS-файл)|Описание:|  
|----------|----------|-----------------------------|-----------------|  
|@ (По умолчанию)|REG_SZ|#% IDS_ADDITEM_TEMPLATES_ENTRY %|Идентификатор ресурса для **Добавление элемента** шаблонов.|  
|Val TemplatesDir|REG_SZ|%TEMPLATE_PATH%\ SomeProjectItems|Путь проекта элементов, отображаемых в диалоговом окне для **Добавление нового элемента** мастера.|  
|Val SortPriority|REG_DWORD|100 ([!INCLUDE[vcprx64](../../includes/vcprx64-md.md)])|Определяет порядок сортировки в узле дерева файлов, отображаемых в **Добавление нового элемента** диалоговое окно.|  
  
> [!NOTE]
>  Идентификаторы GUID для типов проектов Visual C# и Visual Basic, следующим образом:[!INCLUDE[csprcs](../../includes/csprcs-md.md)]: {FAE04EC0-301F-11D3-BF4B-00C04F79EFBC}[!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]: {F184B08F-C81C-45F6-A57F-5ABD9991F28F}  
  
 Каталог, указанные для TemplateDirs, которая является % TEMPLATE_PATH%\SomeProjectItems, — это узел слева от **Добавление нового элемента** дерева поле диалогового окна. Дополнительные элементы в дереве основаны на подкаталог из этого корневого каталога. Файлы, доступные для добавления в проект — это элементы, в правой части **Добавление нового элемента** диалоговое окно.  
  
 Как правило эта папка будет содержать файлы шаблонов для проекта, например шаблон HTML или CPP-файл и любой VSZ-файлов для запуска мастера. Чтобы контролировать, как отображаются элементы, можно также включить файлов VSDir для локализации имен папок и значки. Локализованная строка — это заголовок, который отображается в диалоговом окне, которое представляет этот узел в дереве диалоговое окно Добавление нового элемента.  
  
 Тем не менее у вас есть все, что в один VSDir-файл. Может иметь один VSDir-файл для каждого элемента в каталоге. Дополнительные сведения см. в разделе [мастер (. Файл VSZ)](../../extensibility/internals/wizard-dot-vsz-file.md) и [Описание каталога шаблона (. Файлы VSDir)](../../extensibility/internals/template-directory-description-dot-vsdir-files.md).  
  
> [!NOTE]
>  Файлов VSDir в каталогах шаблона являются необязательными. Если вам нужно просто поместить элемент проекта в каталоге и отобразит в **Добавление нового элемента** диалоговом окне можно поместить этот файл в каталог шаблонов, указанных в инструкции TemplatesDir. Затем файл будет отображаться в правой части **Добавление нового элемента** диалоговое окно для этого проекта. Тем не менее если вы хотите отобразить локализованные названия для файла или значок, необходимо включить по крайней мере один VSDir-файл в каталог шаблонов.  
  
## <a name="grouping-project-items"></a>Группирование элементов проекта  
 Если вы хотите содержат группы шаблонов в папках, в **Добавление нового элемента** дерева поле диалогового окна, необходимо иметь вложенные папки в корневом каталоге шаблона с элементами в них. Когда **Добавление нового элемента** диалоговое окно отображается для пользователей, они будут также представлены вложенные папки и получить возможность выбора из их элементов проекта.  
  
 Приоритет сортировки в сегменте кода определяет, где будет создан этот каталог шаблон в дереве относительно других элементов узла дерева. Для **Добавление нового элемента** » диалогового окна «приоритет сортировки — все, что необходимо включить, чтобы ваши элементы будут отображены в нужное место в диалоговом окне.  
  
 Вы также можете реализовать <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2> интерфейс для фильтрации отображаемых в **Добавление нового элемента** диалоговое окно. Реализовав этот интерфейс, можно выполнить настройку один шаблон каталога на диск, содержащий, например, 50 файлов шаблонов и мастера. Таким образом может иметь различных типов проектов с 20 файлов, которые принадлежат один тип проекта, 30 файлов, принадлежащих к другому типу проекта и все файлы, доступные в общий тип проекта. Таким образом, в зависимости от того, какой проект создается шаблон, можно отобразить другой набор файлов шаблонов.  
  
 Например в проекте Visual Basic, возможно, веб-проекты и проекты клиента. Веб-форм не полезные элементы для добавления в проект клиента, и windows forms не полезные элементы для добавления в проект веб-сервера. Таким образом можно создать один каталог шаблона, содержащий файлы для обоих типов проекта. Затем путем реализации <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>, можно скрыть элементы, которые не должны отображаться на основе типа проекта или параметры проекта в проекте.  
  
## <a name="filtering-project-items"></a>Фильтрация элементов проекта  
 `IVsFilterAddProjectItemDlg2` предоставляет для фильтрации элементов в дереве (слева) и файлы проекта (правая область), одним из следующих способов:  
  
- Локализованные имена (заголовки, отображаемые в диалоговом окне, содержащийся в VSDir-файл), предоставляемые `IVsFilterAddProjectItemDlg`.  
  
- По фактические имена файлов и папок на диске (нелокализованное — VSDir-файл), предоставляемые `IVsFilterAddProjectItemDlg`.  
  
- По категориям, предоставляемые `IVsFilterAddProjectItemDlg2`.  
  
  Чтобы отфильтровать по категории, укажите строку категории для элемента в VSDir-файл, например «Веб-форму» или «Клиент элемент» в Visual Basic. Коду диалогового окна затем извлекает категория классификации из VSDir-файл и передает его вам. Затем можно передать эту информацию для реализации `IVsFilterAddProjectItemDlg2` для фильтрации **Добавление нового элемента** диалоговое окно по категориям. Также позволяет отфильтровать элементы, для веб-страниц или как случаи приложений Win32 клиента. Кроме того, можно определить [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] элементы с пометкой Microsoft Foundation Classes (MFC) или шаблонных элементов library (ATL). При идентификации этих элементов, система проектов можно определить свой собственный классификации, таким образом, чтобы система можно фильтровать по категории и классификации.  
  
  Если вы реализуете эту функцию фильтра, у вас нет сопоставление таблицы всех элементов, которые должны быть скрыты. Кроме того, можно просто классификации в типы элементов и поместить классификации в VSDir-файл или файлы. Затем можно скрыть элементы, которых затрагивает конкретный класс путем реализации интерфейса. Таким образом, чтобы сделать объекты в **Добавление нового элемента** динамическое поле диалогового окна на основе состояния в рамках проекта.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>   
 [Регистрация шаблонов проектов и элементов](../../extensibility/internals/registering-project-and-item-templates.md)   
 [CATID для объектов, которые обычно используются для расширения проектов](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)   
 [Добавление проекта и шаблоны элементов проекта](../../extensibility/internals/adding-project-and-project-item-templates.md)   
 [Описание каталога шаблона (. Файлы VSDir)](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)   
 [Файл мастера (VSZ-файл)](../../extensibility/internals/wizard-dot-vsz-file.md)

