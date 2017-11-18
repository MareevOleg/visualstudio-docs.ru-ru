---
title: "Рефакторинг (C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.csharp.refactoring.preview"
  - "vs.csharp.refactoring.issues"
  - "vs.csharp.refactoring.buildwarning"
  - "VS.PreviewChanges"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "рефакторинг [C#]"
ms.assetid: a39e656a-f81f-4c87-b484-a23168ff1dfc
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Рефакторинг (C#)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Рефакторинг — это процесс улучшения написанного ранее кода путем такого изменения его внутренней структуры, которое не влияет на внешнее поведение.  
  
 Среда разработки Visual C\# предоставляет в меню **Рефакторинг** следующие команды оптимизации:  
  
-   [Рефакторинг для извлечения метода \(C\#\)](../csharp-ide/extract-method-refactoring-csharp.md)  
  
-   [Переименовать рефакторинг \(C\#\)](../csharp-ide/rename-refactoring-csharp.md)  
  
-   [Рефакторинг для инкапсуляции поля \(C\#\)](../csharp-ide/encapsulate-field-refactoring-csharp.md)  
  
-   [Рефакторинг для извлечения интерфейса \(C\#\)](../csharp-ide/extract-interface-refactoring-csharp.md)  
  
-   [Рефакторинг для удаления параметров \(C\#\)](../csharp-ide/remove-parameters-refactoring-csharp.md)  
  
-   [Рефакторинг для упорядочения параметров \(C\#\)](../csharp-ide/reorder-parameters-refactoring-csharp.md)  
  
## Многопроектная оптимизация  
 Среда разработки Visual Studio поддерживает многопроектная оптимизация для проектов, входящих в одно решение.  Все операции рефакторинга, исправляющие ссылки между файлами, выполняют исправление ссылок во всех проектах, реализованных на одном языке.  Это действует в отношении всех ссылок между проектами.  Например, если консольное приложение содержит ссылки на библиотеку классов, то при переименовании типа в библиотеке классов \(с помощью операции рефакторинга `Rename`\) содержащиеся в консольном приложении ссылки на тип в библиотеке классов также будут обновлены.  
  
## Предварительный просмотр изменений  
 Многие операции рефакторинга дают возможность просматривать все изменения ссылок, которые будут выполнены операцией рефакторинга в коде, до осуществления этих изменений.  Для этих операций рефакторинга в диалоговом окне оптимизации отображается параметр **Предварительный просмотр изменений ссылок**.  После того как этот параметр будет выбран и операция рефакторинга принята, откроется диалоговое окно **Предварительный просмотр изменений**.  Обратите внимание, что окно **Предварительный просмотр изменений** имеет два представления.  В нижнем представлении отображается код со всеми обновлениями ссылок в связи с выполнением операции рефакторинга.  Нажатие кнопки **Отмена** в диалоговом окне **Предварительный просмотр изменений** приводит к остановке выполнения операции рефакторинга, и никаких изменений в код не вносится.  
  
## Предупреждения об ошибке рефакторинга  
 Если компилятор не полностью понимает программу или, что также не исключено, подсистема рефакторинга не обновила все соответствующие ссылки, будет открыто диалоговое окно предупреждения.  Это диалоговое окно предупреждения также позволяет просмотреть внесенные в код изменения в диалоговом окне **Предварительный просмотр изменений** до того, как они будут зафиксированы.  
  
> [!NOTE]
>  Если какой\-то метод содержит синтаксическую ошибку \(что помечается интегрированной средой разработки подчеркиванием красной волнистой линией\), то подсистема оптимизации не будет обновлять ссылки на элемент в этом методе.  Приведенный ниже пример демонстрирует это поведение.  
  
 По умолчанию, если какая\-либо операция рефакторинга выполняется без предварительного просмотра изменений ссылок и в программе обнаруживается ошибка компиляции, то среда разработки выводит это диалоговое окно предупреждения.  
  
 Если во время операции рефакторинга при включенной функции **Предварительный просмотр изменений ссылок** в программе будет обнаружена ошибка компиляции, вместо диалогового окна **Предупреждение об ошибке рефакторинга** среда разработки выведет в нижней части диалогового окна **Предварительный просмотр изменений** следующее предупреждающее сообщение:  
  
 **Построение данного проекта или какой\-то его зависимости в настоящее время не выполнено.  Ссылки могут быть не обновлены.**  
  
 Это предупреждение об ошибке рефакторинга доступно только при выполнении операций рефакторинга, для которых предусмотрено использование функции **Предварительный просмотр изменений ссылок**.  
  
## Нечувствительный к ошибкам рефакторинг и результаты проверки  
 Оптимизация допускает наличие ошибок.  Иными словами, можно выполнить оптимизацию проекта, построение которого выполнить невозможно.  Однако в таких случаях процесс оптимизации может неправильно обновить неоднозначные ссылки.  
  
 Диалоговое окно **Результаты проверки** уведомляет о выявленных подсистемой оптимизации ошибках компиляции или операциях рефакторинга, которые по недосмотру привели к появлению в коде ошибочных привязок к иному, чем прежде, объекту \(ошибок повторной привязки\).  
  
 Чтобы включить функцию проверки результата, выберите в меню **Сервис** пункт **Параметры**.  В диалоговом окне **Параметры** разверните узел папки **Текстовый редактор**, а затем — **C\#**.  Выберите пункт **Дополнительно** и установите флажок **Проверить результаты рефакторинга**.  
  
 В диалоговом окне **Результаты проверки** различаются два вида проблем при повторном связывании.  
  
### Ссылки, определением которых больше не является переименованный символ.  
 Этот тип проблем с повторной привязкой происходит в том случае, если ссылка больше не указывает на переименованный символ.  Рассмотрим следующий пример кода:  
  
```c#  
class Example  
{  
    private int a;  
    public Example(int b)  
    {  
        a = b;  
    }  
}  
```  
  
 При использовании оптимизации для переименования `a` в `b` открывается этого диалоговое окно.  Ссылка на переименованную переменную `a` теперь связывается с передаваемым конструктору параметром вместо привязки к полю.  
  
### Ссылки, определением которых теперь становится переименованный символ.  
 Этот тип проблем с повторной привязкой происходит в том случае, если ссылка, которая раньше не указывала на переименованный символ, теперь указывает на него.  Рассмотрим следующий пример кода:  
  
```c#  
class Example  
{  
    private static void Method(object a) { }  
    private static void OtherMethod(int a) { }  
    static void Main(string[] args)  
    {  
        Method(5);  
    }  
}  
```  
  
 При использовании оптимизации для переименования `OtherMethod` в `Method` открывается этого диалоговое окно.  Теперь в методе `Main` есть ссылка на перегруженный метод, принимающий параметр типа `int`, вместо перегруженного метода, принимающего параметр типа `object`.  
  
## См. также  
 [Использование среды разработки Visual C\#](../csharp-ide/using-the-visual-studio-development-environment-for-csharp.md)   
 [Практическое руководство. Восстановление фрагментов кода для оптимизации в C\#](../Topic/How%20to:%20Restore%20C%23%20Refactoring%20Snippets.md)