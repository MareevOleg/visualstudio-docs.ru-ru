---
title: Pass data between forms | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- walkthroughs [Windows Forms], data
- walkthroughs [Visual Studio], data
- data [Visual Studio], passing between forms
- forms, passing data between
- Windows Forms, walkthroughs
ms.assetid: 78bf038b-9296-4fbf-b0e8-d881d1aff0df
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
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
ms.sourcegitcommit: cca2a707627c36221a654cf8a06730383492f371
ms.openlocfilehash: 8e64b722b4156c9aeaf7345bc726283dd913a0b3
ms.contentlocale: ru-ru
ms.lasthandoff: 09/13/2017

---
# <a name="pass-data-between-forms"></a>Pass data between forms
This walkthrough provides step-by-step instructions for passing data from one form to another. Using the customers and orders tables from Northwind, one form allows users to select a customer, and a second form displays the selected customer's orders. This walkthrough shows how to create a method on the second form that receives data from the first form.  
  
> [!NOTE]
>  This walkthrough demonstrates only one way to pass data between forms. There are other options for passing data to a form, including creating a second constructor to receive data, or creating a public property that can be set with data from the first form.  
  
 Tasks illustrated in this walkthrough include:  
  
-   Creating a new **Windows Forms Application** project.  
  
-   Creating and configuring a dataset with the [Data Source Configuration Wizard](../data-tools/media/data-source-configuration-wizard.png).  
  
-   Selecting the control to be created on the form when dragging items from the **Data Sources** window. For more information, see [Set the control to be created when dragging from the Data Sources window](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).  
  
-   Creating a data-bound control by dragging items from the **Data Sources** window onto a form.  
  
-   Creating a second form with a grid to display data.  
  
-   Creating a TableAdapter query to fetch orders for a specific customer.  
  
-   Passing data between forms.  
  
## <a name="prerequisites"></a>Prerequisites  
 In order to complete this walkthrough, you need:  
  
-   Access to the Northwind sample database. For more information, see [How to: Install Sample Databases](../data-tools/installing-database-systems-tools-and-samples.md).  
  
## <a name="create-the-windows-forms-application"></a>Create the Windows Forms Application  
  
#### <a name="to-create-the-new-windows-project"></a>To create the new Windows project  
  
1. In Visual Studio, on the **File** menu, select **New**, **Project...**.  
  
2. Expand either **Visual C#** or **Visual Basic** in the left-hand pane, then select **Windows Classic Desktop**.  

3. In the middle pane, select the **Windows Forms App** project type.  

4. Name the project **PassingDataBetweenForms**, and then choose **OK**. 
  
     The **PassingDataBetweenForms** project is created, and added to **Solution Explorer**.  
  
## <a name="create-the-data-source"></a>Create the data source  
  
#### <a name="to-create-the-data-source"></a>To create the data source  
  
1.  On the **Data** menu, click **Show Data Sources**.  
  
2.  In the **Data Sources** window, select **Add New Data Source** to start the **Data Source Configuration** wizard.  
  
3.  Select **Database** on the **Choose a Data Source Type** page, and then click **Next**.  
  
4.  On the **Choose a database model** page, verify that **Dataset** is specified, and then click **Next**.  
  
5.  On the **Choose your Data Connection** page, do one of the following:  
  
    -   If a data connection to the Northwind sample database is available in the drop-down list, select it.  
  
    -   Select **New Connection** to launch the **Add/Modify Connection** dialog box.  
  
6.  If your database requires a password and if the option to include sensitive data is enabled, select the option and then click **Next**.  
  
7.  On the **Save connection string to the Application Configuration file** page, click **Next**.  
  
8.  On the **Choose your Database Objects** page, expand the **Tables** node.  
  
9. Select the **Customers** and **Orders** tables, and then click **Finish**.  
  
     The **NorthwindDataSet** is added to your project, and the **Customers** and **Orders** tables appear in the **Data Sources** window.  
  
## <a name="create-the-first-form-form1"></a>Create the first form (Form1)  
 You can create a data-bound grid (a <xref:System.Windows.Forms.DataGridView> control), by dragging the **Customers** node from the **Data Sources** window onto the form.  
  
#### <a name="to-create-a-data-bound-grid-on-the-form"></a>To create a data-bound grid on the form  
  
-   Drag the main **Customers** node from the **Data Sources** window onto **Form1**.  
  
     A <xref:System.Windows.Forms.DataGridView> and a tool strip (<xref:System.Windows.Forms.BindingNavigator>) for navigating records appear on **Form1**. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), CustomersTableAdapter, <xref:System.Windows.Forms.BindingSource>, and <xref:System.Windows.Forms.BindingNavigator> appear in the component tray.  
  
