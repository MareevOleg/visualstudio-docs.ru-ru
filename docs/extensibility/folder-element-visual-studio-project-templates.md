---
title: Элемент Folder (шаблоны проектов Visual Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#Folder
helpviewer_keywords:
- Folder element [Visual Studio project templates]
ms.assetid: 558e3d41-0db5-4c44-82bb-6bb87892b093
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b4fca64abf91105e0363ecd67ea5244c533996f3
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/03/2018
ms.locfileid: "39497179"
---
# <a name="folder-element-visual-studio-project-templates"></a>Элемент Folder (шаблоны проектов Visual Studio)
Указывает папку, которая будет добавлена в проект.  
  
 \<VSTemplate >  
 \<TemplateContent >  
 \<Project>  
 \<Папка >  
  
## <a name="syntax"></a>Синтаксис  
  
```  
<Folder Name="Project Folder">  
    <Folder> ... </Folder>  
    <ProjectItem> ... </ProjectItem>  
</Folder>  
```  
  
## <a name="attributes-and-elements"></a>Элементы и атрибуты  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`Name`|Обязательный атрибут.<br /><br /> Имя папки проекта.|  
|`TargetFolderName`|Необязательный атрибут.<br /><br /> Задает имя, назначаемое при создании проекта из шаблона. Этот атрибут полезен при использовании замены параметров для создания имени папки или имени папки многоязыковой строки, которая не может использоваться непосредственно в *ZIP-файл* файл.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|`Folder`|Указывает папку, чтобы добавить в проект. `Folder` элементы могут содержать дочерние `Folder` элементов.|  
|[ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md)|Задает файл для добавления в проект.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[Проект](../extensibility/project-element-visual-studio-templates.md)|Необязательный дочерний элемент элемента [TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md).|  
  
## <a name="remarks"></a>Примечания  
 `Folder` является необязательным потомком `Project`.  
  
 Для упорядочения элементов проекта в папках в шаблоне можно использовать любой из следующих методов:  
  
-   Включить папки в шаблоне *ZIP-файл* и добавьте их в проект в *.vstemplate* файл, указав путь к файлу в `ProjectItem` элементы, не имеющий `Folder` элементов. Это рекомендуемый метод. Пример:  
  
     `...`  
  
     `<ProjectItem>\Folder\item.cs</ProjectItem>`  
  
     `<ProjectItem>Form1.cs</ProjectItem>`  
  
     `...`  
  
-   Включить папки в шаблоне *ZIP-файл* и добавьте их в проект в *.vstemplate* файл с `Folder` элементов. Пример:  
  
     `...`  
  
     `<Folder name="Folder">`  
  
     `<ProjectItem>item.cs</ProjectItem>`  
  
     `</Folder>`  
  
     `<ProjectItem>Form1.cs</ProjectItem>`  
  
     `...`  
  
-   Не используйте папки в шаблоне *ZIP-файл* файл, но Добавление папок с помощью `TargetFileName` атрибут `ProjectItem` элемента. Пример:  
  
     `...`  
  
     `<ProjectItem TargetFileName="\Folder\item.cs">item.cs</ProjectItem>`  
  
     `<ProjectItem>Form1.cs</ProjectItem>`  
  
     `...`  
  
## <a name="example"></a>Пример  
 В следующем примере показано метаданные для шаблона проекта [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] приложения Windows.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyTemplate.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <Folder Name="Properties">  
                <ProjectItem>AssemblyInfo.cs</ProjectItem>  
                <ProjectItem>Resources.resx</ProjectItem>  
                <ProjectItem>Resources.Designer.cs</ProjectItem>  
                <ProjectItem>Settings.settings</ProjectItem>  
                <ProjectItem>Settings.Designer.cs</ProjectItem>  
            </Folder>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>См. также  
 [Справочник по схеме для Visual Studio шаблон](../extensibility/visual-studio-template-schema-reference.md)   
 [Создание шаблонов проектов и элементов](../ide/creating-project-and-item-templates.md)   
 [Элемент ProjectItem (шаблоны элементов Visual Studio)](../extensibility/projectitem-element-visual-studio-item-templates.md)