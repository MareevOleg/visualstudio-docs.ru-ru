---
title: "В среде Visual Studio SDK | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- roadmap, Visual Studio integration SDK
- Visual Studio integration SDK roadmap
- integration roadmap, Visual Studio SDK
ms.assetid: 9118eaa4-0453-4dc5-9e16-c7062d254869
caps.latest.revision: 30
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: ca7c86466fa23fb21a932f26dc24e37c71cf29b4
ms.openlocfilehash: 565aaeb189ad129d5e4e26d9c73c080de2e77676
ms.lasthandoff: 04/05/2017

---
# <a name="inside-the-visual-studio-sdk"></a>В среде Visual Studio SDK
Подробные сведения о расширениях Visual Studio, включая архитектуры Visual Studio, компоненты, службы, схемы, служебные программы и т. д.  
  
## <a name="extensibility-architecture"></a>Архитектура расширяемости  
 Ниже показана архитектура расширяемости Visual Studio. Пакеты VSPackage предоставляют функциональные возможности приложений, которое является общим как службы в интегрированной среде разработки. Стандартная IDE также предлагает широкий набор служб, таких как <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>, которые предоставляют доступ к функциям окон интегрированной среды разработки.</xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>  
  
 ![График архитектуры окружения](~/extensibility/internals/media/environment.gif "environment")  
Обобщенное представление архитектуры Visual Studio  
  
## <a name="vspackages"></a>VSPackages  
 Пакеты VSPackage — это программные модули, которые образуют и расширяют среду Visual Studio с помощью элементов пользовательского интерфейса, служб, проектов, редакторов и конструкторов. Пакеты VSPackage являются центральным элементом архитектуры Visual Studio. Дополнительные сведения см. в разделе [пакетов VSPackage](../../extensibility/internals/vspackages.md).  
  
## <a name="visual-studio-shell"></a>Visual Studio Shell  
 Оболочка Visual Studio предоставляет базовые функциональные возможности и поддержки обмена данными между среди его компонент пакеты VSPackage и расширения MEF. Дополнительные сведения см. в разделе [оболочки Visual Studio](../../extensibility/internals/visual-studio-shell.md).  
  
## <a name="user-experience-guidelines"></a>Рекомендации по пользовательскому интерфейсу  
 Если вы планируете разработать новые возможности Visual Studio, вы должны взгляните на эти рекомендации, советы по разработке и удобство использования: [Visual Studio техники](../../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md).  
  
## <a name="commands"></a>Команды  
 Команды — это функции, которые выполняют задачи, например печать документа, обновление представления или создание нового файла.  
  
 При расширении Visual Studio можно создавать команды и зарегистрируйте его на оболочке Visual Studio. Можно указать эти команды отображения в Интегрированной среде разработки, например, в меню или панели инструментов. Обычно появляется пользовательской команды на **средства** на появятся меню и команды для отображения окна инструментов **другие окна** подменю **представление** меню.  
  
 При создании команды необходимо также создать обработчик событий для него. Обработчик событий определяет, когда команда видна или включена, можно изменить ее текст и гарантирует, что команда отвечает соответствующим образом при активации. В большинстве случаев IDE обрабатывает команды с помощью <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>интерфейса.</xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> Команды в Visual Studio, обрабатываются, начиная с корневого контекста команды, на основе локального выбора и до самый внешний контекст, на основе глобального выделения. Команды, добавленные в главное меню, становятся сразу доступными для использования в сценариях.  
  
 Дополнительные сведения см. в разделе [команд, меню и панелей инструментов](../../extensibility/internals/commands-menus-and-toolbars.md).  
  
