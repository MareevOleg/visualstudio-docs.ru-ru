---
title: Extend the functionality of a TableAdapter | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data [Visual Studio], TableAdapters
- data [Visual Studio], extending TableAdapters
- TableAdapters, adding functionality
ms.assetid: 418249c8-c7f3-47ef-a94c-744cb6fe6aaf
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 9e6c28d42bec272c6fd6107b4baf0109ff29197e
ms.openlocfilehash: a72bc2d1c887cc15905c100e62c4ca007bfcad47
ms.contentlocale: ru-ru
ms.lasthandoff: 08/22/2017

---
# <a name="extend-the-functionality-of-a-tableadapter"></a>Extend the functionality of a TableAdapter
You can extend the functionality of a TableAdapter by adding code to the TableAdapter's partial class file.  
  
 The code that defines a TableAdapter is regenerated when any changes are made to the TableAdapter in the **Dataset Designer**, or when a wizard  modifies the configuration of a TableAdapter. To prevent your code from being deleted during the regeneration of a TableAdapter, add code to the TableAdapter's partial class file.  
  
 Partial classes allow code for a specific class to be divided among multiple physical files. For more information, see [Partial](/dotnet/visual-basic/language-reference/modifiers/partial) or [partial (Type)](/dotnet/csharp/language-reference/keywords/partial-type).  
  
## <a name="locate-tableadapters-in-code"></a>Locate TableAdapters in code  
 While TableAdapters are designed with the **Dataset Designer**, the TableAdapter classes that are generated are not  nested classes of <xref:System.Data.DataSet>. TableAdapters are located in a namespace based on the name of the TableAdapter's associated dataset. For example, if your application contains a dataset named `HRDataSet`, the TableAdapters would be located in the `HRDataSetTableAdapters` namespace. (The naming convention follows this pattern: *DatasetName* + `TableAdapters`).  
  
 The following example assumes a TableAdapter named `CustomersTableAdapter`is in a project with `NorthwindDataSet`.  
  
#### <a name="to-create-a-partial-class-for-a-tableadapter"></a>To create a partial class for a TableAdapter  
  
1.  Add a new class to your project by going to the **Project** menu and selecting **Add Class**.  
  
2.  Name the class `CustomersTableAdapterExtended`.  
  
3.  Select **Add**.  
  
4.  Replace the code with the correct namespace and partial class name for your project as follows:  
  
     [!code-cs[VbRaddataTableAdapters#2](../data-tools/codesnippet/CSharp/extend-the-functionality-of-a-tableadapter_1.cs)]  [!code-vb[VbRaddataTableAdapters#2](../data-tools/codesnippet/VisualBasic/extend-the-functionality-of-a-tableadapter_1.vb)]  
  
## <a name="see-also"></a>See Also  
 [Fill datasets by using TableAdapters](../data-tools/fill-datasets-by-using-tableadapters.md)