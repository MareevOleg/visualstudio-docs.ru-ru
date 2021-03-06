---
title: Справочник по схемам манифеста шаблонов Visual Studio | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: bc7d0a81-0df5-41a9-a912-1b30e5da1d13
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 38581d7c7dd788fef481676283fdc96c8abc96ba
ms.sourcegitcommit: 56ae5032d99d948aae0548ae318ca2bae97ea962
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39586317"
---
# <a name="visual-studio-template-manifest-schema-reference"></a>Справочник по схемам манифеста шаблона Visual Studio
Эта схема описывает формат манифеста шаблона Visual Studio (*.vstman*) файлов, созданных для шаблонов проекта или элемента Visual Studio. Кроме того, схема описывает расположение и другие важные сведения о шаблоне.  
  
 : Существует отдельный элемент и каталоги шаблона проекта, манифест никогда не должен иметь набор шаблонов проектов и элементов.  
  
> [!IMPORTANT]
>  Этот манифест доступна, начиная с Visual Studio 2017.  
  
## <a name="vstemplatemanifest-element"></a>Элемент VSTemplateManifest  
 Корневой элемент манифеста.  
  
### <a name="attributes"></a>Атрибуты  
  
-   **Версия**: строка, представляющая версию шаблона манифеста. Обязательно.  
  
-   **Языковой стандарт**: строка, представляющая языкового стандарта или национальных настроек шаблона манифеста. Значение языкового стандарта, применяется ко всем шаблонам. Необходимо использовать отдельный манифест для каждого языкового стандарта. Необязательный.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
-   **VSTemplateContainer** необязательно.  
  
-   **VSTemplateDir** необязательно.  
  
### <a name="parent-element"></a>Родительский элемент  
 Отсутствует.  
  
## <a name="vstemplatecontainer"></a>VSTemplateContainer  
 Контейнер шаблона манифеста элементов. Манифест содержит один контейнер шаблона для каждого шаблона, который она определяет.  
  
### <a name="attributes"></a>Атрибуты  
 **VSTemplateType**: строковое значение, указывающее тип шаблона (`"Project"`, `"Item"`, или `"ProjectGroup"`). Обязательно  
  
### <a name="child-elements"></a>Дочерние элементы  
  
-   **RelativePathOnDisk**: относительный путь к файлу шаблона на диске. Это расположение также определяет положение шаблона в дереве шаблон, показанный на **новый проект** или **новый элемент** диалоговое окно. Для шаблоны, развертываемые как каталог и отдельных файлов этот путь ссылается на каталог, содержащий файлы шаблонов. Для развернутых шаблонов в качестве *ZIP-файл* файл, этот путь должен быть путь к *ZIP-файл* файл.  
  
-   ** VSTemplateHeader: A [TemplateData](../extensibility/templatedata-element-visual-studio-templates.md) элемент, описывающий заголовок.  
  
### <a name="parent-element"></a>Родительский элемент  
 **VSTemplateManifest**  
  
## <a name="vstemplatedir"></a>VSTemplateDir  
 Указывает каталог, где находится шаблон. Манифест может содержать несколько **VSTemplateDir** записи для предоставления локализованного имени и сортировки, упорядочение для каталогов, управлять их внешним видом в дерево категорий шаблона.  
  
 Из-за структуры **VSTemplateDir** отображаются записи только в заданные манифесты не языкового стандарта.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
-   **RelativePath**: путь к шаблону. Может существовать только одну запись для каждого пути, поэтому первый из них будет предлагаться по умолчанию для всех манифестах.  
  
-   **LocalizedName**: A **NameDescriptionIcon** элемент, который задает локализованное имя. Необязательный.  
  
-   **SortOrder**: строка, указывающая порядок сортировки. Необязательный.  
  
-   **ParentFolderOverrideName**: переопределенное имя родительской папки. Необязательный. Этот элемент имеет **имя** атрибута, который является строковое значение, указывающее имя.  
  
### <a name="parent-element"></a>Родительский элемент  
 **VSTemplateManifest**  
  
## <a name="namedescriptionicon"></a>NameDescriptionIcon  
 Указывает имя и описание, например для локализованных шаблонов. См. в разделе **LocalizedName** выше.  
  
### <a name="attributes"></a>Атрибуты  
  
-   **Пакет**: строковое значение, указывающее пакета. Необязательный.  
  
-   **Идентификатор**: строковое значение, указывающее идентификатор. Необязательный.  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-element"></a>Родительский элемент  
 **LocalizedName**  
  
## <a name="examples"></a>Примеры  
 Следующий код является примером шаблона проекта *.vstman* файла.  
  
```xml  
<VSTemplateManifest Version="1.0" Locale="1033" xmlns="http://schemas.microsoft.com/developer/vstemplatemanifest/2015">  
  <VSTemplateContainer TemplateType="Project">  
    <RelativePathOnDisk>CSharp\1033\TestProjectTemplate</RelativePathOnDisk>  
    <TemplateFileName>TestProjectTemplate.vstemplate</TemplateFileName>  
    <VSTemplateHeader>  
      <TemplateData xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
        <Name>TestProjectTemplate</Name>  
        <Description>TestProjectTemplate</Description>  
        <Icon>TestProjectTemplate.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>  
        <SortOrder>1000</SortOrder>  
        <TemplateID>aac0aeea-7883-4003-992f-937d53d70ab1</TemplateID>  
        <CreateNewFolder>true</CreateNewFolder>  
        <DefaultName>TestProjectTemplate</DefaultName>  
        <ProvideDefaultName>true</ProvideDefaultName>  
      </TemplateData>  
    </VSTemplateHeader>  
  </VSTemplateContainer>  
</VSTemplateManifest>  
  
```  
  
 Следующий код является примером шаблона элемента *.vstman* файла.  
  
```xml  
VSTemplateManifest Version="1.0" Locale="1033" xmlns="http://schemas.microsoft.com/developer/vstemplatemanifest/2015">  
  <VSTemplateContainer TemplateType="Item">  
    <RelativePathOnDisk>CSharp\1033\ItemTemplate1</RelativePathOnDisk>  
    <TemplateFileName>ItemTemplate1.vstemplate</TemplateFileName>  
    <VSTemplateHeader>  
      <TemplateData xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
        <Name>ItemTemplate1</Name>  
        <Description>ItemTemplate1</Description>  
        <Icon>ItemTemplate1.ico</Icon>  
        <TemplateID>bfeadf8e-a251-4109-b605-516b88e38c8d</TemplateID>  
        <ProjectType>CSharp</ProjectType>  
        <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>  
        <NumberOfParentCategoriesToRollUp>1</NumberOfParentCategoriesToRollUp>  
        <DefaultName>Class.cs</DefaultName>  
      </TemplateData>  
    </VSTemplateHeader>  
  </VSTemplateContainer>  
</VSTemplateManifest>  
  
```