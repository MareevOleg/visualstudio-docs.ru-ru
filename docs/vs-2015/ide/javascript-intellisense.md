---
title: JavaScript IntelliSense | Документы Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IntelliSense [JavaScript]
- <reference> JavaScript XML tag
- JavaScript Code Editor
- XML code comments, JavaScript IntelliSense
- reference JavaScript XML tag
- JavaScript, IntelliSense
- code comments, JavaScript IntelliSense
- JavaScript, reference groups
- JavaScript Editor
- reference directives [JavaScript]
- JavaScript, XML documentation comments
- reference groups [JavaScript]
- JavaScript, reference directives
- IntelliSense [JavaScript], about
- IntelliSense extensibility [JavaScript]
- XML documentation comments [JavaScript]
ms.assetid: af1a3171-c9d8-45a3-9c96-a763e3b163ef
caps.latest.revision: 67
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b64dc915dddb7290eb80a8a38352e87a331e0dd0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47573275"
---
# <a name="javascript-intellisense"></a>IntelliSense для JavaScript
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [IntelliSense для JavaScript](https://docs.microsoft.com/visualstudio/ide/javascript-intellisense).  
  
IntelliSense помогает быстрее писать код, допуская при этом меньше ошибок, что достигается благодаря предоставлению сведений в процессе программирования. В ходе работы со скриптом клиента редактора JavaScript IntelliSense выводит списки доступных объектов, функций, свойств и параметров в зависимости от текущего контекста. Вариант кода можно выбрать из всплывающего списка, формируемого IntelliSense для завершения кода.  
  
 С помощью IntelliSense выполнение следующих задач становится проще:  
  
-   Поиск сведений о членах.  
  
-   Вставка элементов языка прямо в код.  
  
-   Сохранение контекста, не покидая текстовый редактор.  
  
-   Поддержка пользовательского IntelliSense с комментариями XML-документации и расширяемостью IntelliSense для JavaScript.  
  
 В этом разделе содержатся следующие подразделы.  
  
-   [Определение контекста IntelliSense](#DeterminingIntelliSenseContext)  
  
-   [Обработка сведений IntelliSense](#ProcessingIntelliSenseInformation)  
  
-   [Функции IntelliSense для JavaScript](#Features)  
  
-   [Расширяемость IntelliSense для JavaScript](#Extensibility)  
  
-   [Проверка JavaScript](#Validation)  
  
 Дополнительные сведения о функциональных возможностях IntelliSense [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)], см. в разделе [использование технологии IntelliSense](../ide/using-intellisense.md).  
  
##  <a name="DeterminingIntelliSenseContext"></a> Определение контекста IntelliSense  
 IntelliSense для JavaScript предоставляет варианты кода на основе всего скрипта, которые имеют отношение к текущему контексту скрипта. Сюда входят элементы скрипта в текущем файле. IntelliSense также включает любой код, на который имеется прямая или косвенная ссылка из скрипта, например ссылки на файл скрипта, ссылки на скрипт сборки, ссылки на службы и ссылки, связанные со страницами.  
  
 Текущий контекст скрипта создается на основе следующих элементов:  
  
-   Функции, определенные во всех блоках скриптов в активном документе. Встроенные блоки скрипта поддерживаются в файлах с расширениями .aspx., .ascx, .master, .html и .htm.  
  
-   Элементы `script` с атрибутами `src`, указывающими на другой файл скрипта. Разрешение конечного файла скрипта должно быть .js.  
  
-   Файлы JavaScript, ссылающиеся на другие файлы JavaScript при помощи директивы `reference`.  
  
-   Эталонные группы для глобальных объектов, расширений IntelliSense или файлов скриптов с отложенной загрузкой.  
  
-   Ссылки на веб-службы XML.  
  
-   Элементы управления <xref:System.Web.UI.ScriptManager> и <xref:System.Web.UI.ScriptManagerProxy>, если веб-приложение является приложением ASP.NET на основе AJAX.  
  
-   [!INCLUDE[atlaslib_current_ext](../includes/atlaslib-current-ext-md.md)], если используется веб-приложение ASP.NET с поддержкой AJAX.  
  
    > [!NOTE]
    >  IntelliSense не поддерживается для скрипта, расположенного в атрибутах обработчика событий для элементов HTML, или определенного в атрибутах `href`.  
  
##  <a name="ProcessingIntelliSenseInformation"></a> Обработка сведений IntelliSense  
 Чтобы предоставить JavaScript IntelliSense, языковая служба выполняет следующие операции:  
  
-   Создается список независимых файлов JavaScript на основе ссылок в активном документе и исходя из рекурсивной проверки ссылок на скрипты в файлах со ссылками.  
  
-   Выполняется обход списка и сбор сведений о типах и других соответствующих данных из каждого файла.  
  
-   Осуществляется объединение данных и их передача в языковую службу JavaScript, обеспечивающую доступность сведений о типах и данных для IntelliSense.  
  
-   Файлы проверяются на предмет изменений, которые могут затронуть список IntelliSense и список обновляется в случае необходимости. Скрипты в удаленных хранилищах (например, связанные с помощью HTTP) не подлежат мониторингу.  
  
##  <a name="Features"></a> Функции IntelliSense для JavaScript  
 IntelliSense для JavaScript поддерживает следующие объекты:  
  
-   [Элементы документа Object Model (DOM)](#HTMLDom)  
  
-   [Встроенные объекты](#IntrinsicObjects)  
  
-   [Определяемые пользователем переменные, функции и объекты](#UserDefined)  
  
-   Объекты, определенные во внешних файлах, таких как использование ссылок на [ссылки на сценарии](#Script), [ссылаться директивы](#ReferenceDirectives), и [используют группы](#ReferenceGroups).  
  
-   Объекты, определенные в удаленных файлах, которые загружены Visual Studio.  
  
-   Объекты, указанные в [комментарии XML-документации](#XMLDocComments), такие как параметры и поля.  
  
-   Объекты, которые описываются с помощью стандартных тегов комментария JavaScript (//). Дополнительные сведения см. в разделе [расширение IntelliSense для JavaScript](../ide/extending-javascript-intellisense.md).  
  
-   Объекты, поддерживаемые с помощью [расширяемость IntelliSense для JavaScript](#Extensibility) механизм. Дополнительные сведения см. в разделе [расширение IntelliSense для JavaScript](../ide/extending-javascript-intellisense.md).  
  
-   [Объекты ASP.NET AJAX](#ASPNet)  
  
 Если технология IntelliSense не сможет определить тип объекта, она предоставляет варианты завершения операторов на основе идентификаторов в активном документе. Дополнительные сведения см. в разделе [завершение операторов для идентификаторов](../ide/statement-completion-for-identifiers.md).  
  
###  <a name="HTMLDom"></a> Элементы HTML DOM  
 IntelliSense для JavaScript предоставляет справочники по программированию для элементов Dynamic HTML (DHTML) DOM, таких как `body`, `form` и `div`. IntelliSense выводит только элементы, включенные в текущий документ и главную страницу. IntelliSense для JavaScript также поддерживает объекты `window` и `document` с их членами.  
  
###  <a name="IntrinsicObjects"></a> Встроенные объекты  
 IntelliSense для JavaScript предоставляет справочники по программированию для встроенных объектов, например `Array`, `String`, `Math`, `Date` и `Number`. Дополнительные сведения о встроенных объектах см. в разделе [встроенные объекты](~/E:/Repos/visualstudio-docs-pr/scripting-docs/javascript/intrinsic-objects-javascript.md).  
  
###  <a name="UserDefined"></a> Определяемые пользователем переменные, функции и объекты  
 При изменении файла JavaScript [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] сканирует открытые и связанные документы для определения всех доступных ресурсов кода. Сюда входят переменные, функции и объекты, которые вы создали. Потом эти ресурсы становятся доступны IntelliSense для JavaScript.  
  
 Дополнительные сведения о пользовательских переменных, функций и объектов, см. в разделе [Создание собственных объектов](http://go.microsoft.com/fwlink/?LinkId=108671) на веб-сайте MSDN.  
  
###  <a name="External"></a> Ссылки на внешние файлы  
 Можно включить различные типы внешних ссылок на файлы, чтобы обеспечить поддержку IntelliSense в коде. Ссылки на внешние файлы могут представлять собой ссылки на скрипты, директивы ссылок, а также могут быть заданы при помощи эталонных групп.  
  
####  <a name="Script"></a> Ссылки на скрипты  
 Чтобы не писать весь скрипт клиента на странице можно создать ссылки на внешние файлы с кодом скрипта. Это упрощает повторное использование кода на нескольких страницах и позволяет помещать скрипт клиента в кэш браузера.  
  
 Если страница ASP.NET с поддержкой AJAX не используется, можно создать ссылку на внешний файл скрипта при помощи атрибута `src` в открывающем теге элемента `script`. Атрибут `src` указывает URL-адрес внешнего файла с исходным кодом или данными.  
  
 В следующем примере показана разметка, где атрибут `src` используется в теге <`script`> для создания ссылки на файл скрипта.  
  
```html  
<script type="text/javascript" src="~/Scripts/JavaScript.js">  
  
</script>  
```  
  
 При работе со страницей ASP.NET с поддержкой AJAX можно создать ссылки на файлы со скриптом при помощи объекта <xref:System.Web.UI.ScriptReference> элемента управления <xref:System.Web.UI.ScriptManager>.  
  
 В следующем примере показана разметка для объекта <xref:System.Web.UI.ScriptReference> в элементе управления <xref:System.Web.UI.ScriptManager> для создания ссылки на файл скрипта.  
  
```html  
<asp:ScriptManager ID="ScriptManager1" runat="server">  
  <Scripts>  
    <asp:ScriptReference Path="~/Scripts/JavaScript.js" />  
  </Scripts>  
</asp:ScriptManager>  
```  
  
 IntelliSense также поддерживает файлы скрипта, внедренные в качестве ресурсов в сборку в веб-приложениях ASP.NET AJAX. Дополнительные сведения о ресурсах внедренных скриптов см. в разделе [Пошаговое руководство: внедрение файл JavaScript в качестве ресурса в сборку](http://msdn.microsoft.com/library/d8cb78cd-95a9-4dc6-92df-391866817e89).  
  
####  <a name="ReferenceDirectives"></a> Директивы ссылок  
 Директивы `reference` позволяют [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] устанавливать отношение между редактируемым скриптом и другими скриптами. Директива `reference` позволяет включить файл скрипта в контекст программирования текущего файла скрипта. Эта дает возможность для IntelliSense ссылаться извне на определенные функции, типы и поля в процессе программирования.  
  
 Директива `reference` создается в форме комментария XML. Объявление директивы должно предшествовать любому скрипту в файле. Директива `reference` может содержать ссылку на скрипт на диске, ссылку на скрипт в сборке, ссылку на скрипт в службе или ссылку на скрипт на странице.  
  
 Ниже приводятся примеры использования директив ссылок на скрипты на диске. В первом примере языковая служба выполняет поиск файла в папке, содержащей файл проекта (например, .jsproj).  
  
 `/// <reference path="ScriptFile1.js" />`  
  
 `/// <reference path="Scripts/ScriptFile2.js" />`  
  
 `/// <reference path="../ScriptFile3.js" />`  
  
 `/// <reference path="~/Scripts/ScriptFile4.js" />`  
  
 В следующем примере продемонстрировано, как создать ссылку на скрипт в сборке.  
  
 `/// <reference name "Ajax.js" assembly="System.Web.Extensions, ..." />`  
  
 В следующем примере показано, как создать ссылку на скрипт в службе.  
  
 `/// <reference path="MyService.asmx" />`  
  
 `/// <reference path="Services/MyService.asmx" />`  
  
 `/// <reference path="../MyService.asmx" />`  
  
 `/// <reference path="~/Services/MyService.asmx" />`  
  
> [!NOTE]
>  IntelliSense для JavaScript не поддерживается для скрипта, расположенного в файлах веб-службы (.asmx) в проектах веб-приложений (WAP).  
  
 В следующем примере показано, как создать ссылку на скрипт на странице.  
  
 `/// <reference path="Default.aspx" />`  
  
 `/// <reference path="Admin/Default.aspx" />`  
  
 `/// <reference path="../Default.aspx" />`  
  
 `/// <reference path="~/Admin/Default.aspx" />`  
  
 К директиве `reference` применяются следующие правила.  
  
-   Комментарий XML `reference` должен быть объявлен перед любым скриптом.  
  
-   В синтаксисе комментария XML необходимо использовать три косые черты. Ссылки со стандартным синтаксисом комментариев (две косые черты) пропускаются.  
  
-   Для каждой директивы можно указать только один файл или ресурс.  
  
-   Несколько ссылок на скрипты на странице не допускается.  
  
-   Если ссылка на страницу уже указана, никакой другой тип директивы ссылки не допускается.  
  
-   В именах файлов должны быть указаны относительные пути. Допускается для относительных путей от корня приложения использовать оператор тильды (`~`).  
  
-   Абсолютные пути пропускаются.  
  
-   Директивы ссылок в страницах со ссылками не будут обрабатываться, то есть директивы ссылок не разрешаются рекурсивно для страниц. Включается только скрипт, на который на странице имеется прямая ссылка.  
  
####  <a name="ReferenceGroups"></a> Группы ссылок  
 С помощью предопределенных групп ссылок можно задавать конкретные типы JS-файлов IntelliSense, которые находятся в области действия для различных проектов JavaScript. Доступны следующие типы эталонных групп:  
  
-   Неявные (Windows) для приложений [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)], использующих JavaScript. Файлы, включенные в эту группу, находятся в области действия для каждого JS-файла, открытого в редакторе кода для проекта указанного типа.  
  
-   Неявные (Интернет), для проектов HTML5. Файлы, включенные в эту группу, находятся в области действия для каждого JS-файла, открытого в редакторе кода для данных типов проектов.  
  
-   Эталонные группы рабочих процессов, для рабочих веб-процессов HTML5. Файлы, указанные в этой группе, находятся в области действия для JS-файлов, снабженных явной ссылкой на эталонную группу выделенного рабочего процесса.  
  
-   Универсальные, для других типов проектов JavaScript.  
  
 В большинстве случаев эталонные группы не требуется изменять. Однако если в них требуется внести изменения, можно использовать параметры конфигурации для редактора кода JavaScript, чтобы определить файлы, включенные в соответствующую эталонную группу. Инструкции по использованию этой функции см. в разделе [параметры, текстовый редактор, JavaScript, IntelliSense](../ide/reference/options-text-editor-javascript-intellisense.md).  
  
> [!TIP]
>  Ссылки IntelliSense обычно используются для обеспечения поддержки IntelliSense для глобальных объектов, а также для IntelliSense [расширения](#Extensibility). Также можно использовать эту возможность для скриптов, которые необходимо загрузить во время выполнения с помощью загрузчика скрипта.  
  
### <a name="remote-file-references"></a>Ссылки на удаленные файлы  
 В Visual Studio можно настроить загрузку удаленных файлов JavaScript, ссылки на которые приведены в файле JavaScript, чтобы обеспечить поддержку IntelliSense для удаленного файла или библиотеки. При использовании этой функции файлы будут загружены, когда вы включите их в файл JavaScript в качестве ссылки.  
  
> [!NOTE]
>  За исключением веб-проектов, эта возможность применима только к файлам JavaScript, открытым вне контекста проекта. Для веб-проектов удаленные файлы, ссылки на которые указаны в проекте, загружаются по умолчанию.  
  
 Инструкции по использованию этой функции см. в разделе [параметры, текстовый редактор, JavaScript, IntelliSense](../ide/reference/options-text-editor-javascript-intellisense.md).  
  
> [!WARNING]
>  Если при включении данной возможности производительность редактора кода снижается, рекомендуется отключить ее.  
  
###  <a name="XMLDocComments"></a> Комментарии XML-документации  
 Комментарии XML-документации представляют собой текстовые описания элементов кода, добавляемые в скрипт. Эти текстовые описания отображаются в IntelliSense при создании ссылки на скрипт с комментарием. Например, можно задать сведения о параметрах и возвращаемом значении функции. Комментарии XML-документации доступны только из файлов, сборок и служб со ссылками. Дополнительные сведения см. в разделе [комментарии XML-документации](../ide/xml-documentation-comments-javascript.md) и [создавать комментарии XML-документации](../ide/create-xml-documentation-comments-for-javascript-intellisense.md).  
  
 Технология IntelliSense может отображать комментарии XML-документации в следующих сценариях:  
  
-   Файл .js со ссылкой на другой файл .js.  
  
-   Файл .js со ссылкой на файл .aspx.  
  
-   Файл .aspx со ссылкой на файл .js.  
  
 IntelliSense недоступен, если файл .aspx ссылается на другой файл .aspx.  
  
###  <a name="ASPNet"></a> Объекты ASP.NET AJAX  
 ASP.NET AJAX также поддерживает IntelliSense для JavaScript. ASP.NET AJAX включает клиентскую платформу, расширяющую стандартные типы, доступные в ECMAScript (JavaScript и JavaScript). Для предоставления IntelliSense для JavaScript подробных сведений об объектах ASP.NET AJAX, комментарии XML-документации были добавлены в [!INCLUDE[atlaslib_current_ext](../includes/atlaslib-current-ext-md.md)]. Эти комментарии XML-документации отображаются при использовании типов и членов из библиотеки ASP.NET AJAX.  
  
> [!NOTE]
>  Закрытые члены IntelliSense для JavaScript не отображаются. Закрытые члены в ASP.NET AJAX можно определить по знаку подчеркивания (_) в начале.  
  
##  <a name="Extensibility"></a> Расширяемость IntelliSense для JavaScript  
 Служба JavaScript Language Service предоставляет объекты и функции, которые позволяют изменить возможности IntelliSense для разработчиков, применяющих сторонние библиотеки. Эти возможности особенно эффективны, если служба языка по умолчанию не может предоставить все данные, которые необходимо обеспечить заказчикам. Дополнительные сведения см. в разделе [расширение IntelliSense для JavaScript](../ide/extending-javascript-intellisense.md).  
  
##  <a name="Validation"></a> Проверка JavaScript  
 Проверка скриптов JavaScript выполняется непрерывно в фоновом режиме. Если [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] обнаруживает синтаксические ошибки в коде JavaScript, отзывы предоставляется следующими способами:  
  
-   Подчеркивание элементов в редакторе. Подчеркивание красной волнистой линией указывает на ошибки. Если навести указатель мыши на ошибку, отобразится подсказка с описанием ошибки.  
  
-   **Список ошибок** окна. **Список ошибок** окно отображает описание ошибки, файл, где произошла ошибка, номер строки и столбца и проекта. Для отображения **список ошибок** окно в **представление** меню, щелкните **список ошибок**.  
  
-   В окне вывода отображаются незагруженные ссылки.  
  
## <a name="see-also"></a>См. также  
 [Использование IntelliSense](../ide/using-intellisense.md)   
 [Создание комментариев XML-документации](../ide/create-xml-documentation-comments-for-javascript-intellisense.md)   
 [Расширение IntelliSense для JavaScript](../ide/extending-javascript-intellisense.md)   
 [Завершение операторов для идентификаторов](../ide/statement-completion-for-identifiers.md)   
 [Комментарии XML-документации](../ide/xml-documentation-comments-javascript.md)   
 [Об объектной модели DHTML](http://go.microsoft.com/fwlink/?LinkID=92344)   
 [Список членов](http://msdn.microsoft.com/en-us/1b9cc469-9cd4-4d42-9999-1f9479635ff8)   
 [Атрибут SRC &#124; свойство src](http://go.microsoft.com/fwlink/?LinkId=92345)


