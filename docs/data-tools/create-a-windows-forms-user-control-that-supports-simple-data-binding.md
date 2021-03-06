---
title: Создание пользовательского элемента управления с простой привязкой данных
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom controls [Visual Studio], Data Sources Window
- Data Sources Window, controls
ms.assetid: b1488366-6dfb-454e-9751-f42fd3f3ddfb
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 673e510536ab866f3be90da630d3cfa261bb98c6
ms.sourcegitcommit: 81e9d90843ead658bc73b30c869f25921d99e116
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2018
ms.locfileid: "52305407"
---
# <a name="create-a-windows-forms-user-control-that-supports-simple-data-binding"></a>Создание пользовательского элемента управления Windows Forms с простой привязкой данных

При отображении данных на формах в приложениях Windows вы можете выбрать имеющиеся элементы управления в **области элементов** или создать пользовательские элементы управления, если вашему приложению требуется функциональность, отсутствующая в стандартных элементах управления. В этом пошаговом руководстве демонстрируется создание элемента управления, реализующего <xref:System.ComponentModel.DefaultBindingPropertyAttribute>. Элементы управления, реализующие <xref:System.ComponentModel.DefaultBindingPropertyAttribute>, могут содержать одно свойство, которое можно привязать к данным. Такие элементы управления похожи на <xref:System.Windows.Forms.TextBox> или <xref:System.Windows.Forms.CheckBox>.

Дополнительные сведения о создании элементов управления, см. в разделе [Разработка Windows Forms элементов управления во время разработки](/dotnet/framework/winforms/controls/developing-windows-forms-controls-at-design-time).

При создании элементов управления для использования в сценариях привязки данных, должны реализовывать один из следующих атрибутов привязки к данным:

|Использование атрибута привязки данных|
| - |
|Реализуйте <xref:System.ComponentModel.DefaultBindingPropertyAttribute> на простых элементах управления, таких как <xref:System.Windows.Forms.TextBox>, которые отображают отдельный столбец (или свойство) данных. (Этот процесс описан в данном пошаговом руководстве.)|
|Реализуйте <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> на элементах управления, таких как <xref:System.Windows.Forms.DataGridView>, которые отображают списки (или таблицы) данных. Дополнительные сведения см. в разделе [создать пользовательский элемент управления Windows Forms, который поддерживает сложную привязку данных](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md).|
|Реализуйте <xref:System.ComponentModel.LookupBindingPropertiesAttribute> на элементах управления, таких как <xref:System.Windows.Forms.ComboBox>, которые отображают списки (или таблицы) данных, но также должны представлять отдельный столбец или отдельное свойство. Дополнительные сведения см. в разделе [создать пользовательский элемент управления Windows Forms с привязкой данных подстановки](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md).|

В этом пошаговом руководстве создается простой элемент управления, отображающий данные из одного столбца в таблице. В данном примере используется столбец `Phone` таблицы `Customers` из учебной базы данных "Борей". Этот простой элемент управления отображает номера телефонов заказчиков в стандартный формат номера телефона, с помощью <xref:System.Windows.Forms.MaskedTextBox> и задавая маску для номера телефона.

В этом пошаговом руководстве описаны следующие процедуры.

-   Создание **приложения Windows Forms**.

-   Добавление нового **пользовательского элемента управления** в проект.

-   Визуальное проектирование пользовательского элемента управления.

-   Реализация атрибута `DefaultBindingProperty`.

-   Создание набора данных с помощью **конфигурации источника данных** мастера.

-   Настройка столбца **Phone** в окне **Источники данных** для использования нового элемента управления.

-   Создание формы для отображения данных в новом элементе управления.

## <a name="prerequisites"></a>Предварительные требования

В этом пошаговом руководстве используется SQL Server Express LocalDB и базе данных Northwind.

