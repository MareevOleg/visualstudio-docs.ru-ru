---
title: "MSBuild: обзор настройки для различных версий | Документация Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eecbcd65-9fbc-4307-a321-46d3c3b79b12
caps.latest.revision: "10"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 573e88f1ebc3777f0ce6a6bfa048a9784d8f6488
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
---
# <a name="msbuild-multitargeting-overview"></a>MSBuild: обзор настройки для различных версий
С помощью MSBuild можно компилировать приложение для его запуска на любой из нескольких версий платформы .NET Framework, а также на любой из нескольких системных платформ. Например, можно компилировать приложение для запуска в .NET Framework 2.0 на 32-разрядной платформе, а также компилировать то же приложение для запуска в .NET Framework 4.5 на 64-разрядной платформе.  
  
> [!IMPORTANT]
>  Несмотря на название "Настройка для различных версий" проект можно назначить одновременно только одной исполняющей среде и только одной платформе.  
  
 Ниже перечислены некоторые возможности MSBuild для различных версий.  
  
-   Можно разрабатывать приложения, которые предназначены для более ранних версий платформы .NET Framework, например версий 2.0, 3.5 или 4.  
  
-   Можно ориентироваться на платформы, отличные от .NET Framework, например на платформу Silverlight.  
  
-   Можно ориентироваться на *профиль платформы*, который представляет собой предопределенное подмножество целевой платформы.  
  
-   После появления пакета обновления для текущей версии .NET Framework можно выбрать его в качестве целевой платформы.  
  
-   Поддержка различных версий гарантирует, что приложение использует только те функциональные возможности, которые доступны в целевой версии .NET Framework и платформы.  
  
## <a name="target-framework-and-platform"></a>Целевая исполняющая среда и целевая платформа  
 *Целевая исполняющая среда* — это версия платформы .NET Framework, для запуска на которой разработан проект, а *целевая платформа* — это системная платформа, для которой предназначен проект.  Например, приложение .NET Framework 2.0 можно настроить для выполнения на 32-разрядной платформе, которая совместима с семейством процессоров 802x86 ("x86"). Сочетание требуемой версии .NET Framework и целевой платформы называется *целевым контекстом*. Дополнительные сведения см. в статье [Target Framework and Target Platform](../msbuild/msbuild-target-framework-and-target-platform.md) (Целевая рабочая среда и целевая платформа).  
  
## <a name="toolset-toolsversion"></a>Набор инструментов (ToolsVersion)  
 Набор инструментов включает средства, задачи и целевые объекты, используемые для создания приложения. В набор инструментов входят компиляторы, такие как csc.exe и vbc.exe, общий файл целей построения (microsoft.common.targets) и общий файл задач (microsoft.common.tasks). Набор инструментов 4.5 можно использовать для платформы .NET Framework версий 2.0, 3.0, 3.5, 4 и 4.5. При этом набор инструментов 2.0 можно использовать только для платформы .NET Framework версии 2.0. Дополнительные сведения см. в разделе [Набор инструментов](../msbuild/msbuild-toolset-toolsversion.md).  
  
## <a name="reference-assemblies"></a>Ссылочные сборки  
 Ссылочные сборки, заданные в наборе инструментов, позволяют проектировать и создавать приложения. Эти ссылочные сборки не только позволяют создать определенную целевую сборку, но также ограничивают набор компонентов и функций в Visual Studio IDE теми, которые совместимы с целевым объектом. Дополнительные сведения см. в разделе [Разрешение сборок во время разработки](../msbuild/resolving-assemblies-at-design-time.md).  
  
## <a name="configuring-targets-and-tasks"></a>Настройка целевых платформ и задач  
 Целевые объекты и задачи MSBuild можно настроить на выполнение вне процесса с помощью MSBuild, чтобы можно было определять целевые контексты, которые значительно отличаются от того, в котором идет выполнение.  Например, на компьютере с 64-разрядной платформой и .NET Framework 4.5 можно создать приложение .NET Framework 2.0, предназначенное для 32-разрядной платформы. Дополнительные сведения см. в разделе [Настройка целевых платформ и задач](../msbuild/configuring-targets-and-tasks.md).  
  
## <a name="troubleshooting"></a>Устранение неполадок  
 При попытке сослаться на сборку, которая не является частью целевого контекста, могут возникнуть ошибки. Дополнительные сведения об этих ошибках и способах их устранения см. в разделе [Устранение неполадок, связанных с настройкой для определенных версий платформы .NET Framework](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md).