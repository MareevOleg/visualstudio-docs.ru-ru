---
title: "Создание нескольких экземпляров окна инструментов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multi
- tool windows
ms.assetid: 4a7872f1-acc9-4f43-8932-5a526b36adea
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: bed04fe13e7232b2c227072ab91e6a56db0c6963
ms.contentlocale: ru-ru
ms.lasthandoff: 09/26/2017

---
# <a name="creating-a-multi-instance-tool-window"></a>Создание нескольких экземпляров окна инструментов
Вы можете программировать окна инструментов, чтобы несколько экземпляров могут быть открыты одновременно. По умолчанию окна инструментов может иметь только один экземпляр открыть.  
  
 При использовании нескольких экземпляров окна инструментов можно отобразить несколько связанных источников информации, в то же время. Например, можно поместить несколько строк <xref:System.Windows.Forms.TextBox> управления в окне инструментов нескольких экземпляров, чтобы несколько фрагментов кода одновременно доступны во время программирования сеанса. Кроме того, например, можно поместить <xref:System.Windows.Forms.DataGrid> управления и раскрывающегося списка поле в окне инструментов нескольких экземпляров, чтобы одновременно можно отслеживать несколько источников данных в режиме реального времени.  
  
## <a name="creating-a-basic-single-instance-tool-window"></a>Создание окна инструментов Basic (экземпляра)  
  
1.  Создайте проект с именем **MultiInstanceToolWindow** с помощью шаблона VSIX и добавить шаблон элемента окна пользовательского инструмента с именем **MIToolWindow**.  
  
    > [!NOTE]
    >  Дополнительные сведения о создании модуля с окном инструментов см. в разделе [создания расширения с окном инструментов](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
## <a name="making-a-tool-window-multi-instance"></a>Создание нескольких экземпляр окна инструментов  
  
1.  Откройте **MIToolWindowPackage.cs** файла и найти `ProvideToolWindow` атрибута. и `MultiInstances=true` параметра, как показано в следующем примере.  
  
    ```csharp  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
        [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)] // Info on this package for Help/About  
        [ProvideMenuResource("Menus.ctmenu", 1)]  
        [ProvideToolWindow(typeof(MultiInstanceToolWindow.MIToolWindow), MultiInstances = true)]  
        [Guid(MIToolWindowPackageGuids.PackageGuidString)]  
        public sealed class MIToolWindowPackage : Package  
    {. . .}  
    ```  
  
2.  В файле MIToolWindowCommand.cs найдите метод ShowToolWindos(). В этом методе можно вызывать <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> метод и набор его `create` флаг `false` , чтобы он будет выполнять итерацию существующие экземпляры окна инструментов до доступный `id` найден.  
  
3.  Чтобы создать экземпляр окна, вызовите <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> метод и задайте его `id` доступных значение и его `create` флаг `true`.  
  
     По умолчанию значение `id` параметр <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> метод `0`. Это делает окно инструментов с одним экземпляром. Для более одного экземпляра размещаемой каждый экземпляр должен иметь собственный уникальный `id`.  
  
4.  Вызовите <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> метод <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> объект, возвращаемый <xref:Microsoft.VisualStudio.Shell.ToolWindowPane.Frame%2A> свойства экземпляра окна инструментов.  
  
5.  По умолчанию `ShowToolWindow` метод, который создается с помощью шаблона элемента окна инструмента создает окно инструментов с одним экземпляром. В следующем примере показано, как изменить `ShowToolWindow` метод для создания нескольких экземпляров.  
  
    ```csharp  
    private void ShowToolWindow(object sender, EventArgs e)  
    {  
        for (int i = 0; i < 10; i++)  
        {  
            ToolWindowPane window = this.package.FindToolWindow(typeof(MIToolWindow), i, false);  
            if (window == null)  
            {  
                // Create the window with the first free ID.   
                window = (ToolWindowPane)this.package.FindToolWindow(typeof(MIToolWindow), i, true);  
                if ((null == window) || (null == window.Frame))  
                {  
                    throw new NotSupportedException("Cannot create tool window");  
                }  
  
            IVsWindowFrame windowFrame = (IVsWindowFrame)window.Frame;  
            Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(windowFrame.Show());  
            break;  
            }  
        }  
    }  
    ```