---
title: "Использование окна задач | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.paralleltasks"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "отладчик, окно параллельных задач"
ms.assetid: bd5e0612-a0dc-41cf-a7af-1e87d0d5c35f
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Использование окна задач
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Окно **Задачи** выглядит так же, как окно **Потоки**, за тем исключением, что вместо сведений о каждом потоке в нем отображаются сведения об объектах <xref:System.Threading.Tasks.Task?displayProperty=fullName>, [task\_handle](../Topic/task_group%20Class.md) или [WinJS.Promise](http://msdn.microsoft.com/library/windows/apps/br211867.aspx).  Как и потоки, задачи представляют асинхронные операции, которые могут выполняться параллельно; однако несколько задач могут выполняться в одном потоке.  Дополнительные сведения см. в разделе [Асинхронное программирование в JavaScript \(приложения для Магазина Windows\)](http://msdn.microsoft.com/library/windows/apps/hh700330.aspx).  
  
 В случае управляемого кода окно **Задачи** можно использовать при работе с объектами <xref:System.Threading.Tasks.Task?displayProperty=fullName> или ключевыми словами **await** и **async** \(**Await** и **Async** в VisualBasic\).  Дополнительные сведения о задачах в управляемом коде см. в разделе [Parallel Programming](../Topic/Parallel%20Programming%20in%20the%20.NET%20Framework.md).  
  
 В случае машинного кода окно **Задачи** можно использовать при работе с [группами задач](/visual-cpp/parallel/concrt/task-parallelism-concurrency-runtime), [параллельными алгоритмами](/visual-cpp/parallel/concrt/parallel-algorithms), [асинхронными агентами](/visual-cpp/parallel/concrt/asynchronous-agents) и [упрощенными задачами](/visual-cpp/parallel/concrt/task-scheduler-concurrency-runtime).  Дополнительные сведения о задачах в машинном коде см. в разделе [Среда выполнения с параллелизмом](/visual-cpp/parallel/concrt/concurrency-runtime).  
  
 В случае JavaScript окно "Задачи" можно использовать при работе с методом обещания .then.  
  
 Окно **Задачи** можно использовать всякий раз при переключении в режим отладчика.  Его можно открыть в меню **Отладка**, щелкнув пункт **Окна**, а затем выбрав **Задачи**.  На следующем рисунке показано окно **Задачи** в режиме по умолчанию.  
  
 ![Окно параллельных задач](../debugger/media/parallel_tasks_window.png "Parallel\_Tasks\_Window")  
  
> [!NOTE]
>  В случае управляемого кода объект <xref:System.Threading.Tasks.Task>, который имеет состояние <xref:System.Threading.Tasks.TaskStatus>, <xref:System.Threading.Tasks.TaskStatus> или <xref:System.Threading.Tasks.TaskStatus>, может не отображаться в окне "Задачи", если управляемые потоки находятся в состоянии сна или состоянии соединения.  
  
## Сведения в столбцах окна "Задачи"  
 В столбцах окна **Задачи** отображаются следующие сведения.  
  
|Имя столбца|Описание|  
|-----------------|--------------|  
|**Флаги**|Показывает, какие задачи помечены, и позволяет помечать задачи и снимать с них метки.|  
|**Значки**|Рядом с текущей задачей отображается желтая стрелка.  Текущая задача находится на самом верхнем уровне текущего потока.<br /><br /> Белая стрелка указывает прерванную задачу, т.е. задачу, которая была текущей во время вызова отладчика.<br /><br /> Значок паузы указывает задачу, замороженную пользователем.  Задачу можно заморозить или разморозить, щелкнув ее в списке правой кнопкой мыши.|  
|**Идентификатор**|Предоставленный системой номер задачи.  В машинном коде этот номер является адресом задачи.|  
|**Состояние**|Текущее состояние задачи \(запланирована, активна, заблокирована, находится в ожидании или завершена\).  Запланированная задача – это задача, которая еще не выполнялась и, следовательно, не имеет стека вызова, назначенного потока и других соответствующих сведений.<br /><br /> Активная задача — это задача, которая выполняла код, пока не была прервана в отладчике.<br /><br /> Находящаяся в ожидании задача – это задача, заблокированная вследствие ожидания сигнала события, освобождения блокировки или завершения другой задачи.<br /><br /> Заблокированная задача – это находящаяся в ожидании задача, чей поток заблокирован другим потоком.<br /><br /> Наведите указатель мыши на ячейку **Состояние** заблокированной или ожидающей задачи, чтобы увидеть дополнительные сведения о блокировке. **Warning:**  Окно **Задачи** сообщает о состоянии взаимоблокировки только для блокированных задач, использующих примитив синхронизации, который поддерживается функцией прохождения цепочки ожидания \(Wait Chain Traversal, WCT\).  Например, для заблокированного объекта <xref:System.Threading.Tasks.Task>, использующего WCT, отладчик отображает состояние **Ожидание\-Блокировка**.  Для заблокированной задачи, управляемой средой выполнения с параллелизмом, которая не поддерживает WCT, отладчик отображает состояние **Ожидание**.  Дополнительные сведения о функции WCT см. в разделе [Прохождение цепочки ожидания](http://msdn.microsoft.com/library/ms681622\(VS.85\).aspx).|  
|**Время начала**|Время, когда задача стала активной.|  
|**Длительность**|Количество секунд, в течение которого задача была активна.|  
|**Время завершения**|Время, когда задача была завершена.|  
|**Расположение**|Текущее расположение в стеке вызова задачи.  Наведите указатель мыши на эту ячейку, чтобы увидеть весь стек вызова задачи.  У запланированных задач значение в этом столбце отсутствует.|  
|**Задача**|Исходный метод и какие\-либо аргументы, которые были переданы в задачу при ее создании.|  
|**Родительский**|Идентификатор задачи, создавшей данную задачу.  Если эта ячейка пуста, то у задачи нет родительской задачи.  Это применимо только для управляемых программ.|  
|**Назначение потоков**|Идентификатор и имя потока, в котором запущена задача.|  
|**Состояние возврата**|Состояние задачи при ее завершении.  Состояние возврата может иметь одно из следующих значений: **Success** \(успешное завершение\), **Cancelled** \(отменено\) и **Error** \(ошибка\).|  
|**Домен приложения**|Для управляемого кода это домен приложения, в котором выполняется задача.|  
|**task\_group**|Для машинного кода это адрес объекта [task\_group](../Topic/task_group%20Class.md), который запланировал задачу.  Для асинхронных агентов и упрощенных задач этот столбец содержит значение 0.|  
|Процесс|Идентификатор процесса, к которому относится выполняемая задача.|  
|Асинхронное состояние|В случае управляемого кода указывает состояние задачи.  По умолчанию этот столбец скрыт.  Для отображения этого столбца откройте контекстное меню для одного из заголовков столбцов.  Выберите **Столбцы**, **AsyncState**.|  
  
 В это представление можно добавлять столбцы, щелкнув правой кнопкой мыши заголовок столбца и выбрав нужные столбцы.  \(Чтобы удалить столбцы, нужно убрать выбор.\) Можно также изменять расположение столбцов, перетаскивая их влево или вправо.  На следующем рисунке показано контекстное меню столбца.  
  
 ![Контекстное меню представлений в окне параллельных стеков](../debugger/media/parallel_tasks_contextmenu.png "Parallel\_Tasks\_ContextMenu")  
  
## Сортировка задач  
 Чтобы выполнить сортировку задач, щелкните заголовок столбца.  Например, если щелкнуть заголовок столбца **ИД**, то задачи будут отсортированы по их идентификаторам: 1,2,3,4,5 и так далее.  Чтобы изменить порядок сортировки, еще раз щелкните заголовок столбца.  Текущий столбец сортировки и порядок сортировки указывается стрелкой в столбце.  
  
## Группирование задач  
 Задачи можно группировать на основе любого столбца в представлении списка.  Например, если щелкнуть правой кнопкой мыши заголовок столбца **Состояние**, а затем выбрать **Группировать по состоянию**, то можно сгруппировать все задачи, имеющие одинаковое состояние.  Затем можно быстро просмотреть задачи, находящиеся в определенном состоянии, например в состоянии ожидания, чтобы понять причину их блокировки.  Можно также свернуть группу, которая не представляет интереса в текущем сеансе отладки.  Таким же образом можно группировать задачи по другим столбцам.  Можно установить или удалить пометку группы, просто нажав кнопку рядом с заголовком группы.  На следующем рисунке показано окно **Задачи** в режиме группирования.  
  
 ![Группированный режим в окне параллельных задач](../debugger/media/parallel_tasks_groupedmode.png "Parallel\_Tasks\_GroupedMode")  
  
## Представление родительского и дочернего объектов  
 \(Данное представление доступно только для управляемого кода.\) Щелкнув правой кнопкой мыши заголовок столбца и выбрав **Представление родительского и дочернего объектов**, можно изменить список задач, переведя его в иерархическое представление, в котором каждая дочерняя задача представляет собой вложенный узел, который можно отобразить или скрыть под его родительским узлом.  На следующем рисунке показаны задачи в представлении родительского и дочернего объектов.  
  
 ![Представление родительского и дочернего объектов в окне параллельных задач](~/debugger/media/parallel_tasks_parentchildview.png "Parallel\_Tasks\_ParentChildView")  
  
## Пометка задач  
 Можно пометить поток, в котором выполняется задача. Для этого следует выделить элемент списка задач и выбрать команду **Пометить** в контекстном меню либо щелкнуть значок флажка в первом столбце.  Если помечается несколько задач, то затем их можно сортировать по столбцу флага, чтобы вывести все помеченные задачи наверх и далее сосредоточиться только на них.  Для просмотра только помеченных задач можно также воспользоваться окном **Параллельные стеки**.  Это позволяет отфильтровывать задачи, которые не нужны для отладки.  Между сеансами отладки пометки не существуют.  
  
## Замораживание и размораживание задач  
 Чтобы заморозить поток, в котором запущена задача, можно щелкнуть правой кнопкой мыши элемент задачи в списке и выбрать **Заморозить назначенный поток**.  \(Если задача уже заморожена, то вместо этого пункта в контекстном меню появляется пункт **Разморозить назначенный поток**.\) Если поток замораживается, то он не будет выполняться при проходе по коду после текущей точки останова.  Команда **Заморозить все потоки кроме** замораживает все потоки, за исключением выполняющего указанный элемент задачи в списке.  
  
 На следующем рисунке показаны остальные пункты меню для каждой задачи.  
  
 ![Контекстное меню потоков в окне параллельных стеков](../debugger/media/parallel_tasks_contextmenu2.png "Parallel\_Tasks\_ContextMenu2")  
  
## См. также  
 [Основы отладки](../debugger/debugger-basics.md)   
 [Отладка управляемого кода](../debugger/debugging-managed-code.md)   
 [Parallel Programming](../Topic/Parallel%20Programming%20in%20the%20.NET%20Framework.md)   
 [Среда выполнения с параллелизмом](/visual-cpp/parallel/concrt/concurrency-runtime)   
 [Использование окна "Параллельные стеки"](../debugger/using-the-parallel-stacks-window.md)   
 [Пошаговое руководство. Отладка параллельного приложения](../debugger/walkthrough-debugging-a-parallel-application.md)