## <a name="menus-and-toolbars"></a>Меню и панелей инструментов  
 Меню и панели инструментов позволяют пользователям вызова команд. Меню, строк или столбцов команд, которые обычно отображаются в виде отдельных текстовых элементов в верхней части окна инструментов. Вложенные меню, вторичного меню, которые отображаются, когда пользователь нажимает кнопку команды, включающие маленькую стрелку. Контекстные меню появляются при щелчке определённые элементы пользовательского интерфейса. Некоторые общие имена меню: **файл**, **изменить**, **представление**, и **окна**. Дополнительные сведения см. в разделе [расширение меню и команд](../../extensibility/extending-menus-and-commands.md).  
  
 Панели инструментов, строк или столбцов кнопок и других элементов управления, например поля со списком, списков и текстовых полей. Кнопки панели инструментов обычно имеют значок изображения, такие как значок папки для **открыть файл** команды или принтер для **печати** команды. Все элементы панели инструментов связаны с командами. При нажатии кнопки на панели инструментов выполняется ее связанная команда. В случае раскрывающийся элемент управления каждый элемент в раскрывающемся списке связывается с другой командой. Некоторые элементы управления панели инструментов, таких как элемент управления splitter являются гибридами. Одна часть элемента управления — кнопка панели инструментов, а другая — стрелка вниз, которая отображает несколько команд, при щелчке.  
  
## <a name="tool-windows"></a>Окна инструментов  
 Окна инструментов используются в Интегрированной среде разработки для отображения информации. **Панель элементов**, **обозревателе решений**, **свойства** окна, и **веб-браузер** приведены примеры окна инструментов.  
  
 Окна инструментов обычно обеспечивают различные элементы управления, с которыми может взаимодействовать пользователь. Например **свойства** окна пользователь может задать свойства объектов, предназначенных для определенной цели. **Свойства** окна специализированных в этом смысле, а также общие, так как он может использоваться во многих различных ситуациях. Аналогичным образом **вывода** окно является специальным, так как она обеспечивает текстовых выходных данных, но Общие, так как многие подсистем в Visual Studio можно использовать для представления выходных данных для пользователей Visual Studio.  
  
 Рассмотрим приведенный ниже рисунок Visual Studio, которая содержит несколько окон инструментов.  
  
 ![Снимок экрана](~/extensibility/internals/media/t1gui.png "T1gui")  
  
 Некоторые окна инструментов закреплены вместе в одну область, отображаются в окне инструментов обозревателя решений и скрывает окна инструментов, но делает их доступными, щелкнув вкладок. На рисунке показаны два окна инструментов **список ошибок** и **вывода** закреплены вместе на одной панели окна.  
  
 Также показано, является основной области документа, отображающий несколько окон редактора. Несмотря на то, что окна инструментов обычно имеют только один экземпляр (например, можно открыть только один **обозревателе решений**), редактор windows может иметь несколько экземпляров, каждый из которых используется для изменения отдельный документ, но все они закрепляются в той же области. На рисунке показана область документа, которая имеет два окна редактора, одно окно конструктора формы и окна браузера, показывающая начальной страницы. Все окна в окне документа, щелкнув вкладки доступны, но в окне редактора, содержащее файл EditorPane.cs является видимым и активной.  
  
 При расширении Visual Studio, можно создать инструмент, windows, позволяющих пользователям Visual Studio взаимодействовать с расширением. Можно также создать свои собственные редакторы, позволяющих пользователям Visual Studio редактирования документов. Поскольку окон инструментов и редакторов будут встроены в Visual Studio, у вас их, чтобы закрепить или неправильно отображаться на вкладке программирования. Неправильно зарегистрированы в Visual Studio, они будут автоматически после типичные компоненты окна инструментов и окна документов в Visual Studio. Дополнительные сведения см. в разделе [расширение и настройка окна инструментов](../../extensibility/extending-and-customizing-tool-windows.md).  
  
