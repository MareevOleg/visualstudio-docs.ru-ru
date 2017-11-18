---
title: "Набор правил, диалоговое окно редактора (устаревшая версия) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Workflow.Activities.Rules.Design.RuleSetDialog.UI
helpviewer_keywords: Rule Set Editor dialog box
ms.assetid: 7cfd5df1-1115-4e5c-9b72-121f39419e83
caps.latest.revision: "7"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6ac342921696cb2a88426e2fd1f1ddee79e9341c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2017
---
# <a name="rule-set-editor-dialog-box-legacy"></a>Диалоговое окно «Редактор набора правил» (для прежних версий)
В этом разделе описывается использование **редактор набора правил** диалоговое окно в прежних [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]. [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] прежних версий используется при создании приложений для [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] или [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
 **Редактор набора правил** диалоговое окно используется для создания и изменения [PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019) наборов, которые будут сериализованы в файл с расширением RULES правил.  
  
> [!NOTE]
>  Если вы хотите открыть файл с расширением RULES **редактор XML с кодировкой**, необходимо сначала закрыть связанное окно конструктора для рабочего процесса или действия.  
  
 Сведения о доступе к **редактор набора правил** диалоговое окно, в разделе [как: создание PolicyActivity набора правил (для прежних версий)](../workflow-designer/how-to-create-a-policyactivity-rule-set-legacy.md).  
  
> [!WARNING]
>  Редактор правил [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] прежних версий, используемый для работы с [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] или [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)], не поддерживает настройку для различных версий.  
  
 В следующей таблице описаны элементы пользовательского интерфейса (UI) **редактор набора правил** диалоговое окно.  
  
|Элемент пользовательского интерфейса|Описание|  
|----------------|-----------------|  
|**Добавить правило**|Добавляет новое определение правила в набор правил.|  
|**Удалить**|Удаляет выбранное правило из набора правил.|  
|**Цепочки**|Задает тип прямой логической цепочки для использования с набором правил. Доступны следующие варианты:<br /><br /> -   **Полная логическая цепочка**, которая указывает использование механизмов все прямой логической цепочки: неявного, задание атрибутов и с помощью явного **обновления** функции.<br />-   **Последовательный**, который указывает не использовать все прямые логические цепочки.<br />-   **Только явное обновление**, которая указывает только выполнение прямых логических цепочек на **обновление** действия.<br /><br /> Дополнительные сведения о прямых логических цепочках см. в разделе [использование действия PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65004).|  
|**Имя**|Заголовок столбца со списком набора правил. Нажмите, чтобы отсортировать список правил по имени.|  
|**Приоритет**|Заголовок столбца со списком набора правил. Нажмите, чтобы отсортировать список правил по приоритету.|  
|**Повторная оценка**|Заголовок столбца со списком набора правил. Нажмите, чтобы отсортировать список правил по типу повторной оценки.|  
|**Предварительный просмотр правила**|Заголовок столбца со списком набора правил. Нажмите, чтобы отсортировать список правил по условию предварительного просмотра правила и действиям.|  
|**Имя:**|Введите имя правила.|  
|**Приоритет:**|Введите приоритет правила. Приоритет по умолчанию равен 0.|  
|**Повторная оценка:**|Задает тип повторной оценки правила для использования с правилом. Доступны следующие варианты:<br /><br /> -   **Всегда**, при необходимости повторная оценка правила.<br />-   **Никогда не**, никогда не повторная оценка правила. В этом случае правило выполняется только один раз.|  
|**Активный**|Включите, чтобы сделать это правило активным.|  
|**Условие:**|Введите выражение для условия правила. Описание синтаксиса выражений см. в разделе "Ввод выражений условия и действия" на этой странице.|  
|**Затем действия:**|Введите выражение для действий THEN. Описание синтаксиса выражений см. в разделе "Ввод выражений условия и действия" на этой странице.|  
|**Действия Else:**|Введите выражение для действий ELSE. Описание синтаксиса выражений см. в разделе "Ввод выражений условия и действия" на этой странице.|  
|**ХОРОШО**|Нажмите для сохранения набора правил в файл RULES.|  
  
 Дополнительные сведения о наборах правил см. в разделе [использование действия PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65004).  
  
## <a name="entering-condition-and-action-expressions"></a>Ввод выражений условия и действия  
 Введите выражения для условий, Then и Else действия в виде текста в соответствующие текстовые поля в **редактор набора правил** диалоговое окно. Можно ввести **это.** в редактор для ссылки на поля, свойства и методы, используемые в рабочем процессе с помощью типа IntelliSense меню. Либо можно прямо ввести имя члена рабочего процесса. Можно вызвать статические методы для ссылочных типов, для этого введите имя класса, далее имя метода.  
  
 К условию можно добавить логические операторы, например AND ("И"), OR ("ИЛИ") и NOT ("НЕ"). Также можно добавлять предикаты. Предикат - это бинарный оператор и два операнда. Бинарные операторы поддерживается ==, >, \<, > = и < =. Поддерживаемые операнды - константа арифметическая функция и члены с соответствующей областью действия.  
  
 Можно указать тип для сравнения, сравнивать можно со **null** или является пустой строкой. Можно вложить вызовы к членам в переменные, которые содержат сложный тип, например `this.Address.State == "WA"`.  
  
 Выражения поддерживают следующие операторы:  
  
-   Реляционные операторы: ==, =, !=  
  
-   Операторы сравнения: <, \<=, >, > =  
  
-   Арифметические операторы: +, -, *, /, MOD  
  
-   Логические операторы: И, & &, OR, &#124; &#124; NOT,!  
  
-   Битовые операторы: &, &#124;  
  
 Приоритет оператора выражения определяется правилами приоритета операторов языка C#.  
  
 Дополнительные сведения об условиях см. в разделе [использование условий в рабочих процессах](http://msdn.microsoft.com/en-us/541211f5-d382-4810-894f-71f00b34fa77).  
  
### <a name="halt-and-update-functions"></a>Функции Halt и Update  
 **Действия Then:** и **действия Else:** выражения поддерживают **прервет** и **обновление** функции. Для использования **прервет** введите **прервет** в **действие Then:** или **действие Else:** текстовое поле. **Прервет** выполнение набора правил для немедленной остановки и управление возвращается в вызывающий код. Вы используете **обновление** функция прямых логических цепочках.  
  
 **Обновление** инструкции могут быть выражены в редакторе в одной из двух форм; обе формы показаны в следующем примере:  
  
```  
Update(this.Address.State)  
Update("this/Address/State")  
```  
  
 Дополнительные сведения об использовании **обновление** с прямых логических цепочках см [использование действия PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65004).  
  
## <a name="see-also"></a>См. также  
 [Действие PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019)   
 [Диалоговое окно задания выберите правило (для прежних версий)](../workflow-designer/select-rule-set-dialog-box-legacy.md)   
 [Использование действия PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65004)   
 [Использование условий в рабочих процессах](http://go.microsoft.com/fwlink?LinkID=65009)