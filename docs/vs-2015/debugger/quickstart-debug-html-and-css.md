---
title: 'Краткое руководство: Отладка HTML и CSS | Документация Майкрософт'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.WebClient.DomExplorer
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging, CSS
- debugging, HTML
- debugging, JavaScript [Windows Store apps]
- DOM Explorer [Windows Store apps]
ms.assetid: 6d156cff-36c6-425a-acf8-e1f02d4f7869
caps.latest.revision: 104
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 710bafe2383d95358ba06a287a300d9aea7baf66
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51729980"
---
# <a name="quickstart-debug-html-and-css"></a>Краткое руководство по отладке HTML и CSS
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Применяется к Windows и Windows Phone] (.. /Image/windows_and_phone_content.PNG «windows_and_phone_content»)  
  
 Для приложений, созданных с использованием языка JavaScript, Visual Studio позволяет выполнять комплексную отладку, которая включает в себя функции, знакомые разработчикам Internet Explorer и Visual Studio. Эти возможности поддерживаются для приложений [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)], приложений Магазина Windows Phone и приложений, созданных с помощью инструментов Visual Studio для Apache Cordova.  
  
 С помощью интерактивной модели отладки, предоставляемой средствами проверки DOM, вы можете просмотреть и изменить визуализируемый код HTML и CSS. Все это можно делать без остановки и перезапуска отладчика.  
  
 В этом разделе.  
  
