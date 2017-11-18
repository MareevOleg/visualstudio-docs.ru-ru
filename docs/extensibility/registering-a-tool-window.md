---
title: "Регистрация окна инструментов | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Регистрация управляемых окна инструментов"
  - "окна инструментов, регистрация"
ms.assetid: 8c8c4a24-3da4-497b-9db2-0ddd7cfbfdd2
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# Регистрация окна инструментов
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Можно зарегистрировать с помощью средства windows <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> и  <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowVisibilityAttribute>  
  
## Пример  
  
```c#  
  
      [ProvideToolWindow(typeof(PersistedWindowPane), Style = MsVsShell.VsDockStyle.Tabbed, Window = "3ae79031-e1bc-11d0-8f78-00a0c9110057")] [ProvideToolWindow(typeof(DynamicWindowPane), PositionX=250, PositionY=250, Width=160, Height=180, Transient=true)] [ProvideToolWindowVisibility(typeof(DynamicWindowPane), /*UICONTEXT_SolutionExists*/"f1536ef8-92ec-443c-9ed7-fdadf150da82")]  
[ProvideMenuResource(1000, 1)]  
[PackageRegistration(UseManagedResourcesOnly = true)]  
[Guid("01069CDD-95CE-4620-AC21-DDFF6C57F012")]  
public class PackageToolWindow : Package  
{  
```  
  
 В приведенном выше коде <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> регистрирует PersistedWindowPane и DynamicWindowPane окна инструментов в Visual Studio. Материализованные окно закреплено и с вкладками с **обозревателе решений**, и окно динамической начальной позиции и размера. Динамическое окно становится временными, указывающая, что она не была создана при запуске. Это записывает DontForceCreate значение в ключе ToolWindows в системном реестре. Для получения дополнительной информации см. [Настройка отображения окна средства](../extensibility/tool-window-display-configuration.md).