1.  Если у вас нет SQL Server Express LocalDB, установите его из [странице загрузки SQL Server Express](https://www.microsoft.com/sql-server/sql-server-editions-express), либо с помощью **установщик Visual Studio**. В **установщик Visual Studio**, можно установить SQL Server Express LocalDB как часть **хранение и обработка данных** рабочей нагрузки, или в качестве отдельного компонента.

2.  Установка образца базы данных "Борей", выполнив следующие действия:

    1. В Visual Studio откройте **обозреватель объектов SQL Server** окна. (Обозреватель объектов SQL Server устанавливается как часть **хранение и обработка данных** рабочей нагрузки в **установщик Visual Studio**.) Разверните **SQL Server** узла. Щелкните правой кнопкой мыши на локальном экземпляре LocalDB и выберите **новый запрос**.

       Откроется окно редактора запросов.

    2. Копировать [скрипт Northwind Transact-SQL](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) в буфер обмена. Этот сценарий T-SQL создает базу данных "Борей" с нуля и заполняет ее данными.

    3. Вставьте сценарий T-SQL в редакторе запросов, а затем выберите **Execute** кнопки.

       Через некоторое время выполнения запроса отобразятся и создания базы данных Northwind.

## <a name="create-a-windows-forms-application"></a>Создание приложения Windows Forms

Первым шагом является создание **приложение Windows Forms**:

1. В Visual Studio на **файл** меню, выберите **New** > **проекта**.

2. Разверните **Visual C#**  или **Visual Basic** левой панели, а затем выберите **Windows Desktop**.

3. В средней области выберите **приложения Windows Forms** тип проекта.

4. Назовите проект **SimpleControlWalkthrough**, а затем выберите **ОК**.

     Создается проект **SimpleControlWalkthrough**, который добавляется в **Обозреватель решений**.

## <a name="add-a-user-control-to-the-project"></a>Добавление пользовательского элемента управления в проект

В этом пошаговом руководстве создается простой элемент управления можно привязать к данным из **пользовательский элемент управления**. Добавить **пользовательский элемент управления** элемент **SimpleControlWalkthrough** проекта:

1.  В меню **Проект** выберите пункт **Добавить пользовательский элемент управления**.

2.  Введите **PhoneNumberBox** в области "Имя" и нажмите кнопку **Добавить**.

     Элемент управления **PhoneNumberBox** добавляется в **Обозреватель решений** и открывается в конструкторе.

## <a name="design-the-phonenumberbox-control"></a>Порядок проектирования элемента управления PhoneNumberBox

В этом пошаговом руководстве расширяется существующий <xref:System.Windows.Forms.MaskedTextBox> для создания **PhoneNumberBox** управления:

1.  Перетащите <xref:System.Windows.Forms.MaskedTextBox> из **области элементов** на рабочую область конструирования пользовательского элемента управления.

2.  Выберите смарт-тег на только что перетащенном <xref:System.Windows.Forms.MaskedTextBox> и выберите **Установка маски**.

3.  Выберите **Номер телефона** в диалоговом окне **Маска ввода** и нажмите кнопку **ОК** для задания маски.

## <a name="add-the-required-data-binding-attribute"></a>Добавьте необходимый атрибут привязки данных

Для простых элементов управления, поддерживающих привязку к данным, реализуйте <xref:System.ComponentModel.DefaultBindingPropertyAttribute>:

1.  Коммутатор **PhoneNumberBox** элемента управления в представление кода. (В меню **Вид** выберите **Код**.)

2.  Замените код в **PhoneNumberBox** на следующий:

     [!code-csharp[VbRaddataDisplaying#3](../data-tools/codesnippet/CSharp/create-a-windows-forms-user-control-that-supports-simple-data-binding_1.cs)]
     [!code-vb[VbRaddataDisplaying#3](../data-tools/codesnippet/VisualBasic/create-a-windows-forms-user-control-that-supports-simple-data-binding_1.vb)]

3.  В меню **Построение** выберите пункт **Построить решение**.

## <a name="create-a-data-source-from-your-database"></a>Создать источник данных из базы данных

В этом шаге **Мастер настройки источника данных** используется для создания источника данных на основе таблицы `Customers` в учебной базе данных "Борей". Для создания подключения необходимо иметь доступ к учебной базе данных "Борей". Сведения о настройке учебной базе данных Northwind, см. в разделе [как: установить образцы баз данных](../data-tools/installing-database-systems-tools-and-samples.md).

1.  Чтобы открыть **источников данных** окна на **данных** меню, щелкните **Показать источники данных**.

2.  В окне **Источники данных** выберите **Добавить новый источник данных**, чтобы запустить **Мастер настройки источника данных**.

3.  На странице **Выбор типа источника данных** выберите **База данных** и нажмите кнопку **Далее**.

4.  На странице **Выбор подключения к базе данных** выполните одно из следующих действий:

    -   Если подключение к учебной базе данных Northwind доступно в раскрывающемся списке, то выберите его.

    -   Выберите **Новое подключение** для открытия диалогового окна **Добавить/изменить подключение**.

5.  Если базе данных требуется пароль, выберите параметр для включения конфиденциальных данных и нажмите кнопку **Далее**.

6.  На **сохранение подключения в файле конфигурации приложения** щелкните **Далее**.

7.  Разверните узел **Таблицы** на странице **Выбор объектов базы данных**.

8.  Выберите таблицу `Customers` и нажмите кнопку **Готово**.

     Объект **NorthwindDataSet** добавляется в проект, и таблица `Customers` отображается в окне **Источники данных**.

## <a name="set-the-phone-column-to-use-the-phonenumberbox-control"></a>Порядок настройки столбца телефона на использование элемента управления PhoneNumberBox

Вы можете задать создаваемый элемент управления в окне **Источники данных** перед перетаскиванием элементов на форму.

1.  Откройте **Form1** в конструкторе.

2.  Разверните узел **Customers** в окне **Источники данных**.

3.  Щелкните стрелку раскрывающегося списка в узле **Customers** и выберите **Сведения** в списке элементов управления.

4.  Щелкните стрелку раскрывающегося списка в столбце **Phone** и выберите **Настроить**.

5.  Выберите **PhoneNumberBox** в списке **Связанные элементы управления** диалогового окна **Настройка данных интерфейса пользователя**.

6.  Щелкните стрелку раскрывающегося списка в столбце **Phone** и выберите **PhoneNumberBox**.

## <a name="add-controls-to-the-form"></a>Добавление элементов управления на форму

Вы можете создавать элементы управления с привязкой к данным с помощью перетаскивания элементов из окна **Источники данных** на форму.

Чтобы создать элементы управления с привязкой данных в форме, перетащите главный **клиентов** узел из **источников данных** окна в форму и убедитесь, что **PhoneNumberBox** элемент управления используется для отображения данных в **Phone** столбца.

     Data-bound controls with descriptive labels appear on the form, along with a tool strip (<xref:System.Windows.Forms.BindingNavigator>) for navigating records. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), CustomersTableAdapter, <xref:System.Windows.Forms.BindingSource>, and <xref:System.Windows.Forms.BindingNavigator> appear in the component tray.

## <a name="run-the-application"></a>Запуск приложения

Нажмите клавишу **F5** для запуска приложения.

## <a name="next-steps"></a>Следующие шаги

В зависимости от требований приложения существуют несколько шагов, которые, возможно, потребуется выполнить после создания элемента управления, поддерживающего привязку к данным. Некоторые типичные дальнейшие действия.

-   Помещение пользовательских элементов управления в библиотеку элементов управления, чтобы их можно было повторно использовать в других приложениях.

-   Создание элементов управления, поддерживающих более сложных сценариев привязки к данным. Дополнительные сведения см. в разделе [создать пользовательский элемент управления Windows Forms, который поддерживает сложную привязку данных](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md) и [создать пользовательский элемент управления Windows Forms с привязкой данных подстановки](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md).

## <a name="see-also"></a>См. также

- [Привязка элементов управления Windows Forms к данным в Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
- [Задание поведения, при котором элемент управления создается при перетаскивании из окна "Источники данных"](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)