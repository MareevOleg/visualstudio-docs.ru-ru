---
title: Задача ZipDirectory | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ZipDirectory
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ZipDirectory task [MSBuild]
- MSBuild, ZipDirectory task
ms.assetid: 916bb2e3-3017-4828-ae27-c0b5c99bbb48
caps.latest.revision: 16
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bc46e664bd117827be3534c7aa81978d7cc03d5e
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "39231305"
---
# <a name="zipdirectory-task"></a>Задача ZipDirectory
Создает *ZIP-архив* из содержимого каталога.

>[!NOTE]
>Задача `ZipDirectory` доступна только в MSBuild 15.8 и более поздних версий.
  
## <a name="parameters"></a>Параметры  
 В следующей таблице приводятся параметры задачи `ZipDirectory` .  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|`DestinationFile`|Обязательный параметр <xref:Microsoft.Build.Framework.ITaskItem><br /><br /> Полный путь к создаваемому *ZIP-файлу*.|
|`Overwrite`|Необязательный параметр `Boolean` .<br /><br /> Если задано значение `true`, пропускает целевой файл, который будет перезаписан при его наличии. По умолчанию — `false`.|
|`SourceDirectory`|Обязательный параметр <xref:Microsoft.Build.Framework.ITaskItem> .<br /><br /> Указывает каталог, из которого создается *ZIP-архив*.|
  
## <a name="remarks"></a>Примечания  
 Помимо перечисленных выше параметров, эта задача наследует параметры от класса <xref:Microsoft.Build.Tasks.TaskExtension>, который, в свою очередь, наследует от класса <xref:Microsoft.Build.Utilities.Task>. Список этих дополнительных параметров и их описания см. в статье [Базовый класс TaskExtension](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Пример  
 В следующем примере создается *ZIP-архив* из каталога выходных данных после сборки проекта.
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <PropertyGroup>
      <ZipOutputPath>$(MSBuildProjectDirectory)</ZipOutputPath>
    </PropertyGroup>

    <Target Name="ZipOutputPath" AfterTargets="Build">
        <ZipDirectory
            SourceDirectory="$(OutputPath)"
            DestinationFile="$(MSBuildProjectDirectory)\output.zip">
        />
    </Target>

</Project>
```
  
## <a name="see-also"></a>См. также  
 [Задачи](../msbuild/msbuild-tasks.md)   
 [Справочные сведения о задачах](../msbuild/msbuild-task-reference.md)