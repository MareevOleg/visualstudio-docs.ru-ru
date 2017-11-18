---
title: "Практическое руководство. Просмотр и изменение кода с помощью окна \"Показать определение\" (ALT+F12) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45f3dd20-902a-4047-8cca-9f18216123f4
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: ghogen
translation.priority.ht:
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 47057e9611b824c17077b9127f8d2f8b192d6eb8
ms.openlocfilehash: e4b64d7c82e28c5ba58157ea729465eef84f52a4
ms.contentlocale: ru-ru
ms.lasthandoff: 05/13/2017

---
# <a name="how-to-view-and-edit-code-by-using-peek-definition-altf12"></a>Практическое руководство. Просмотр и изменение кода с помощью окна "Показать определение" (ALT+F12)
Команду **Показать определение** можно использовать для просмотра и изменения определений кода без переключения с текущего кода, над которым работает пользователь. Команды **Показать определение** и **Перейти к определению** отображают одни и те же сведения, но команда **Перейти к определению** отображает их во всплывающем окне, а команда **Перейти к определению** — в отдельном окне. При вызове команды **Перейти к определению** текущий контекст (т. е. активное окно кода, текущая строка и позиция курсора) переключается на окно кода определения. С помощью функции **Показать определение** можно просмотреть и изменить определение, а также переместиться в другое место внутри файла определения, оставаясь при этом на месте в изначально открытом файле исходного кода.  
  
 Команду **Показать определение** можно применить при работе с кодом C#, Visual Basic и C++. В Visual Basic в разделе **Показать определение** отображается ссылка на **обозреватель объектов** для символов, которые не имеют метаданных определения (например, встроенных типов .NET Framework).  
  
> [!IMPORTANT]
>  В версиях Express приложения Visual Studio 2013 данную команду использовать нельзя.  
  
## <a name="working-with-peek-definition"></a>Работа с окном "Показать определение"  
  
#### <a name="to-open-a-peek-definition-window"></a>Открытие окна "Показать определение"  
  
1.  Чтобы открыть окно **Показать определение**, откройте контекстное меню для нужного метода. (Сочетание клавиш: ALT+F12)  
  
     На этой иллюстрации представлено окно **Показать определение** для метода с именем `Print()`:  
  
     ![Окно показа](../ide/media/peekwindow.png "PeekWindow")  
  
     Окно определения отображается под строкой `printer.Print("Hello World!")` в исходном файле. Данное окно не скрывает никакие фрагменты кода в исходном файле. Строки,следующие за строкой `printer.Print("Hello World!")`, отображаются под окном определения.  
  
2.  Можно переместить курсор в другую точку окна определения кода. Сохраняется возможность перемещаться по исходному окну кода выше или ниже окна определения.  
  
3.  Можно скопировать строку из окна определения и вставить ее в исходный код. Можно также перетащить строку из окна определения в исходный код, не удаляя ее из окна определения.  
  
4.  Чтобы закрыть окно определения, нажмите клавишу ESC или кнопку **Закрыть** на вкладке окна определения.  
  
#### <a name="to-open-a-peek-definition-window-from-within-a-peek-definition-window"></a>Открытие окна "Показать определение" из окна "Показать определение"  
  
-   Если окно **Показать определение** уже открыто, можно применить функцию **Показать определение** к коду в данном окне. В этом случае откроется еще одно окно определения. Рядом с вкладкой окна определения отображается набор точек навигации, который можно использовать для перехода из одного окна определения в другое. Всплывающая подсказка для каждой точки отображает имя файла и путь к файлу определения, представляемого данной точкой.  
  
     ![Окно показа внутри другого окна показа](../ide/media/peekwithinpeek.png "PeekWithinPeek")  
  
#### <a name="to-use-peek-definition-with-multiple-results"></a>Использование функции "Показать определение" с несколькими результатами  
  
-   При использовании окна **Показать определение** в коде, который содержит более одного определения (например, разделяемые классы), список результатов отображается справа от представления определения кода. Можно выбрать любой результат в списке, чтобы открыть его определение.  
  
     ![Окно показа с несколькими результатами](../ide/media/peekmultiple.png "PeekMultiple")  
  
#### <a name="to-edit-inside-the-peek-definition-window"></a>Правка содержимого окна "Показать определение"  
  
-   Когда пользователь приступает к редактированию содержимого окна **Показать определение**, изменяемый файл автоматически открывается в отдельной вкладке в редакторе кода, отражая уже внесенные изменения. Если затем содержимое окна **Показать определение** будет изменено путем добавления данных, отмены и сохранения внесенных изменений, эти изменения будут отражены на этой вкладке. Даже если окно будет закрыто без сохранения изменений, у пользователя останется возможность добавить элементы, отменить выполненное изменение и сохранить дополнительные изменения при помощи этой вкладки с того этапа, на котором окно было закрыто.  
  
     ![Редактирование в окне показа](../ide/media/peekedit.png "PeekEdit")  
  
#### <a name="to-use-keyboard-shortcuts-for-peek-definition"></a>Использование сочетаний клавиш при работе с окном "Показать определение"  
  
-   При работе с окном **Показать определение** можно использовать следующие сочетания клавиш.  
  
    |Функция|Сочетание клавиш|  
    |-------------------|-----------------------|  
    |Открытие окна определения|ALT+F12|  
    |Закрытие окна определения|ESC|  
    |Преобразование окна определения в стандартную вкладку документа|SHIFT+ALT+HOME|  
    |Переход из одного окна определения в другое|CTRL+ALT+- и CTRL+ALT+=|  
    |Переключение с одного результата на другой|F8 и SHIFT+F8|  
    |Переключение между окном редактора кода и окном определения|SHIFT+ESC|  
  
    > [!NOTE]
    >  Для редактирования кода в окне **Показать определение** можно также использовать те же сочетания клавиш, что и в любом другом окне Visual Studio.  
  
## <a name="see-also"></a>См. также  
 [Советы по повышению производительности](../ide/productivity-tips-for-visual-studio.md)