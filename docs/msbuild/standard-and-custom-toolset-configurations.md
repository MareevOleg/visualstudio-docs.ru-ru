---
title: "Стандартные и настраиваемые конфигурации наборов инструментов | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "MSBuild, настраиваемые конфигурации набора инструментов"
  - "MSBuild, msbuild.exe.config"
ms.assetid: 15a048c8-5ad3-448e-b6e9-e3c5d7147ed2
caps.latest.revision: 31
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 31
---
# Стандартные и настраиваемые конфигурации наборов инструментов
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

MSBuild Набор инструментов ссылки задачам, целевые объекты и средства, которые можно использовать для построения проекта приложения.  MSBuild включает стандартное Набор инструментов, но можно также создать пользовательские наборы инструментов.  Дополнительные сведения об определении набора инструментов см. в разделе [Набор инструментов \(ToolsVersion\)](../msbuild/msbuild-toolset-toolsversion.md).  
  
## Стандартные конфигурации наборов инструментов  
 MSBuild 12.0 включает следующие стандартные наборы инструментов:  
  
|ToolsVersion|Путь Набор инструментов \(в соответствии с свойством построения MSBuildToolsPath или MSBuildBinPath\)|  
|------------------|-----------------------------------------------------------------------------------------------------------|  
|2.0|*Windows installation path*\\Microsoft.Net\\Framework\\v2.0.50727\\|  
|3.5|*Windows installation path*\\Microsoft.NET\\Framework\\v3.5\\|  
|4.0|*Windows installation path*\\Microsoft.NET\\Framework\\v4.0.30319\\|  
|12.0|*%ProgramFiles%*\\MSBuild\\12.0\\bin|  
  
 Значение `ToolsVersion` указывает, что Набор инструментов используется проектом, Visual Studio создает.  В [!INCLUDE[vs_dev12](../data-tools/includes/vs_dev12_md.md)] значение по умолчанию «12.0» \(независимо от того, какие версии, определенная в файле проекта\), но можно переопределить, атрибут с помощью ключа **\/toolsversion** в командной строке.  Дополнительные сведения об этом атрибуте и других способах определения `ToolsVersion` см. в разделе [Переопределение параметров ToolsVersion](../msbuild/overriding-toolsversion-settings.md).  
  
 Если значение `ToolsVersion` не указано, версия\>Number\\DefaultToolsVersion HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MSBuild\\\<раздела реестра `ToolsVersion`, которая определяет всегда равен 2.0.  
  
 Следующие разделы реестра определяют пути установки MSBuild.exe.  
  
|Раздел реестра .|Имя ключа|Значение строки раздела реестра|  
|----------------------|---------------|-------------------------------------|  
|\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MSBuild\\ToolsVersions\\2.0\\|MSBuildToolsPath|.NET Framework 2.0 установит путь|  
|\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\ MSBuild\\ToolsVersions\\3.5\\|MSBuildToolsPath|.NET Framework 3.5 установит путь|  
|\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\ MSBuild\\ToolsVersions\\4.0\\|MSBuildToolsPath|.NET Framework 4 установит путь|  
|\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\ MSBuild\\ToolsVersions\\12.0\\|MSBuildToolsPath|MSBuild установит путь|  
  
### Часть наборов инструментов  
 Если раздел реестра в предыдущей таблице есть подраздел, MSBuild используется для указания пути вложенного набора инструментов может переопределить путь в родительском набора инструментов.  В следующем примере подраздела:  
  
 \\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MSBuild\\ToolsVersions\\12.0\\12.0  
  
 Если какие\-либо свойства определяются как в базовом наборе инструментов, так и в выбранном часть Набор инструментов, определения свойств в часть Набор инструментов используются.  Например, набор инструментов MSBuild 4.0 указывает `SDK40ToolsPath` для указания на 7.0A SDK, но набор инструментов 4.0\\11.0 MSBuild определяет одно свойство, чтобы она указывала на 8.0A SDK.  Если `VisualStudioVersion` имеет значение `SDK40ToolsPath`, то указало бы на 7.0A, но, если `VisualStudioVersion` имеет значение 11.0, то вместо этого свойству указало бы на 8.0A.  
  
 Свойство построения `VisualStudioVersion` указывает, будет ли часть Набор инструментов активным.  Например, `VisualStudioVersion` значение «12.0», MSBuild 12.0 вложенного набора инструментов.  Дополнительные сведения см. в разделе [Набор инструментов \(ToolsVersion\)](../msbuild/msbuild-toolset-toolsversion.md) вложенного набора инструментов.  
  
