---
title: Задача ResourcesGenerator | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- embedding resources into a .resources file [WPF MSBuild]
- ResourcesGenerator task [WPF MSBuild]
- ResourcesGenerator task [WPF MSBuild], parameters
ms.assetid: e782bbac-9ee6-472b-8171-3ee008c77b4e
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4d2d470c91d6303976e5afcbffc7f4eff968ea04
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49173307"
---
# <a name="resourcesgenerator-task"></a>Задача ResourcesGenerator
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Задача <xref:Microsoft.Build.Tasks.Windows.ResourcesGenerator> внедряет один или несколько ресурсов (файлов JPG, ICO, BMP, [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] в двоичном формате и других) в RESOURCES-файл.  
  
## <a name="task-parameters"></a>Параметры задачи  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`OutputPath`|Обязательный параметр **string**.<br /><br /> Определяет абсолютный путь выходного каталога. Если путь не является абсолютным, он интерпретируется относительно корневого каталога проекта.|  
|`OutputResourcesFile`|Обязательный параметр вывода **ITaskItem[]**.<br /><br /> Определяет путь и имя для созданного RESOURCES-файла. Если путь не является абсолютным, RESOURCES-файл интерпретируется относительно корневого каталога проекта.|  
|`ResourcesFiles`|Обязательный параметр **ITaskItem[]**.<br /><br /> Определяет один или несколько ресурсов для внедрения в создаваемый RESOURCES-файл.|  
  
## <a name="example"></a>Пример  
 Следующий пример создает RESOURCES-файл с одним BMP-ресурсом. BMP-ресурс создается в каталоге, который интерпретируется относительно корневого каталога проекта.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.ResourcesGenerator"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="ResourcesGeneratorTask">  
    <ResourcesGenerator  
      ResourceFiles="Resource1.bmp"  
      OutputPath="myresources"  
      OutputResourcesFile="myresources\my.resources" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>См. также  
 [Справочные сведения о WPF для MSBuild](../msbuild/wpf-msbuild-reference.md)   
 [Справочные сведения о задачах](../msbuild/wpf-msbuild-task-reference.md)   
 [Справочные сведения о MSBuild](../msbuild/msbuild-reference.md)   
 [Справочные сведения о задачах](../msbuild/msbuild-task-reference.md)   
 [Построение приложения WPF](http://msdn.microsoft.com/library/a58696fd-bdad-4b55-9759-136dfdf8b91c)



