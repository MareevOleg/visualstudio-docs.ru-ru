---
title: Узнайте, как Отладка многопоточных приложений
description: Отладка с помощью окна "Параллельные стеки" и "контроль параллельных данных" в Visual Studio
ms.custom: H1HackMay2017
ms.date: 11/16/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- multithreaded debugging, tutorial
- tutorials, multithreaded debugging
ms.assetid: 62df746b-b0f6-4df4-83cf-b1d9d2e72833
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2a6ded522a917dd7207da7731850303535e19fdb
ms.sourcegitcommit: 54c65f81a138fc1e8ff1826f7bd9dcec710618cc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2018
ms.locfileid: "51948989"
---
# <a name="get-started-debugging-multithreaded-applications"></a>Начало отладки многопоточных приложений
Visual Studio предоставляет несколько средств и элементы пользовательского интерфейса для отладки многопоточных приложений. Этом руководстве показано, как использовать маркеры потоков **Параллельные стеки** окне **контроль параллельных данных** окна, условные точки останова и фильтр точки останова. Завершение изучения этого учебника вы ознакомитесь с возможностями Visual Studio для отладки многопоточных приложений.

| | |
|---------|---------|
| ![значок кинокамеры для видео](../install/media/video-icon.png "Просмотреть видео") | [Ознакомьтесь с видео](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Debugging-Multi-threaded-Apps-in-Visual-Studio-2017-MoZPKMD6D_111787171) на многопотоковая отладка, показывающая те же действия. |

Дополнительных сведений об использовании средств отладки многопоточных следующие две темы:

- Для использования **место отладки** инструментов и **потоков** окно, см. в разделе [Пошаговое руководство: отладка многопоточного приложения](../debugger/how-to-use-the-threads-window.md).

- Пример, использующий <xref:System.Threading.Tasks.Task> (управляемый код) и среда выполнения с параллелизмом (C++), см. в разделе [Пошаговое руководство: отладка параллельного приложения](../debugger/walkthrough-debugging-a-parallel-application.md). Общие отладки советы, которые применяются к типам наиболее многопоточного приложения приведены в этой теме и данное действие.
  
Проект многопоточного приложения необходимо сначала. Ниже приведен пример.  
  
## <a name="create-a-multithreaded-app-project"></a>Создайте проект многопоточного приложения  
  
1.  В меню **Файл** выберите пункт **Создать** > **Проект**.  
  
     Откроется диалоговое окно **Новый проект** .  
  
2.  Выберите язык: **Visual C#** , **Visual C++**, или **Visual Basic**.  
  
3.  В разделе **Windows Desktop**, выберите **консольное приложение**.  
  
4.  В **имя** введите MyThreadWalkthroughApp.  
  
5.  Нажмите кнопку **ОК**.  
  
     Появится новый проект консольного приложения. После создания проекта, откроется файл исходного кода. В зависимости от языка, вы выбрали, исходный файл может вызываться *Program.cs*, *MyThreadWalkthroughApp.cpp*, или *Module1.vb*.  
  
