---
title: 'Walkthrough: Updating a Chart in a Document Using Radio Buttons | Microsoft Docs'
ms.custom: 
ms.date: 02/02/2017
ms.prod: visual-studio-dev14
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], updating using controls
- controls [Office development in Visual Studio], updating documents
ms.assetid: 56e6d1f2-65a4-41f0-aff5-f0cfd96d7185
caps.latest.revision: 60
author: kempb
ms.author: kempb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: eb5c9550fd29b0e98bf63a7240737da4f13f3249
ms.openlocfilehash: b70182f68576ac9e142f4819ff78c2804c5be907
ms.contentlocale: ru-ru
ms.lasthandoff: 08/30/2017

---
# <a name="walkthrough-updating-a-chart-in-a-document-using-radio-buttons"></a>Walkthrough: Updating a Chart in a Document Using Radio Buttons
  This walkthrough demonstrates how to use radio buttons in a document-level customization for Microsoft Office Word to give users the option to select chart styles on the document.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 This walkthrough illustrates the following tasks:  
  
-   Adding a chart to the document in a document-level project at design time.  
  
-   Grouping radio buttons by adding them to a user control.  
  
-   Changing the chart style when an option is selected.  
  
 To see the result as a completed sample, see the Word Controls Sample at [Office Development Samples and Walkthroughs](../vsto/office-development-samples-and-walkthroughs.md).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Prerequisites  
 You need the following components to complete this walkthrough:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] or [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].  
  
## <a name="creating-the-project"></a>Creating the Project  
 The first step is to create a Word Document project.  
  
#### <a name="to-create-a-new-project"></a>To create a new project  
  