- [Проверка динамической модели DOM](#InspectingDOM)  
  
- [Selecting elements](#SelectingElements)  
  
  Дополнительные сведения об использовании проводника DOM см. в следующих разделах:  
  
- [Отладка стилей CSS с использованием проводника DOM](../debugger/debug-css-styles-using-dom-explorer.md)  
  
- [Отладка макета с использованием проводника DOM](../debugger/debug-layout-using-dom-explorer.md)  
  
- [Просмотр прослушивателей событий DOM](../debugger/view-dom-event-listeners.md)  
  
- [Обновление приложения (JavaScript)](../debugger/refresh-an-app-javascript.md)  
  
- [Отладка элемента управления WebView](../debugger/debug-a-webview-control.md)  
  
  Сведения о других возможностях отладки JavaScript, таких как использование окна консоли JavaScript и задание точек останова, см. в разделе [краткое руководство: Отладка JavaScript](../debugger/quickstart-debug-javascript-using-the-console.md) и [отладка приложений в Visual Studio](../debugger/debug-store-apps-in-visual-studio.md).  
  
##  <a name="InspectingDOM"></a> Проверка динамической модели DOM  
 Проводник DOM содержит представление отображаемой страницы. В проводнике можно менять значения и немедленно просматривать результаты. Это позволяет тестировать изменения без остановки и перезапуска отладчика. Исходный код в проекте не меняется, если разработчик выполняет какие-либо операции с этой страницей, используя данный метод, поэтому, найдя места для внесения исправлений в код, вы вносите исправления в исходный код.  
  
> [!TIP]
>  Чтобы не останавливать и не перезапускать отладчик при внесении изменений в исходный код, вы можете обновить приложение, нажав кнопку **Обновить приложение Windows** на панели инструментов "Отладка" (или клавишу F4). Дополнительные сведения см. в разделе [обновление приложения (JavaScript)](../debugger/refresh-an-app-javascript.md).  
  
 Проводник DOM позволяет решать следующие задачи.  
  
- Навигация по поддереву элементов DOM и проверка отображаемого кода HTML, CSS и JavaScript.  
  
- Динамическое изменение атрибутов и стилей CSS отображаемых элементов с немедленным просмотром результатов.  
  
- Проверка применения стилей CSS к элементам страницы и трассировка примененных правил.  
  
  В процессе отладки приложений часто требуется выбрать те или иные элементы в проводнике DOM. При выборе элемента значения, отображаемые на вкладках с правой стороны проводника DOM, автоматически обновляются, отражая текущее состояние выбранного элемента в проводнике DOM. Вкладки следующие: **Стили**, **Вычисленные**, **Макет**. Приложения Магазина Windows также поддерживают вкладки **События** и **Изменения** . Дополнительные сведения о выборе элементов см. в разделе [Selecting elements](#SelectingElements).  
  
> [!TIP]
>  Если окно проводника DOM закрыто, выберите **Отладка**>**Окна** > **Проводник DOM** , чтобы повторно открыть его. Окно отображается только во время сеанса отладки скрипта.  
  
 В описанной ниже процедуре мы выполним отладку приложения в интерактивном режиме с помощью обозревателя DOM. Мы создадим приложение, использующее элемент управления `FlipView` , и отладим это приложение. В приложении имеется несколько ошибок.  
  
> [!WARNING]
>  В качестве примера здесь используется приложение Магазина Windows. Эти же функции поддерживаются для Cordova, но приложение будет другим.  
  
#### <a name="to-debug-by-inspecting-the-live-dom"></a>Отладка путем проверки динамической модели DOM  
  
1. Создайте новое решение в Visual Studio, выбрав **Файл** > **Новый проект**.  
  
2. Выберите **JavaScript** > **Магазин**, а затем выберите либо **Приложения Windows** , либо **Приложения Windows Phone**, затем выберите **Пустое приложение**.  
  
3. Введите имя проекта, например `FlipViewApp`, и нажмите кнопку **ОК** , чтобы создать приложение.  
  
4. Добавьте следующий код в элемент ТЕЛО файла default.html.  
  
   ```html  
   <div id="flipTemplate" data-win-control="WinJS.Binding.Template"  
            style="display:none">  
       <div class="fixedItem" >  
           <img src="#" data-win-bind="src: flipImg" />  
       </div>  
   </div>  
   <div id="fView" style="width:100px;height:100px"  
       data-win-control="WinJS.UI.FlipView" data-win-options="{  
       itemDataSource: Data.items.dataSource, itemTemplate: flipTemplate }">  
   </div>  
   ```  
  
5. Откройте файл default.css и добавьте следующий код CSS:  
  
   ```css  
   #fView {  
       background-color:#0094ff;  
       height: 100%;  
       width: 100%;  
       margin: 25%;  
   }  
   ```  
  
6. Замените код в файле default.js следующим кодом:  
  
   ```javascript  
   (function () {  
       "use strict";  
  
       var app = WinJS.Application;  
       var activation = Windows.ApplicationModel.Activation;  
  
       var myData = [];  
       for (var x = 0; x < 4; x++) {  
           myData[x] = { flipImg: "/images/logo.png" }  
       };  
  
       var pages = new WinJS.Binding.List(myData, { proxy: true });  
  
       app.onactivated = function (args) {  
           if (args.detail.kind === activation.ActivationKind.launch) {  
               if (args.detail.previousExecutionState !==  
               activation.ApplicationExecutionState.terminated) {  
                   // TODO: . . .  
               } else {  
                   // TODO: . . .  
               }  
               args.setPromise(WinJS.UI.processAll());  
  
               updateImages();  
           }  
       };  
  
       function updateImages() {  
  
           pages.setAt(0, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223195" });  
           pages.setAt(1, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223196" });  
           pages.setAt(2, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223197" });  
       };  
  
       app.oncheckpoint = function (args) {  
       };  
  
       app.start();  
  
       var publicMembers = {  
           items: pages  
       };  
  
       WinJS.Namespace.define("Data", publicMembers);  
  
   })();  
   ```  
  
    На следующем рисунке показано, что именно мы хотим видеть, если запустим это приложение в эмуляторе телефона (аналогично выглядит в имитаторе). Тем не менее для доведения приложения до такого состояния нам потребуется сначала устранить несколько ошибок.  
  
    ![Приложение FlipView с ожидаемым результатами](../debugger/media/js-dom-appfixed.png "JS_DOM_AppFixed")  
  
7. Выберите либо **Имитатор** , либо **Emulator 8.1 WVGA 512MB (RU)** из раскрывающегося списка рядом с кнопкой **Начать отладку** на панели инструментов **Отладка** .  
  
    ![Список целевых объектов отладки выберите](../debugger/media/js-select-target.png "JS_Select_Target")  
  
8. Выберите **Отладка** > **Начать отладку**или нажмите клавишу F5, чтобы запустить приложение в режиме отладки.  
  
    При этом приложение запустится в имитаторе или эмуляторе телефона, но экран будет практически пустым, поскольку в стилях имеется несколько ошибок. Первое изображение `FlipView` появляется в малом квадрате около середины экрана.  
  
9. Если приложение выполняется в имитаторе, выберите команду панели инструментов **Изменить разрешение** в правой части имитатора, чтобы настроить разрешение экрана 1280 х 800. Таким образом вы обеспечите соответствие значений, которые вы видите в имитаторе, значениям, отображаемым в перечисленных ниже шагах.  
  
10. Переключитесь в Visual Studio и выберите вкладку **Проводник DOM** .  
  
    > [!TIP]
    >  Для переключения между Visual Studio и работающим приложением можно использовать сочетание клавиш Alt+Tab или клавишу F12.  
  
11. В окне проводника DOM выберите элемент DIV для раздела с идентификатором `"fView"`. Для просмотра и выбора правильного элемента DIV используйте клавиши со стрелкой. (С помощью клавиши со стрелкой вправо можно просмотреть дочерние элементы выбранного элемента.)  
  
     ![Проводник DOM](../debugger/media/js-dom-explorer.png "JS_DOM_Explorer")  
  
    > [!TIP]
    >  Можно также выбрать элемент DIV в левом нижнем углу окна консоли JavaScript, введя `select(fView)` в строке ввода ">>" и нажав клавишу ВВОД.  
  
     Значения, отображаемые на вкладках в правой части проводника DOM, автоматически обновляются, отражая состояние текущего элемента в проводнике DOM.  
  
12. Выберите вкладку **Вычисляемый** в правой части.  
  
     На этой вкладке отображается вычисляемое или конечное значение каждого свойства выбранного элемента DOM.  
  
13. Откройте правило CSS для высоты. Обратите внимание на наличие встроенного стиля со значением 100 пикс., который не соответствует значению высоты 100 %, установленному для селектора CSS `#fView` . Зачеркнутый текст для селектора `#fView` означает, что встроенный стиль обладает приоритетом перед этим стилем.  
  
     На следующем рисунке показана вкладка **Вычисленные** .  
  
     ![Вкладка "вычисляемый обозревателя DOM"](../debugger/media/js-dom-explorer-computed.png "JS_DOM_Explorer_Computed")  
  
14. В главном окне проводника DOM дважды щелкните встроенный стиль высоты и ширины элемента DIV `fView` . Теперь можно изменить здесь значения. В этом сценарии требуется удалить их полностью.  
  
15. Выберите `width: 100px;height: 100px;`и нажмите клавишу DELETE, а затем клавишу ВВОД. После нажатия клавиши ВВОД новые значения немедленно отражаются в имитаторе или эмуляторе телефона, хотя сеанс отладки не был остановлен.  
  
    > [!IMPORTANT]
    >  Поскольку можно обновить атрибуты в окне проводника DOM, можно также обновить значения, отображаемые на вкладках **Стили**, **Вычисленные**и **Макет** . Дополнительные сведения см. в разделе [стилей CSS, отладка с использованием проводника DOM](../debugger/debug-css-styles-using-dom-explorer.md) и [макета отладки с использованием проводника DOM](../debugger/debug-layout-using-dom-explorer.md).  
  
16. Перейдите к приложению, выбрав имитатор или эмулятор телефона или использовав сочетание клавиш Alt+Tab.  
  
     Теперь элемент управления `FlipView` больше размера экрана имитатора или эмулятора телефона. Это незапланированный результат. Чтобы изучить вопрос, вернитесь в Visual Studio.  
  
17. В проводнике DOM снова перейдите на вкладку **Вычисляемый** и откройте правило высоты. Элемент fView по-прежнему показывает значение 100 % (как и ожидалось от CSS), но вычисляемое значение равно высоте экрана имитатора (например, 800 пикс. или 667,67 пикс.), а это не соответствует нашим требованиям к приложению. Для изучения вопроса можно удалить высоту и ширину элемента DIV `fView` .  
  
18. На вкладке **Стили** снимите флажки свойств высоты и ширины для селектора CSS `#fView` .  
  
     На вкладке **Вычисляемый** теперь отображается высота 400 пикс. Информация указывает на то, что это значение берется из селектора .win-flipview, заданного в файле ui-dark.css, представляющем собой CSS-файл платформы.  
  
19. Вернитесь к приложению.  
  
     Результат улучшился. Однако есть еще одна проблема, которую следует устранить; поля отображаются слишком большими.  
  
20. Чтобы изучить вопрос, переключитесь в Visual Studio и выберите вкладку **Макет** для просмотра рамочной модели элемента.  
  
     На вкладке **Макет** можно увидеть следующие значения.  
  
    - Для имитатора: 320 пикс. (смещение) и 320 пикс. (поле).  
  
    - Для эмулятора телефона: 100 пикс. (смещение) и 100 пикс. (поле).  
  
      На следующем рисунке показано, как выглядит вкладка **Макет** , если используется эмулятор телефона (смещение и поле 100 пикс).  
  
      ![Вкладка макета проводника DOM](../debugger/media/js-dom-explorer-layout.png "JS_DOM_Explorer_Layout")  
  
      Это неправильно. На вкладке **Вычисленные** также отображаются те же значения полей.  
  
21. Перейдите на вкладку **Стили** и найдите селектор CSS `#fView` . Здесь вы увидите значение 25 % для свойства **поле** .  
  
22. Выберите 25 %, измените это значение на 25 пикс. и нажмите клавишу ВВОД.  
  
23. На вкладке **Стили** выберите правило высоты для селектора .win-flipview, измените значение 400 пикс. на 500 пикс. и нажмите клавишу ВВОД.  
  
24. Вернитесь к приложению. Теперь элементы размещены правильно. Чтобы внести исправления в источник и обновить приложение, не останавливая и не перезапуская отладчик, выполните следующую процедуру.  
  
#### <a name="to-refresh-your-app-while-debugging"></a>Обновление приложения во время отладки  
  
1.  Пока приложение выполняется, переключитесь на Visual Studio  
  
2.  Откройте файл default.html и внесите исправления в исходный код, изменив высоту и ширину элемента DIV `"fView"` на 100 %.  
  
3.  Нажмите кнопку **Обновить приложение Windows** на панели инструментов "Отладка" (или нажмите F4). Кнопка выглядит следующим образом: ![кнопкой "Обновить Windows-приложение"](../debugger/media/js-refresh.png "JS_Refresh").  
  
     Страницы приложения перезагружаются, имитатор или эмулятор телефона снова отображается на переднем плане.  
  
     Дополнительные сведения о функции обновления, см. в разделе [обновление приложения (JavaScript)](../debugger/refresh-an-app-javascript.md).  
  
##  <a name="SelectingElements"></a> Selecting elements  
 Во время отладки приложения элементы модели DOM можно выбирать тремя способами:  
  
- нажатием элементов непосредственно в окне проводника DOM (или с помощью клавиш со стрелками);  
  
- с помощью кнопки **Выбор элемента** (Ctrl+B);  
  
- с помощью кнопки `select` , входящей в [JavaScript Console commands](../debugger/javascript-console-commands.md).  
  
  При выборе элементов с помощью окна проводника DOM и наведении указателя мыши на элемент соответствующий элемент выделяется в запущенном приложении. Чтобы выбрать элемент, необходимо щелкнуть по нему в проводнике DOM (или воспользоваться для выбора элементов клавишами со стрелками). Элементы в проводнике DOM можно также выбирать с помощью кнопки **Выбрать элемент** . На следующем рисунке показана кнопка **Выбор элемента** .  
  
  ![Нажмите кнопку "элемент" в проводнике DOM](../debugger/media/js-dom-select-element-button.png "JS_DOM_Select_Element_Button")  
  
  При нажатии кнопки **Выбрать элемент** (или сочетания клавиш CTRL+B) меняется режим выделения, то есть элемент в проводнике DOM можно выделить, щелкнув по нему в запущенном приложении. По щелчку режим возвращается в нормальный режим выделения. При нажатии кнопки **Выбор элемента**приложение отображается на переднем плане, а вид курсора меняется в соответствии с новым режимом выделения. Если щелкнуть выделенный элемент, проводник DOM снова отображается на переднем плане, а указанный элемент выделен.  
  
  Перед нажатием **Выбрать элемент**можно задать, необходимо ли выделять элементы в запущенном приложении, с помощью кнопки **Отображать поля выделения веб-страницы** . Эта кнопка показана на следующем рисунке. По умолчанию выделение отображается.  
  
  ![Отображение веб-страницы выделенная кнопка](../debugger/media/js-dom-display-highlights-button.png "JS_DOM_Display_Highlights_Button")  
  
  Если выделение элементов включено, элементы, на которые наводится указатель мыши в имитаторе, выделяются. Цвет выделения элементов соответствует рамочной модели, отображаемой на вкладке **Макет** проводника DOM.  
  
> [!NOTE]
>  В эмуляторе Windows Phone выделение элементов с помощью наведения поддерживается лишь частично.  
  
 Пример, демонстрирующий способ выбора элементов с помощью **элемент Select** "Кнопка", см. в разделе [стилей CSS, отладка с использованием проводника DOM](../debugger/debug-css-styles-using-dom-explorer.md).  
  
##  <a name="BrowserSupport"></a> Поддержка браузерами и платформами  
 Инструменты Visual Studio для JavaScript, проводник DOM и окно консоли JavaScript поддерживаются в следующих платформах:  
  
- [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)] и приложения для Магазина Windows Phone с использованием JavaScript и HTML  
  
- Internet Explorer 11 на платформе [!INCLUDE[win81](../includes/win81-md.md)]  
  
- Internet Explorer 10 на платформе [!INCLUDE[win8](../includes/win8-md.md)]  
  
  Перейдите [сюда](http://go.microsoft.com/fwlink/?LinkID=232448) , чтобы скачать [!INCLUDE[win8](../includes/win8-md.md)] и Visual Studio.  
  
## <a name="see-also"></a>См. также  
 [Debug apps in Visual Studio](../debugger/debug-store-apps-in-visual-studio.md)   
 [Отладка стилей CSS с использованием проводника DOM](../debugger/debug-css-styles-using-dom-explorer.md)   
 [Отладка макета с использованием проводника DOM](../debugger/debug-layout-using-dom-explorer.md)   
 [Просмотр прослушивателей событий DOM](../debugger/view-dom-event-listeners.md)   
 [Обновление приложения (JavaScript)](../debugger/refresh-an-app-javascript.md)   
 [Отладка элемента управления WebView](../debugger/debug-a-webview-control.md)   
 [Сочетания клавиш](../debugger/keyboard-shortcuts-html-and-javascript.md)   
 [JavaScript Console commands](../debugger/javascript-console-commands.md)   
 [Отладка примера кода HTML, CSS и JavaScript](../debugger/debug-html-css-and-javascript-sample-code.md)   
 [Поддержка и специальные возможности продукта](http://msdn.microsoft.com/library/tzbxw1af\(VS.120\).aspx)