6.  Удалите код, который отображается в исходном файле и замените его соответствующем примере кода ниже.

    ```csharp
    using System;
    using System.Threading;

    public class ServerClass
    {

        static int count = 0;
        // The method that will be called when the thread is started.
        public void InstanceMethod()
        {
            Console.WriteLine(
                "ServerClass.InstanceMethod is running on another thread.");

            int data = count++;
            // Pause for a moment to provide a delay to make
            // threads more apparent.
            Thread.Sleep(3000);
            Console.WriteLine(
                "The instance method called by the worker thread has ended.");
        }
    }

    public class Simple
    {
        public static void Main()
        {
            for (int i = 0; i < 10; i++)
            {
                CreateThreads();
            }
        }
        public static void CreateThreads()
        {
            ServerClass serverObject = new ServerClass();

            Thread InstanceCaller = new Thread(new ThreadStart(serverObject.InstanceMethod));
            // Start the thread.
            InstanceCaller.Start();

            Console.WriteLine("The Main() thread calls this after "
                + "starting the new InstanceCaller thread.");

        }
    }
    ```

    ```C++
    #include "stdafx.h"
    #include <thread>
    #include <iostream>
    #include <vector>

    using namespace;

    int count = 0;

    void doSomeWork() {

        cout << "The doSomeWork function is running on another thread." << endl;
        int data = count++;
        // Pause for a moment to provide a delay to make
        // threads more apparent.
        this_thread::sleep_for(chrono::seconds(3));
        cout << "The function called by the worker thread has ended." << endl;
    }

    int main() {
        vector<thread> threads;

        for (int i = 0; i < 10; ++i) {

            threads.push_back(thread(doSomeWork));
            cout << "The Main() thread calls this after starting the new thread" << endl;
        }

        for (auto& thread : threads) {
            thread.join();
        }

        return 0;
    }
    ```

    ```VB
    Imports System.Threading

    Public Class ServerClass
        ' The method that will be called when the thread is started.
        Public count = 0
        Public Sub InstanceMethod()
            Console.WriteLine(
                    "ServerClass.InstanceMethod is running on another thread.")

            Dim data = count + 1
            ' Pause for a moment to provide a delay to make
            ' threads more apparent.
            Thread.Sleep(3000)
            Console.WriteLine(
                    "The instance method called by the worker thread has ended.")
        End Sub

    End Class

    Public Class Simple

        Public Shared Sub Main()

            Dim ts As New ThreadStarter
            For index = 1 To 10
                ts.CreateThreads()
            Next

        End Sub

    End Class
    Public Class ThreadStarter
        Public Sub CreateThreads()
            Dim serverObject As New ServerClass()

            ' Create the thread object, passing in the
            ' serverObject.InstanceMethod method using a
            ' ThreadStart delegate.
            Dim InstanceCaller As New Thread(AddressOf serverObject.InstanceMethod)

            ' Start the thread.
            InstanceCaller.Start()

            Console.WriteLine("The Main() thread calls this after " _
                        + "starting the new InstanceCaller thread.")

        End Sub
    End Class
    ```
  
7.  На **файл** меню, выберите **сохранить все**.  
  
## <a name="debug-the-multithreaded-app"></a>Отладка многопоточных приложений  
  
1. В редакторе исходного кода искать его в следующих фрагментах кода: 
  
    ```csharp  
    Thread.Sleep(3000);  
    Console.WriteLine();  
    ```  
  
    ```C++  
    this_thread::sleep_for(chrono::seconds(3));
    cout << "The function called by the worker thread has ended." << endl; 
    ```  

    ```VB
    Thread.Sleep(3000)
    Console.WriteLine()
    ```

1. Левой кнопкой мыши щелкните в левом поле `Thread.Sleep` или `this_thread::sleep_for` инструкцию, чтобы добавить новую точку останова.  
  
    Во внутренней области красный кружок указывает, что установлена точка останова в этом расположении. 
  
2. На **Отладка** меню, выберите **начать отладку** (**F5**).  
  
    Visual Studio создает решение, приложение начинает выполняться с подключенным отладчиком, и затем приложение останавливается в точке останова.  
  
3. В редакторе исходного кода найдите строку, содержащую точку останова.
  
### <a name="ShowThreadsInSource"></a>Обнаружить маркер потока  

1.  На панели инструментов отладки выберите **Показать потоки в исходном коде** кнопку ![Показать потоки в исходном коде](../debugger/media/dbg-multithreaded-show-threads.png "ThreadMarker").

2. Нажмите клавишу **F11** один раз, чтобы перейти к строке кода отладчиком по одному.
  
3.  Посмотрите на переплет в левой части окна. В этой строке, вы увидите *маркер потока* значок ![маркер потока](../debugger/media/dbg-thread-marker.png "ThreadMarker") , аналогичный два витой потока. маркер потока указывает, что некий поток остановлен в этом месте.

    Маркер потока может быть частично скрыты с помощью точки останова. 
  
4.  Наведите указатель мыши на маркер потока. Появится подсказка о том, имя и Идентификационный номер для каждого потока. В этом случае имя является, вероятно, `<noname>`. 
  
5.  Выберите маркер потока, чтобы просмотреть доступные параметры в контекстном меню.
    
### <a name="ParallelStacks"></a>Просмотр расположения потока