## <a name="create-the-second-form-form2"></a>Create the second form (Form2)  
  
#### <a name="to-create-a-second-form-to-pass-the-data-to"></a>To create a second form to pass the data to  
  
1.  From the **Project** menu, choose **Add Windows Form**.  
  
2.  Leave the default name of **Form2**, and click **Add**.  
  
3.  Drag the main **Orders** node from the **Data Sources** window onto **Form2**.  
  
     A <xref:System.Windows.Forms.DataGridView> and a tool strip (<xref:System.Windows.Forms.BindingNavigator>) for navigating records appear on **Form2**. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), CustomersTableAdapter, <xref:System.Windows.Forms.BindingSource>, and <xref:System.Windows.Forms.BindingNavigator> appear in the component tray.  
  
4.  Delete the **OrdersBindingNavigator** from the component tray.  
  
     The **OrdersBindingNavigator** disappears from **Form2**.  
  
## <a name="add-a-tableadapter-query-to-form2-to-load-orders-for-the-selected-customer-on-form1"></a>Add a TableAdapter query to Form2 to load orders for the selected customer on Form1  
  
#### <a name="to-create-a-tableadapter-query"></a>To create a TableAdapter query  
  
1.  Double-click the **NorthwindDataSet.xsd** file in **Solution Explorer**.  
  
2.  Right-click the **OrdersTableAdapter**, and select **Add Query**.  
  
3.  Leave the default option of **Use SQL statements**, and then click **Next**.  
  
4.  Leave the default option of **SELECT which returns rows**, and then click **Next**.  
  
5.  Add a WHERE clause to the query, to return `Orders` based on the `CustomerID`. The query should be similar to the following:  
  
    ```  
    SELECT OrderID, CustomerID, EmployeeID, OrderDate, RequiredDate, ShippedDate, ShipVia, Freight, ShipName, ShipAddress, ShipCity, ShipRegion, ShipPostalCode, ShipCountry  
    FROM Orders   
    WHERE CustomerID = @CustomerID  
    ```  
  
    > [!NOTE]
    >  Verify the correct parameter syntax for your database. For example, in Microsoft Access, the WHERE clause would look like: `WHERE CustomerID = ?`.  
  
6.  Click **Next**.  
  
7.  For the **Fill a DataTableMethod Name**, type `FillByCustomerID`.  
  
8.  Clear the **Return a DataTable** option, and then click **Next**.  
  
9. Click **Finish**.  
  
## <a name="create-a-method-on-form2-to-pass-data-to"></a>Create a method on Form2 to pass data to  
  
#### <a name="to-create-a-method-to-pass-data-to"></a>To create a method to pass data to  
  
1.  Right-click **Form2**, and select **View Code** to open **Form2** in the **Code Editor**.  
  
2.  Add the following code to **Form2** after the `Form2_Load` method:  
  
     [!code-vb[VbRaddataDisplaying#1](../data-tools/codesnippet/VisualBasic/pass-data-between-forms_1.vb)]
     [!code-csharp[VbRaddataDisplaying#1](../data-tools/codesnippet/CSharp/pass-data-between-forms_1.cs)]  
  
## <a name="create-a-method-on-form1-to-pass-data-and-display-form2"></a>Create a method on Form1 to pass data and display Form2  
  
#### <a name="to-create-a-method-to-pass-data-to-form2"></a>To create a method to pass data to Form2  
  
1.  In **Form1**, right-click the Customer data grid, and then click **Properties**.  
  
2.  In the **Properties** window, click **Events**.  
  
3.  Double-click the **CellDoubleClick** event.  
  
     The code editor appears.  
  
4.  Update the method definition to match the following sample:  
  
     [!code-csharp[VbRaddataDisplaying#2](../data-tools/codesnippet/CSharp/pass-data-between-forms_2.cs)]
     [!code-vb[VbRaddataDisplaying#2](../data-tools/codesnippet/VisualBasic/pass-data-between-forms_2.vb)]  
  
## <a name="run-the-application"></a>Run the Application  
  
#### <a name="to-run-the-application"></a>To run the application  
  
-   Press F5 to run the application.  
  
-   Double-click a customer record in **Form1** to open **Form2** with that customer's orders.  
  
## <a name="next-steps"></a>Next Steps  
 Depending on your application requirements, there are several steps you may want to perform after passing data between forms. Some enhancements you could make to this walkthrough include:  
  
-   Editing the dataset, to add or remove database objects. For more information, see [Create and configure datasets](../data-tools/create-and-configure-datasets-in-visual-studio.md).  
  
-   Adding functionality to save data back to the database. For more information, see [Save data back to the database](../data-tools/save-data-back-to-the-database.md).  
  
## <a name="see-also"></a>See Also  
 [Bind Windows Forms controls to data in Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)