## <a name="document-windows"></a>Окна документов  
 Окно документа — это окно рамке дочернего окна многодокументного интерфейса (MDI). Окна документов обычно используются для размещения текстовые редакторы, редакторы формы (также известный как конструкторы) или элементы управления для редактирования, но они может также содержать другие функциональные типы. **Новый файл** диалоговое окно содержит примеры окон документов, предоставляемых средой Visual Studio.  
  
 Большинства редакторов специфичны для языка программирования или тип файлов, например HTML-страниц, наборы фреймов, файлы C++ или файлы заголовков. Выбирая шаблон в **новый файл** диалоговое окно, пользователь динамически создает окно документа для редактора для типа файла, который связан с шаблоном. Окно документа также создается, когда пользователь открывает существующий файл.  
  
 Окна документов, ограничены клиентской области MDI. Каждый документ имеет вкладку в верхней части страницы и порядок табуляции связан других окон, которые можно открыть в области MDI. Щелкните правой кнопкой мыши вкладку окна документа отображается контекстное меню, которое включает в себя параметры можно разбить на несколько групп вкладок горизонтальной или вертикальной области MDI. Разделение области MDI включает несколько файлов, которые можно просматривать в то же время. Дополнительные сведения см. в разделе [окна документов](../../extensibility/internals/document-windows.md).  
  
## <a name="editors"></a>Редакторы  
 В редакторе Visual Studio позволяет настраивать и использовать его для типа содержимого с помощью Managed Extensibility Framework (MEF). Во многих случаях вам не нужно будет создать VSPackage для расширения редактора, несмотря на то, что если вы хотите включить средства из командной оболочки (например, команда меню или сочетание клавиш), можно объединить с VSPackage расширения MEF.  
  
 Также можно создать пользовательский редактор, например, при желании для чтения и записи в базу данных, или если вы хотите использовать конструктор. Также можно использовать внешний редактор, например «Блокнот» или Microsoft WordPad. Дополнительные сведения см. в разделе [редактора и расширения службы языка](../../extensibility/editor-and-language-service-extensions.md).  
  
## <a name="language-services"></a>Службы языка  
 Редактор Visual Studio для поддержки новых ключевых слов для программирования или даже новый язык программирования, можно создать языковой службы. Каждая языковая служба может реализовать некоторых функций редактора, полностью, частично или вообще. В зависимости от настроек может предоставить служба языка подсветку синтаксиса, парные фигурные скобки, поддержку технологии IntelliSense и другие функции в редакторе.  
  
 Основа языковую службу: средство синтаксического анализа и сканер. Сканер (или лексический анализатор) разделяет исходный файл на элементы, которые известны как маркеры, а также средство синтаксического анализа устанавливает отношения между этих токенов. При создании языковую службу, необходимо реализовать средство синтаксического анализа и сканер, Visual Studio можно понять токены и грамматики языка. Можно создавать управляемые или неуправляемые языковой службы. Дополнительные сведения см. в разделе [расширяемость службы языка для прежних версий](../../extensibility/internals/legacy-language-service-extensibility.md).  
  
## <a name="projects"></a>Проекты  
 В Visual Studio проекты — это контейнеры, которые разработчики используют для организации и создания исходного кода и другие ресурсы. Проекты позволяют организовать, построения, отладки и развертывания исходного кода, ссылки на веб-служб и баз данных и другие ресурсы. Пакеты VSPackage можно расширить система проектов Visual Studio, предоставляя типы проектов, подтипов проекта и пользовательские средства.  
  
 Проекты могут также можно собирать в решении, которое представляет собой группу одного или нескольких проектов, которые работают совместно, чтобы создать приложение. Проект и состояние сведения, относящиеся к решению хранится в двух файлов решений, файл текстовый файл решения (SLN) и файл пользовательских параметров (.suo) двоичные решения. Эти файлы похожи на файлы группы (VBG), которые использовались в предыдущих версиях [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)], и рабочей области (DSW) и пользователь параметры файлов (.opt), которые использовались в предыдущих версиях [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)].  
  
 Дополнительные сведения см. в разделе [проекты](../../extensibility/internals/projects.md) и [решения](../../extensibility/internals/solutions.md).  
  