В **Параллельные стеки** окно, можно переключаться между представление "Потоки" и (для программирования на основе задач) представление "задачи" и вы можете просмотреть стек вызовов для каждого потока. В этом приложении можно использовать представление "Потоки".

1. Откройте **Параллельные стеки** окно, выбрав **Отладка** > **Windows** > **Параллельные стеки**. Вы увидите примерно следующее. Точные сведения будут различаться в зависимости от текущего расположения, каждый поток, оборудования и языка программирования.

    ![Параллельных стеков окно](../debugger/media/dbg-multithreaded-parallel-stacks.png "ParallelStacksWindow")

    В этом примере слева направо нам просматривать эту информацию для управляемого кода:
    
    - Основной поток (слева) остановлена на `Thread.Start`, где точка останова обозначается значок маркера потока ![маркер потока](../debugger/media/dbg-thread-marker.png "ThreadMarker").
    - Два потока ввода `ServerClass.InstanceMethod`, один из которых является текущий поток (желтая стрелка), пока другой поток остановлен в `Thread.Sleep`.
    - Также запускает новый поток (справа), но остановлена на `ThreadHelper.ThreadStart`.

2.  Щелкните правой кнопкой мыши записи в **Параллельные стеки** окно, чтобы просмотреть доступные параметры в контекстном меню.

    Можно выполнять различные действия из этих меню щелкните правой кнопкой мыши, но в этом руководстве мы покажем несколько из этих сведений в **контроль параллельных данных** окна (в следующих разделах).

    > [!NOTE]
    > Чтобы просмотреть представление списка со сведения для каждого потока, используйте **потоков** окно вместо этого. См. в разделе [Пошаговое руководство: отладка многопоточного приложения](../debugger/how-to-use-the-threads-window.md).

### <a name="set-a-watch-on-a-variable"></a>Установка контрольных значений для переменной

1. Откройте **контроль параллельных данных** окно, выбрав **Отладка** > **Windows** > **контроль параллельных данных**  >  **Контроль параллельных данных 1**.

2. Выберите ячейку, где встречается `<Add Watch>` текста (или пустой заголовок ячейки в четвертом столбце) и введите `data`.

    В окне отображаются значения для переменной данных для каждого потока.

3. Выберите ячейку, где встречается `<Add Watch>` текста (или пустой заголовок ячейки в столбце 5-й) и введите `count`.

    Значения для `count` переменную для каждого потока отображаются в окне. Если вы не видите еще такой большой объем сведений, попробуйте нажатие **F11** несколько раз, чтобы продолжить выполнение потоков в отладчике.

    ![Параллельное окно контрольных значений](../debugger/media/dbg-multithreaded-parallel-watch.png "ParallelWatchWindow")

4. Щелкните правой кнопкой мыши одну из строк в окне, чтобы просмотреть доступные параметры.

### <a name="flag-and-unflag-threads"></a>Установка и снятие отметки для потока  
Можно пометить поток, чтобы отслеживать важные потоки и игнорировать других потоков.  
  
1. В **контроль параллельных данных** окна, удерживайте нажатой **Shift** ключ и выбрать несколько строк.

2. Щелкните правой кнопкой мыши и выберите **флаг**.

    Все выбранные потоки, помечаются. Теперь можно фильтровать на показ только помеченных потоков.
  
