---
title: "Настройка проекта для вывода | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "конфигурации проектов, выходные данные"
ms.assetid: a4517f73-45af-4745-9d7f-9fddf887b636
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# Настройка проекта для вывода
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Все конфигурации может поддерживать набор процессов построения, производящие выходных элементов, такие как файлы исполняемого файла или ресурса. Эти выходные данные элементы для пользователя и может быть помещен в группы, связывающие связанных типов выходных данных, например исполняемые файлы \(.exe .dll, .lib\) и исходных файлов \(.idl, h\-файлы\).  
  
 Выходные элементы доступны через <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutput2> методы и перечисления с <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumOutputs> методы. При необходимости группы выходных элементов проекта, также требуется реализовать <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputGroup> интерфейса.  
  
 Разработанная реализация конструкция `IVsOutputGroup` позволяет выходов группы в соответствии с использованием проекта. Например библиотеки DLL могут быть сгруппированы с его базы данных программы \(PDB\).  
  
> [!NOTE]
>  PDB\-файл содержит сведения об отладке и создается при указании параметра «Создавать отладочные сведения» при создании .dll или .exe. PDB\-файл обычно создается для отладки только в конфигурации проекта.  
  
 Проект должен возвращать одинаковое количество групп для каждой конфигурации, которые его поддерживают, несмотря на то, что количество выходов, содержащихся в группе зависит от конфигурации для конфигурации. Например, проекта Мэтт DLL может включать mattd.dll и mattd.pdb в конфигурации отладки, но включать только matt.dll конфигурация розничной торговли.  
  
 Группы также имеют те же сведения идентификатора, например каноническое имя, отображаемое имя и сведения о группе, с конфигурацией в рамках проекта. Эта согласованность позволяет развертывания и упаковки продолжить работать, даже если изменения конфигурации.  
  
 Группы могут также иметь основного выходного файла, позволяющий упаковки помещаются ярлыки понятное имя. Любая группа может быть пустым в заданной конфигурации, поэтому вносится никаких предположений о размере группы. Размер \(количество выходов\) каждой группы в любой конфигурации может отличаться от размера другой группы в той же конфигурации. Он также может быть отличается от размера в одну группу в другой конфигурации.  
  
 ![График групп вывода](~/extensibility/internals/media/vsoutputgroups.gif "vsOutputGroups")  
Выходные группы  
  
 Основное назначение <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg> интерфейс состоит в предоставлении доступа для построения, развертывания и отладки объектов управления и разрешить свободу выходы группы проектов. Дополнительные сведения об использовании этого интерфейса см. в разделе [Объект конфигурации проекта](../../extensibility/internals/project-configuration-object.md).  
  
 На предыдущей диаграмме встроенные группы имеет ключ вывода на конфигурации \(bD.exe или b.exe\), поэтому пользователь может создать ярлык для встроенные и знать, что ярлык будет работать независимо от конфигурации развертывания. Источник группы не имеет ключа выход, поэтому пользователю не удается создать ярлык. Если построение отладка группы имеет основного выходного файла, но не поддерживает встроенные группы розничной торговли, который будет неверной реализации. Следовательно, затем, если какой\-либо настройки группу, содержащую ни одного выхода и в результате нет файла ключа, а затем другие конфигурации с данной группой, содержащих выходные данные не может иметь файлы ключа. Установщик редакторы предполагается, что канонические имена и отображаемые имена групп, а также наличие файла ключа, не изменяйте на основе конфигурации.  
  
 Обратите внимание, что если проект имеет `IVsOutputGroup` для упаковки и развертывания не нужно, достаточно не помещать выходные данные в группе. Выходные данные по\-прежнему могут быть перечислены обычно путем реализации <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg.EnumOutputs%2A> метод, который возвращает все выходные данные конфигурации независимо от группирования.  
  
 Дополнительные сведения см. в разделе Реализация `IVsOutputGroup` в примере пользовательский проект в [MPF проектов](http://mpfproj12.codeplex.com).  
  
## См. также  
 [Управление параметрами конфигурации](../../extensibility/internals/managing-configuration-options.md)   
 [Настройка проекта для построения](../../extensibility/internals/project-configuration-for-building.md)   
 [Объект конфигурации проекта](../../extensibility/internals/project-configuration-object.md)   
 [Конфигурация решения](../../extensibility/internals/solution-configuration.md)