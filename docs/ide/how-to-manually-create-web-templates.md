---
title: Создание веб-шаблонов
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio templates, Web
- templates [Visual Studio], Web
- Web templates [Visual Studio]
- project templates [Visual Studio], Web
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: cff4fda5113cdbacba2d9389e360707f49ba595b
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/07/2018
ms.locfileid: "53063672"
---
# <a name="how-to-manually-create-web-templates"></a>Как выполнить Создание веб-шаблонов вручную

Создание веб-шаблона отличается от создания других типов шаблонов. Так как шаблоны веб-проектов отображаются в диалоговом окне **Добавить новый веб-сайт**, а элементы веб-проекта классифицируются по языку программирования, файл *VSTEMPLATE* должен указывать, что это веб-шаблон, а также задавать язык программирования.

> [!NOTE]
> Веб-шаблоны должны содержать пустой файл *WEBPROJ*, на который должна быть добавлена ссылка в файле *VSTEMPLATE* в атрибуте `File` элемента `Project`. Для веб-проектов не требуется файл проекта *PROJ*. Но необходимо создать этот файл-заглушку для правильной работы веб-шаблона.

## <a name="to-manually-create-a-web-template"></a>Создание веб-шаблонов вручную

1. Создайте веб-проект.

2. Измените или удалите файлы в проекте или добавьте в него новые файлы.

3. Создайте XML-файл и сохраните его с расширением *VSTEMPLATE* в одном каталоге с проектом. Не добавляйте его в проект в Visual Studio.

4. Измените файл *VSTEMPLATE* с XML-кодом, чтобы предоставить метаданные шаблона проекта. Дополнительные сведения см. в [приведенных ниже примерах](#example).

5. Найдите в файле *VSTEMPLATE* элемент `ProjectType` и задайте `Web` в качестве текстового значения.

6. После элемента `ProjectType` добавьте элемент `ProjectSubType` и задайте язык программирования этого шаблона в качестве текстового значения. Этот язык программирования может принимать одно из следующих значений:

   - CSharp
   - VisualBasic

     Например:

     ```xml
     <TemplateData>
       ...
       <ProjectType>Web</ProjectType>
       <ProjectSubType>CSharp</ProjectSubType>
       ...
     </TemplateData>
     ```

7. Выберите файлы в шаблоне (включая файл *VSTEMPLATE*), щелкните их правой кнопкой мыши и последовательно выберите **Отправить** > **Сжатая ZIP-папка**. Файлы сжимаются в *ZIP*-файл.

8. Поместите *ZIP*-файл шаблона в каталог шаблонов проекта Visual Studio. По умолчанию это каталог *%USERPROFILE%\Documents\Visual Studio \<версия\>\ProjectTemplates*.

## <a name="example"></a>Пример

В следующем примере показан базовый файл *VSTEMPLATE* для шаблона веб-проекта:

```xml
<VSTemplate Version="2.0.0" Type="Project"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>MyWebProjecStarterKit</Name>
        <Description>A simple web template</Description>
        <Icon>icon.ico</Icon>
        <ProjectType>Web</ProjectType>
        <ProjectSubType>CSharp</ProjectSubType>
        <DefaultName>WebSite</DefaultName>
    </TemplateData>
    <TemplateContent>
        <Project File="WebApplication.webproj">
            <ProjectItem>icon.ico</ProjectItem>
            <ProjectItem OpenInEditor="true">Default.aspx</ProjectItem>
            <ProjectItem>Default.aspx.cs</ProjectItem>
        </Project>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>См. также

- [Создание шаблонов проектов и элементов](../ide/creating-project-and-item-templates.md)
- [Справочник по схемам шаблонов Visual Studio (расширяемость)](../extensibility/visual-studio-template-schema-reference.md)