> [!NOTE]
>  Рекомендуется избегать изменить эти параметры.  Однако можно добавлять собственные параметры и задавать параметры уровня \(пользовательские определения для набора инструментов, как показано в следующем разделе.  
  
## Пользовательские определения для набора инструментов  
 Если стандартный набор инструментов не удовлетворяет необходимым требованиям построения, можно создать пользовательский набор инструментов.  Например, если имеется сценарий лаборатории построения, в котором необходимо обладать собственной системы построения для проектов [!INCLUDE[vcprvc](../debugger/includes/vcprvc_md.md)].  С помощью пользовательского набора инструментов, можно присвоить специальные значения атрибуту `ToolsVersion` при создании проектов или выполнения MSBuild.exe.  Таким образом, можно также использовать свойство `$(MSBuildToolsPath)` импортировать файлы с расширением TARGETS из этой папки, а также определять собственные пользовательские свойства набора инструментов, которые можно использовать для любого проекта, использующие этот набор инструментов.  
  
 Определение пользовательского набора инструментов в файле конфигурации для MSBuild.exe \(или для пользовательского инструмента, что узлы обработчик MSBuild, то, что используется\).  Например, файл конфигурации для MSBuild.exe может включать следующее определение набора инструментов при пожелали переопределить реакция на событие по умолчанию ToolsVersion 12.0.  
  
```  
<msbuildToolsets default="12.0">  
   <toolset toolsVersion="12.0">  
      <property name="MSBuildToolsPath"   
        value="C:\SpecialPath" />  
   </toolset>  
</msbuildToolsets>  
```  
  
 `<msbuildToolsets>` необходимо также задать в файле конфигурации следующим образом.  
  
```  
<configSections>  
   <section name="msbuildToolsets"         
       Type="Microsoft.Build.BuildEngine.ToolsetConfigurationSection,   
       Microsoft.Build.Engine, Version=12.0.0.0, Culture=neutral,   
       PublicKeyToken=b03f5f7f11d50a3a"  
   </section>  
</configSections>  
```  
  
> [!NOTE]
>  Чтение быть правильно, `<configSections>` должно быть первым подразделом в разделе `<configuration>`.  
  
 `ToolsetConfigurationSection` пользовательского раздела конфигурации, может использоваться любым узлом MSBuild для пользовательской конфигурации.  Если используется пользовательский набор инструментов, то серверу ничего не нужно делать для инициализации ядра построения, кроме ввода файла конфигурации.  Путем задания записи в реестре можно указать параметры уровня \(наборы инструментов, которые применяются к MSBuild.exe, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] и всем узлам MSBuild.  
  
> [!NOTE]
>  Если в файле конфигурации заданы параметры `ToolsVersion`, которые уже были определены в реестре, 2 определения не добавляются.  Определение в файле конфигурации имеет приоритет, поэтому параметры в реестре для этого `ToolsVersion`.  
  
 Следующие свойства имеют значение `ToolsVersion`, которое используется в проектах.  
  
-   **$ \(MSBuildBinPath\)** установлено в значение `ToolsPath`, которое задается либо в реестре или в файле конфигурации, `ToolsVersion`.  Параметр `$(MSBuildToolsPath)` в реестре или в файле конфигурации указывает расположение основных задач и целевых объектов.  В файле проекта это соответствует свойству $\(MSBuildBinPath\), а также свойству $\(MSBuildToolsPath\).  
  
-   зарезервированное свойство `$(MSBuildToolsPath)`, которое предоставляется свойством MSBuildToolsPath, заданным в файле конфигурации. \(Это свойство заменяет собой `$(MSBuildBinPath)`.  Однако для обеспечения совместимости используется `$(MSBuildBinPath)`\). Пользовательский набор инструментов должен указать `$(MSBuildToolsPath)` или `$(MSBuildBinPath)`, но не оба равны, если они не имеют одно и то же значение.  
  
 Вы можете также добавить в файл конфигурации пользовательские и зависящие от ToolsVersion свойства, используя тот же самый синтаксис, который применяется для добавления свойств MSBuildToolsPath.  Чтобы сделать эти пользовательские свойства доступа к файлу проекта, используйте одно и то же имя, что и имя значения, заданные в файле конфигурации.  Можно задать набор инструментов, но не вложенные наборы инструментов в файле конфигурации.  
  
## См. также  
 [Набор инструментов \(ToolsVersion\)](../msbuild/msbuild-toolset-toolsversion.md)