1.  Create a Word Document project with the name **My Chart Options**. In the wizard, select **Create a new document**. For more information, see [How to: Create Office Projects in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio opens the new Word document in the designer and adds the **My Chart Options** project to **Solution Explorer**.  
  
## <a name="adding-a-chart-to-the-document"></a>Adding a Chart to the Document  
  
#### <a name="to-add-a-chart"></a>To add a chart  
  
1.  In the Word document that is hosted in the Visual Studio designer, on the Ribbon, click the **Insert** tab.  
  
2.  In the **Text** group, click the **Insert Object** drop-down button, and click **Object**.  
  
     The **Object** dialog box opens.  
  
3.  In the **Object type** list on the **Create New** tab, select **Microsoft Graph Chart** and then click **OK**.  
  
     A chart is added to the document at the insertion point, and the **Datasheet** window appears with some default data.  
  
4.  Close the **Datasheet** window to accept the default values in the chart and click inside the document to move focus away from the chart.  
  
5.  Right-click the chart, and then click **Format Object**.  
  
6.  On the **Layout** tab of the **Format Object** dialog box, select **Square** and click **OK**.  
  
## <a name="adding-a-user-control-to-the-project"></a>Adding a User Control to the Project  
 Radio buttons on a document are not mutually exclusive by default. You can make them function correctly by adding them to a user control, and then writing code to control the selection.  
  
#### <a name="to-add-a-user-control"></a>To add a user control  
  
1.  Select the **My Chart Options** project in **Solution Explorer**.  
  
2.  On the **Project** menu, click **Add New Item**.  
  
3.  In the **Add New Item** dialog box, click **User Control**, name the control **ChartOptions,** and click **Add**.  
  
#### <a name="to-add-windows-form-controls-to-the-user-control"></a>To add Windows Form controls to the user control  
  
1.  If the user control is not visible in the designer, double-click **ChartOptions** in **Solution Explorer**.  
  
2.  From the **Common Controls** tab of the **Toolbox**, drag the first **Radio Button** control to the user control, and change the following properties.  
  
    |Property|Value|  
    |--------------|-----------|  
    |**Name**|**columnChart**|  
    |**Text**|**Column Chart**|  
  
3.  Add a second **Radio Button** to the user control, and change the following properties.  
  
    |Property|Value|  
    |--------------|-----------|  
    |**Name**|**barChart**|  
    |**Text**|**Bar Chart**|  
  
4.  Add a third **Radio Button** to the user control, and change the following properties.  
  
    |Property|Value|  
    |--------------|-----------|  
    |**Name**|**lineChart**|  
    |**Text**|**Line Chart**|  
  
5.  Add a fourth **Radio Button** to the user control, and change the following properties.  
  
    |Property|Value|  
    |--------------|-----------|  
    |**Name**|**areaBlockChart**|  
    |**Text**|**Area Block Chart**|  
  
## <a name="adding-references"></a>Adding References  
 To access the chart from the user control on a document, you must have a reference to the Microsoft.Office.Interop.Graph assembly in your project.  
  
#### <a name="to-add-a-reference-to-the-microsoftofficeinteropgraph-assembly"></a>To add a reference to the Microsoft.Office.Interop.Graph assembly  
  
1.  On the **Project** menu, click **Add Reference**.  
  
     The **Add Reference** dialog box appears.  
  
2.  On the **.NET** tab, select **Microsoft.Office.Interop.Graph** and click **OK**. Select the 14.0.0.0 version of the assembly.  
  
## <a name="changing-the-chart-style-when-a-radio-button-is-selected"></a>Changing the Chart Style when a Radio Button is Selected  
 To make the buttons work correctly, create a public event on the user control, add a property to set the selection type, and create a procedure for the `CheckedChanged` event of each of the radio buttons.  
  
#### <a name="to-create-an-event-and-property-on-a-user-control"></a>To create an event and property on a user control  
  
1.  In **Solution Explorer**, right-click the user control, and then click **View Code**.  
  
2.  Add code to create a `SelectionChanged` event and the `Selection` property to the `ChartOptions` class.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#9](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#9)]  [!code-vb[Trin_VstcoreProgrammingControlsWord#9](../vsto/codesnippet/VisualBasic/my chart options/ChartOptions.vb#9)]  
  
#### <a name="to-handle-the-checkedchange-event-of-the-radio-buttons"></a>To handle the CheckedChange event of the radio buttons  
  
1.  Set the chart type in the `CheckedChanged` event handler of the `areaBlockChart` radio button and then raise the event.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#10](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#10)]  [!code-vb[Trin_VstcoreProgrammingControlsWord#10](../vsto/codesnippet/VisualBasic/my chart options/ChartOptions.vb#10)]  
  
2.  Set the chart type in the `CheckedChanged` event handler of the `barChart` radio button.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#11](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#11)]  [!code-vb[Trin_VstcoreProgrammingControlsWord#11](../vsto/codesnippet/VisualBasic/my chart options/ChartOptions.vb#11)]  
  
3.  Set the chart type in the `CheckedChanged` event handler of the `columnChart` radio button.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#12](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#12)]  [!code-vb[Trin_VstcoreProgrammingControlsWord#12](../vsto/codesnippet/VisualBasic/my chart options/ChartOptions.vb#12)]  
  
4.  Set the chart type in the `CheckedChanged` event handler of the `lineChart` radio button.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#13](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#13)]  [!code-vb[Trin_VstcoreProgrammingControlsWord#13](../vsto/codesnippet/VisualBasic/my chart options/ChartOptions.vb#13)]  
  
5.  In C#, you must add event handlers for the radio buttons. You can add the code to the `ChartOptions` constructor, beneath the call to `InitializeComponent`. For information about creating event handlers, see [How to: Create Event Handlers in Office Projects](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#14](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#14)]  
  
## <a name="adding-the-user-control-to-the-document"></a>Adding the User Control to the Document  
 When you build the solution, the new user control is automatically added to the **Toolbox**. You can then drag the control from the **Toolbox** to your document.  
  
#### <a name="to-add-the-user-control-your-document"></a>To add the user control your document  
  
1.  On the **Build** menu, click **Build Solution**.  
  
     The **ChartOptions** user control is added to the **Toolbox**.  
  
2.  In **Solution Explorer**, right-click **ThisDocument.vb** or **ThisDocument.cs**, and then click **View Designer**.  
  
3.  Drag the `ChartOptions` control from the **Toolbox** to the document.  
  
     In the **Properties** window, name the control that you just added to the document  `ChartOptions1`.  
  
## <a name="changing-the-chart-type"></a>Changing the Chart Type  
 Create an event handler to change the chart type according to the option that is selected in the user control.  
  
#### <a name="to-change-the-type-of-chart-that-is-displayed-in-the-document"></a>To change the type of chart that is displayed in the document  
  
1.  Add the following event handler to the `ThisDocument` class.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsWord#15](../vsto/codesnippet/VisualBasic/my chart options/ThisDocument.vb#15)]  [!code-csharp[Trin_VstcoreProgrammingControlsWord#15](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#15)]  
  
2.  In C#, you must add an event handler for the user control to the <xref:Microsoft.Office.Tools.Word.Document.Startup> event.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#16](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#16)]  
  
## <a name="testing-the-application"></a>Testing the Application  
 You can now test your document to make sure that the chart style is updated correctly when you select a radio button.  
  
#### <a name="to-test-your-document"></a>To test your document  
  
1.  Press F5 to run your project.  
  
2.  Select various radio buttons.  
  
3.  Confirm that the chart style changes to match the selection.  
  
## <a name="next-steps"></a>Next Steps  
 Here are some tasks that might come next:  
  
-   Using a button to populate a text box. For more information, see [Walkthrough: Displaying Text in a Text Box in a Document Using a Button](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-document-using-a-button.md).  
  
-   Change formatting by selecting a style from a combo box. For more information, see [Walkthrough: Changing Document Formatting Using CheckBox Controls](../vsto/walkthrough-changing-document-formatting-using-checkbox-controls.md).  
  
## <a name="see-also"></a>See Also  
 [Walkthroughs Using Word](../vsto/walkthroughs-using-word.md)   
 [Office Development Samples and Walkthroughs](../vsto/office-development-samples-and-walkthroughs.md)   
 [Limitations of Windows Forms Controls on Office Documents](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)  
  
  