3.  В **контроль параллельных данных** выберите **Показывать только отмеченные потоки** кнопку ![Показывать отмеченные потоки](../debugger/media/dbg-threads-show-flagged.png "ThreadMarker").  
  
    В списке отображаются только помеченных потоков.

    > [!TIP]
    > После Вы отметили некоторые потоки, можно правой кнопкой мыши строку кода в редакторе кода и выбрать **Запустить помеченные потоки до курсора**. Убедитесь в том, что выбрать достигнет кода, что все отмеченные потоки. Visual Studio будет приостанавливать потоки в выбранной строке кода, что упрощает для управления порядком выполнения по [Замораживание и размораживание потоков](#bkmk_freeze).

4.  Выберите **Показывать только отмеченные потоки** кнопку еще раз, чтобы снова переключиться в **Показывать все потоки** режим.
    
5. Снять отметку с потока, щелкните правой кнопкой мыши один или несколько отмеченных потоков в **контроль параллельных данных** и выберите **снять отметку**.

### <a name="bkmk_freeze"></a> Замораживание и размораживание потоков выполнения 

> [!TIP]
> Можно заморозить или разморозить (приостанавливать и возобновлять) потоки можно управлять порядком, в котором потоки выполнения работы. Это может помочь устранить проблемы параллелизма, например взаимоблокировки и состояния гонки.
   
1.  В **контроль параллельных данных** окно с всех выбранных строк, щелкните правой кнопкой мыши и выберите **закрепить**.

    Во втором столбце значок паузы отображается для каждой строки. Значок паузы указывает, что поток заморожен.

2.  Снимите все остальные строки, выбрав только одну строку.

3.  Щелкните правой кнопкой мыши строку и выберите **Разморозить**.

    Значок паузы исчезает на этой строке, указывающее, что поток не приостановлен.

4.  Переключитесь в редактор кода и нажмите клавишу **F11**. Только незафиксированных поток выполняется.

    Приложение также может создавать экземпляры некоторых новых потоков. Все новые потоки без отметки и заморожены.

### <a name="bkmk_follow_a_thread"></a> Выполните один поток с условные точки останова

Можно следить за выполнением из одного потока в отладчике. Одним из способов сделать это является замораживание потоков, которые вас не интересуют. В некоторых сценариях необходимо следовать один поток не замораживание других потоков, например воспроизвести определенной ошибки. Чтобы выполнить поток без замораживание других потоков, необходимо избегать Приостановка выполнения кода, за исключением случаев, в том потоке, которые вас интересуют. Это можно сделать, задав [условную точку останова](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression).

Можно установить точки останова на различных условиях, например имя или идентификатор потока. Это может быть полезно — задать условие на данные, которые вы знаете, является уникальным для каждого потока. Это распространенный сценарий отладки, который вас интересует более в некоторые данные определенного типа чем любого конкретного потока.

1. Щелкните правой кнопкой мыши созданную ранее точку останова и выберите **условия**.

2. В **параметры точки останова** окно, введите `data == 5` для условного выражения.

    ![Условную точку останова](../debugger/media/dbg-multithreaded-conditional-breakpoint.png "ConditionalBreakpoint")

    > [!TIP]
    > Если вас интересуют более конкретного потока, затем используйте имя или идентификатор потока для условия. Для этого в **параметры точки останова** выберите **фильтра** вместо **условное выражение**и следуйте советам фильтра. Вам может потребоваться имя потоков в коде приложения как потоки идентификаторы изменить при повторном запуске отладчика.

3. Закрыть **параметры точки останова** окна.

4. Выбор перезагрузки ![перезапустить приложение](../debugger/media/dbg-tour-restart.png "RestartApp") кнопку, чтобы перезапустить сеанс отладки.

    Вы будете Приостановка выполнения кода в потоке, где значение переменной данных — 5. В **контроль параллельных данных** окна, найдите желтая стрелка, указывающий текущий контекст отладчика.

5. Теперь вы можете шаг с обходом кода (**F10**) и шаг с заходом в код (**F11**) и следить за выполнением один поток.

    Пока условие точки останова является уникальным для потока, и отладчик не достигнет других точек останова в других потоках (может потребоваться отключить их), вы выполните шаг с обходом кода и пошаговое выполнение кода без переключения для других потоков.

    > [!NOTE]
    > При переходе отладчика будет выполняться все потоки. Тем не менее отладчик не будет останавливаться в код в других потоках, если один из других потоков достигает точки останова. 
  
## <a name="see-also"></a>См. также  
[Отладка многопоточных приложений](../debugger/debug-multithreaded-applications-in-visual-studio.md)  
[Практическое руководство. Переключение на другой поток при отладке](../debugger/how-to-switch-to-another-thread-while-debugging.md)  
[Практическое: использование окна параллельных стека](../debugger/using-the-parallel-stacks-window.md)  
[Практическое руководство. Использование окна "Контроль параллельных данных"](../debugger/how-to-use-the-parallel-watch-window.md)  