## <a name="project-and-item-templates"></a>Шаблоны проектов и элементов  
 Visual Studio включает предопределенных шаблонов проектов и шаблонов элементов проекта. Можно также создайте собственные шаблоны или получите шаблонов от сообщества, а затем интегрировать их в Visual Studio. [Коллекции кода MSDN](http://code.msdn.microsoft.com/Project/ProjectDirectory.aspx?ProjectSearchText=visual%20studio) можно перейти для шаблонов и расширения.  
  
 Шаблоны содержат структуры проекта и основные файлы, необходимые для создания определенного типа приложений, управления, библиотеки или класса. При необходимости для разработки программного обеспечения, похожа на один из шаблонов, создайте проект, основанный на шаблоне, а затем измените файлы в этом проекте.  
  
> [!NOTE]
>  Эта архитектура шаблона не поддерживается для [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] проектов. Дополнительные сведения о создании [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] шаблонов проектов см. в разделе [Разработка мастера](/cpp/ide/designing-a-wizard).  
  
 Дополнительные сведения см. в разделе [Добавление проекта и шаблоны элементов проекта](../../extensibility/internals/adding-project-and-project-item-templates.md).  
  
## <a name="properties-and-options"></a>Свойства и параметры  
 **Свойства** окне отображаются свойства одного или нескольких выбранных элементов: [расширение свойств](../../extensibility/internals/extending-properties.md) параметры страницы содержат наборами параметров, относящихся к конкретный компонент, например языка программирования или VSPackage: [параметры и параметры страницы](../../extensibility/internals/options-and-options-pages.md). Параметры являются компонентами, обычно связанные с Пользовательским интерфейсом, которые можно импортировать и экспортировать: [Поддержка пользовательских параметров](../../extensibility/internals/support-for-user-settings.md).  
  
## <a name="visual-studio-services"></a>Службы Visual Studio  
 Служба предоставляет определенный набор интерфейсов для использования компонентов. Visual Studio предоставляет ряд служб, которые могут использоваться все компоненты, включая расширения. Например службы Visual Studio позволяют окна инструментов, чтобы отображаться или скрыты динамически, включите доступ к справке, строка состояния или события пользовательского интерфейса. В редакторе Visual Studio также предоставляет службы, которые можно импортировать в расширения редактора. Дополнительные сведения см. в разделе [использование и предоставление службы](../../extensibility/using-and-providing-services.md).  
  
## <a name="debugger"></a>Отладчик  
 Отладчик — это пользовательский интерфейс для компонентов отладки конкретного языка. При создании новой языковой службы, необходимо будет создать определенные отладчик для перенаправления в в отладчике. Дополнительные сведения см. в разделе [расширения отладчика Visual Studio](../../extensibility/debugger/visual-studio-debugger-extensibility.md).  
  
## <a name="source-control"></a>Система управления версиями  
 Сведения о реализации подключаемого модуля системы управления версиями или VSPackage см. в разделе [системы управления версиями](../../extensibility/internals/source-control.md).  
  
## <a name="wizards"></a>Мастера  
 Мастер можно создать в сочетании с новым типом проекта, чтобы мастер поможет пользователям принимать правильные решения, при создании нового проекта этого типа. Дополнительные сведения см. в разделе [мастеров](../../extensibility/internals/wizards.md).  
  
## <a name="custom-tools"></a>Пользовательские средства  
 Пользовательские средства позволяют вам это средство, связанные с элементом в проекте и запуска этого средства, при каждом сохранении файла. Дополнительные сведения см. в разделе [средства пользовательских](../../extensibility/internals/custom-tools.md).  
  
## <a name="vssdk-utilities"></a>Служебные программы VSSDK  
 VSSDK содержит набор служебных программ, которые могут потребоваться для работы с различными аспектами пакеты VSPackage. Дополнительные сведения см. в разделе [VSSDK программы](../../extensibility/internals/vssdk-utilities.md).  
  
## <a name="using-windows-installer"></a>С помощью установщика Windows  
 В некоторых случаях может потребоваться использовать установщик Windows, а не установщик VSIX: например, может потребоваться записать в реестр. Сведения об использовании установщика Windows с помощью расширений см. в разделе [Установка пакетов VSPackage с помощью установщика Windows](../../extensibility/internals/installing-vspackages-with-windows-installer.md).  
  
## <a name="help-viewer"></a>Help Viewer  
 Собственные справки и F1 страниц можно интегрировать в средство просмотра справки. Дополнительные сведения см. в разделе [средстве просмотра справки Microsoft SDK](../../extensibility/internals/microsoft-help-viewer-sdk.md).