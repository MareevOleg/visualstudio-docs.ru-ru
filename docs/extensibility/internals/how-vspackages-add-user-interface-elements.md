---
title: "Как добавить элементы пользовательского интерфейса в VSPackages | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user interfaces, adding elements
- UI element design [Visual Studio SDK], VSPackages
- VSPackages, contributing UI elements
ms.assetid: abc5d9d9-b267-48a1-92ad-75fbf2f4c1b9
caps.latest.revision: 60
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
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: 6bf44a2b1fa029753c4b3c00f911070a2132bb75
ms.lasthandoff: 02/22/2017

---
# <a name="how-vspackages-add-user-interface-elements"></a>Как добавить элементы пользовательского интерфейса в пакеты VSPackage
VSPackage можно добавить элементы пользовательского интерфейса (UI, например, меню, панелей инструментов) и средства windows в Visual Studio с помощью файла .vsct.  
  
 Можно найти рекомендации по проектированию для элементов пользовательского интерфейса в [Visual Studio техники](../../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md).  
  
## <a name="the-visual-studio-command-table-architecture"></a>Архитектура таблиц команд Visual Studio  
 Как было отмечено, архитектура таблицы команда поддерживает вышеупомянутые архитектурных принципов. Принципов абстракции, структуры данных и средства архитектуры таблицы команды выглядят следующим образом:  
  
-   Существует три основных типа элементов: меню, команд и группы. Меню могут быть предоставлены в пользовательском Интерфейсе как меню, подменю, панели инструментов и окна инструментов. Команды, процедуры, которые пользователь может выполнить инструкцию в Интегрированной среде разработки и они могут быть предоставлены как элементы меню, кнопки, списки или других элементов управления. Группы являются контейнерами для меню и команд.  
  
-   Каждый элемент задается по определению, который описывает элемент, его приоритет относительно других элементов и флаги, которые изменяют свое поведение.  
  
-   Каждый элемент имеет размещения, в котором описывается родительский элемент. Элемент может иметь несколько родительских элементов, чтобы он может располагаться в нескольких местах в пользовательском Интерфейсе.  
  
     Каждая команда должна быть группа родительских, даже если он является единственным дочерним в этой группе. Каждый стандартный меню должен быть родительской группы. Панели инструментов и окна инструментов в качестве собственные родительские элементы. В группе может быть как родительским главного меню Visual Studio, или любой меню, панели инструментов или окно инструментов.  
  
### <a name="how-items-are-defined"></a>Определение элементов  
 . Vsct файлы представлены в формате XML. Файл .vsct определяет элементы пользовательского интерфейса для пакета и определяет место отображения этих элементов в Интегрированной среде разработки. Каждый меню, группы или команды в пакете сначала назначается идентификатор GUID и идентификатор в `Symbols` разделе. В оставшейся части .vsct файла каждого меню, команды и группы определяется его комбинация GUID и идентификатор. В следующем примере показано типичное `Symbols` раздел, созданный шаблон пакета Visual Studio при **команды меню** выбранных в шаблоне.  
  
```xml  
<Symbols>  
  <!-- This is the package guid. -->  
  <GuidSymbol name="guidMenuTextPkg" value="{b1253bc6-d266-402b-89e7-5e3d3b22c746}" />  
  
  <!-- This is the guid used to group the menu commands together -->  
  <GuidSymbol name="guidMenuTextCmdSet" value="{a633d4e4-6c65-4436-a138-1abeba7c9a69}">  
  
    <IDSymbol name="MyMenuGroup" value="0x1020" />  
    <IDSymbol name="cmdidMyCommand" value="0x0100" />  
  </GuidSymbol>  
  
  <GuidSymbol name="guidImages" value="{53323d9a-972d-4671-bb5b-9e418480922f}" >  
    <IDSymbol name="bmpPic1" value="1" />  
    <IDSymbol name="bmpPic2" value="2" />  
    <IDSymbol name="bmpPicSearch" value="3" />  
    <IDSymbol name="bmpPicX" value="4" />  
    <IDSymbol name="bmpPicArrows" value="5" />  
  </GuidSymbol>  
</Symbols>  
```  
  
 Элемент верхнего уровня `Symbols` раздел [GuidSymbol элемент](../../extensibility/guidsymbol-element.md). `GuidSymbol`имена элементов соответствуют идентификаторы GUID, которые используются для идентификации пакетов и их частей компонента в интегрированной среде разработки.  
  
> [!NOTE]
>  Идентификаторы GUID формируются автоматически шаблоном пакета Visual Studio. Можно также создать уникальный идентификатор GUID, щелкнув **создать GUID** на **средства** меню.  
  
 Первый `GuidSymbol` элемент, «guid [имя пакета] Pkg», идентификатор GUID самого пакета. Это идентификатор GUID, который используется в Visual Studio для загрузки пакета. Как правило не имеет дочерних элементов.  
  
 По соглашению, меню и команд сгруппированы второй `GuidSymbol` элемент, «guid [имя пакета] CmdSet», и точечные рисунки в группе имеют третий `GuidSymbol` элемент, «guidImages». Необходимо соблюдать этот формат, но каждый меню, группы, команды и точечный рисунок должен быть потомком `GuidSymbol` элемента.  
  
 Во втором `GuidSymbol` элемент, представляющий набор команд пакета, несколько `IDSymbol` элементы. Каждый [IDSymbol элемент](../../extensibility/idsymbol-element.md) сопоставляет имя числовое значение и могут представлять меню, группу или команду, которая является частью набора команд. `IDSymbol` Элементами в третьем `GuidSymbol` растровые изображения представляют собой элемент, можно использовать в качестве значков для команд. Так как пары GUID-идентификатор должен быть уникальным в приложение в двух дочерних элементов того же `GuidSymbol` элемент может иметь то же значение.  
  
### <a name="menus-groups-and-commands"></a>Меню, групп и команд  
 Меню, группы или команды содержит GUID и идентификатор, могут добавляться в интегрированную среду разработки. Каждый элемент пользовательского интерфейса должен иметь следующее:  
  
-   Объект `guid` атрибут, который совпадает с именем `GuidSymbol` элемент, заданный элемент пользовательского интерфейса в списке.  
  
-   `id` , Соответствующий имени связанного атрибута `IDSymbol` элемента.  
  
     Вместе `guid` и `id` составить атрибуты *подписи* элементом пользовательского интерфейса.  
  
-   A `priority` атрибут, который определяет положение элемента пользовательского интерфейса в его родительском меню или группы.  
  
-   Объект [родительского элемента](../../extensibility/parent-element.md) с `guid` и `id` атрибутов, определяющих сигнатуры родительского меню или группы.  
  
#### <a name="menus"></a>Меню  
 Каждое меню определяется как [элемент меню](../../extensibility/menu-element.md) в `Menus` разделе. Меню должен иметь `guid`, `id`, и `priority` атрибуты и `Parent` элемента, а также следующие дополнительные атрибуты и дочерние элементы:  
  
-   A `type` атрибут, указывающий, следует ли отображать меню в интегрированной среде разработки в качестве своеобразного меню или панели инструментов.  
  
-   A [элемент строки](../../extensibility/strings-element.md) , содержащий [ButtonText элемент](../../extensibility/buttontext-element.md), которого определяет название меню в Интегрированной среде разработки и [CommandName элемент](../../extensibility/commandname-element.md), который указывает имя, используемое в **команда** окна для доступа к меню.  
  
-   Необязательные флаги. Объект [элемент Command флаг](../../extensibility/command-flag-element.md) может появляться в определении меню для изменения его внешнего вида и поведения в Интегрированной среде разработки.  
  
 Каждый `Menu` элемент должен иметь группы его родительского, если он не является фиксируемого элемента, например, панель инструментов. Закрепляемое меню является его родительский элемент. Дополнительные сведения о меню и значения для `type` см. в разделе [элемент меню](../../extensibility/menu-element.md) документации.  
  
 В следующем примере показано меню, которое отображается в строке меню Visual Studio, рядом с **средства** меню.  
  
```xml  
<Menu guid="guidTopLevelMenuCmdSet"  
id="TopLevelMenu" priority="0x700" type="Menu">  
  <Parent guid="guidSHLMainMenu"  
          id="IDG_VS_MM_TOOLSADDINS" />  
  <Strings>  
    <ButtonText>TestMenu</ButtonText>  
    <CommandName>TestMenu</CommandName>  
  </Strings>  
</Menu>  
```  
  
#### <a name="groups"></a>Группы  
 Группа — это элемент, определенный в `Groups` раздел файла .vsct. Группы — это просто контейнеры. Они не отображаются в интегрированной среде разработки, кроме как разделителя меню. Таким образом [элемент группы](../../extensibility/group-element.md) определяется только его сигнатура, приоритет и родительским.  
  
 Группа может иметь меню, другую группу или самого в качестве родительского. Однако родительский обычно является меню или панели инструментов. Меню в предыдущем примере является дочерним для элемента `IDG_VS_MM_TOOLSADDINS` группы и группы является дочерним для элемента меню Visual Studio. Группы в следующем примере является дочерним элементом меню в предыдущем примере.  
  
```  
 <Group guid="guidTopLevelMenuCmdSet" id="MyMenuGroup"  
priority="0x0600">  
   <Parent guid="guidTopLevelMenuCmdSet" id="TopLevelMenu"/>  
 </Group>  
```  
  
 Поскольку это часть меню этой группы обычно будет содержать команды. Он также может содержать другие меню. Это определение подменю, как показано в следующем примере.  
  
```xml  
<Menu guid="guidTopLevelMenuCmdSet" id="SubMenu"  
priority="0x0100" type="Menu">  
  <Parent guid="guidTopLevelMenuCmdSet" id="MyMenuGroup"/>  
  <Strings>  
    <ButtonText>Sub Menu</ButtonText>  
    <CommandName>Sub Menu</CommandName>  
  </Strings>  
</Menu>  
```  
  
#### <a name="commands"></a>Команды  
 Команды, которая предоставляется в Интегрированной среде разработки, определена как [элемент Button](../../extensibility/button-element.md) или [элемент поля со списком](../../extensibility/combo-element.md). Отображение в меню или панель инструментов, команда должна быть группа с родительским.  
  
##### <a name="buttons"></a>Кнопки  
 Кнопки определены в `Buttons` разделе. Кнопка считается любой элемент меню, кнопки или другого элемента, которую пользователь может щелкнуть для выполнения отдельных команд. Некоторые типы кнопка может также включать функции списка. Кнопки имеют же необходимые и необязательные атрибуты, которые имеют меню, а также может иметь [значок элемент](../../extensibility/icon-element.md) , указывающий идентификатор GUID и идентификатор точечного рисунка, представляющий кнопку в Интегрированной среде разработки. Дополнительные сведения о нажатии клавиш и их атрибутов см. в разделе [элемент кнопки](../../extensibility/buttons-element.md) документации.  
  
 Кнопки в следующем примере является дочерним элементом группы в предыдущем примере и отображается как элемент меню в его родительском меню этой группы в Интегрированной среде разработки.  
  
```  
<Button guid="guidTopLevelMenuCmdSet" id="cmdidTestCommand" priority="0x0100" type="Button">  
  <Parent guid="guidTopLevelMenuCmdSet" id="MyMenuGroup" />  
  <Icon guid="guidImages" id="bmpPic1" />  
  <Strings>  
    <CommandName>cmdidTestCommand</CommandName>  
    <ButtonText>Test Command</ButtonText>  
  </Strings>  
</Button>  
```  
  
##### <a name="combos"></a>Комбинировать  
 Комбинировать определяются в `Combos` разделе. Каждый `Combo` элемент представляет раскрывающегося списка в Интегрированной среде разработки. Список может или не может быть записи пользователей, в зависимости от значения `type` атрибута поля со списком. Комбинировать имеют те же элементы поведения, кнопки имеют и могут также иметь следующие дополнительные атрибуты:  
  
-   A `defaultWidth` атрибут, указывающий ширину в пикселях.  
  
-   `idCommandList` Атрибут, указывающий список, содержащий элементы, которые отображаются в окне списка. Список команд, которые должны объявляться в том же `GuidSymbol` узел, содержащий поле со списком.  
  
 В следующем примере определяется элемент поля со списком.  
  
```xml  
<Combos>  
  <Combo guid="guidFirstToolWinCmdSet"  
         id="cmdidWindowsMediaFilename"  
         priority="0x0100" type="DynamicCombo"  
         idCommandList="cmdidWindowsMediaFilenameGetList"  
         defaultWidth="130">  
    <Parent guid="guidFirstToolWinCmdSet"  
            id="ToolbarGroupID" />  
    <CommandFlag>IconAndText</CommandFlag>  
    <CommandFlag>CommandWellOnly</CommandFlag>  
    <CommandFlag>StretchHorizontally</CommandFlag>  
    <Strings>  
      <CommandName>Filename</CommandName>  
      <ButtonText>Enter a Filename</ButtonText>  
    </Strings>  
  </Combo>  
</Combos>  
```  
  
##### <a name="bitmaps"></a>Точечные рисунки  
 Команды, которые будут отображаться вместе со значком должен включать `Icon` элемент, который ссылается на точечный рисунок с помощью его идентификатора GUID и идентификатор. Каждый рисунок определяется как [элемента растрового изображения](../../extensibility/bitmap-element.md) в `Bitmaps` разделе. Только необходимые атрибуты для `Bitmap` , определение `guid` и `href`, который указывает на исходный файл. Если исходный файл является панелью ресурсов **usedList** атрибута требуется также, чтобы получить список доступных образов на полосе. Дополнительные сведения см. в разделе [элемента растрового изображения](../../extensibility/bitmap-element.md) документации.  
  
### <a name="parenting"></a>Родительские связи  
 Следующие правила определяют, как элемент может вызвать другой элемент в качестве родительского.  
  
|Элемент|Заданные в этом разделе таблице команд|Могут содержаться (родительской или путем размещения в `CommandPlacements` разделе или оба)|Может содержать (называется родительской)|  
|-------------|--------------------------------------------------|---------------------------------------------------------------------------------------------------|---------------------------------------------|  
|Группа|[Группирует элемент](../../extensibility/groups-element.md), интегрированной среды разработки, другие пакеты VSPackage|Выберите группу, самого элемента|Меню, групп и команд|  
|Меню|[Элемент меню](../../extensibility/menus-element.md), интегрированной среды разработки, другие пакеты VSPackage|1 для *n* групп|0 для *n* групп|  
|Toolbar|[Элемент меню](../../extensibility/menus-element.md), интегрированной среды разработки, другие пакеты VSPackage|Сам элемент|0 для *n* групп|  
|Menu Item|[Кнопки элемент](../../extensibility/buttons-element.md), интегрированной среды разработки, другие пакеты VSPackage|1 для *n* групп самого элемента|-0, чтобы *n* групп|  
|Кнопка|[Кнопки элемент](../../extensibility/buttons-element.md), интегрированной среды разработки, другие пакеты VSPackage|1 для *n* групп самого элемента||  
|Поле со списком|[Элемент комбинировать](../../extensibility/combos-element.md), интегрированной среды разработки, другие пакеты VSPackage|1 для *n* групп самого элемента||  
  
### <a name="menu-command-and-group-placement"></a>Меню, команды и размещение группы  
 Меню, группы или команды могут отображаться в нескольких местах в Интегрированной среде разработки. Элемент должен появляться в нескольких местах, его необходимо будет добавить `CommandPlacements` раздел как [CommandPlacement элемент](../../extensibility/commandplacement-element.md). Как размещение команд можно добавить любое меню, группы или команды. Тем не менее панели инструментов нельзя расположить таким образом, так как они не могут находиться в нескольких местах в контекстно-зависимые.  
  
 Размещение команд имеют `guid`, `id`, и `priority` атрибуты. GUID и Идентификаторы должны совпадать, размещенного элемента. `priority` Атрибута определяет расположение элемента относительно других элементов. При Интегрированной объединяет два или более элементов, которые имеют одинаковый приоритет, их размещения не определены, так как интегрированная среда разработки не гарантирует, что ресурсы пакета считываются в том же порядке каждый раз при построении пакета.  
  
 Если в нескольких местах в меню или группу, все дочерние элементы этого меню или группа появляется в каждом экземпляре.  
  
## <a name="command-visibility-and-context"></a>Видимость команды и контекста  
 При установке нескольких пакетов VSPackages profusion меню, пункты меню и панелей инструментов может загромождать интегрированной среды разработки. Чтобы избежать этой проблемы, можно управлять видимостью отдельных элементов пользовательского интерфейса с помощью *ограничения на видимость* и командной строки.  
  
##### <a name="visibility-constraints"></a>Ограничения на видимость  
 Ограничение видимости задается как [элемент VisibilityItem](../../extensibility/visibilityitem-element.md) в `VisibilityConstraints` разделе. Ограничение видимости определяет конкретных контекстах пользовательского интерфейса, в которых отображается целевого элемента. Меню или команды, которые включены в этот раздел отображается только в том случае, когда один из определенных контекстах активен. Если меню или команда не упоминается в этом разделе, это всегда отображается по умолчанию. В этом разделе не применяются к группам.  
  
 `VisibilityItem`элементы должны иметь три атрибута, следующим образом: `guid` и `id` целевого элемента пользовательского интерфейса, и `context`. `context` Атрибут указывает, когда будут видны и принимает любой допустимый контекст пользовательского интерфейса, как его значение целевого элемента. Константы контекста пользовательского интерфейса для Visual Studio являются членами <xref:Microsoft.VisualStudio.VSConstants>класса.</xref:Microsoft.VisualStudio.VSConstants> Каждый `VisibilityItem` элемент может принимать значение только одного контекста. Чтобы применить второй контекста, создания второго `VisibilityItem` элемент, указывающий на один и тот же элемент, как показано в следующем примере.  
  
```xml  
<VisibilityConstraints>  
  <VisibilityItem guid="guidSolutionToolbarCmdSet"  
        id="cmdidTestCmd"  
        context="UICONTEXT_SolutionHasSingleProject" />  
  <VisibilityItem guid="guidSolutionToolbarCmdSet"  
        id="cmdidTestCmd"  
        context="UICONTEXT_SolutionHasMultipleProjects" />  
</VisibilityConstraints>  
```  
  
##### <a name="command-flags"></a>Команда флаги  
 Следующие флаги команда может повлиять на видимость меню и команды, которому они применяются.  
  
 AlwaysCreate  
 Меню создается, даже если он не имеет групп и кнопок.  
  
 Действует для:`Menu`  
  
 CommandWellOnly  
 Примените этот флаг Если команда не отображается в меню верхнего уровня, и вы хотите сделать его доступным для настройки дополнительных оболочки, например, привязка к ключ. После установки VSPackage, пользователь может изменять эти команды, открыв **параметры** диалоговое окно и затем измените расположение команды в разделе **клавиатуры среды** категории. Не влияет на размещение на контекстных меню, панелей инструментов, меню контроллеров или подменю.  
  
 Допустимые для: `Button`,`Combo`  
  
 DefaultDisabled  
 По умолчанию команда будет отключен, если VSPackage, который реализует команду не загружены или не был вызван метод QueryStatus.  
  
 Допустимые для: `Button`,`Combo`  
  
 DefaultInvisible  
 По умолчанию команда остается невидимым, если VSPackage, который реализует команду не загружены или не был вызван метод QueryStatus.  
  
 Следует использовать в сочетании с `DynamicVisibility` флаг.  
  
 Valid for: `Button`, `Combo`,`Menu`  
  
 DynamicVisibility  
 Видимость команды можно изменить с помощью метода QueryStatus или идентификатор GUID, который включается в контекст `VisibilityConstraints` раздел.  
  
 Применяется к командам, которые отображаются в меню, а не на панели инструментов. Элементы верхнего уровня панели инструментов можно отключить, но не скрываются, когда флаг OLECMDF_INVISIBLE возвращается из метода QueryStatus.  
  
 Меню этот флаг также указывает, что он должен быть автоматически скрыт при его элементы являются скрытыми. Этот флаг обычно назначается подменю, поскольку это поведение уже в меню верхнего уровня.  
  
 Следует использовать в сочетании с `DefaultInvisible` флаг.  
  
 Valid for: `Button`, `Combo`,`Menu`  
  
 NoShowOnMenuController  
 Если команду, которая содержит этот флаг располагается на контроллере меню, команда не отображается в раскрывающемся списке.  
  
 Действует для:`Button`  
  
 Дополнительные сведения о флагах командной см [элемент Command флаг](../../extensibility/command-flag-element.md) документации.  
  
##### <a name="general-requirements"></a>Общие требования  
 Команде необходимо передать следующий ряд тестов перед выводом а включен:  
  
-   Команда расположена правильно.  
  
-   `DefaultInvisible` Флаг не установлен.  
  
-   Родительском меню или панель инструментов отображается.  
  
-   Команда не является невидимым из-за запись контекста в [VisibilityConstraints элемент](../../extensibility/visibilityconstraints-element.md) раздел.  
  
-   Код VSPackage, который реализует <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>интерфейс отображает и позволяет команде.</xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> Код интерфейса не перехвачено и обрабатываться на нем.  
  
-   Когда пользователь щелкает команду, становится подпадают под той процедуре, описанной в [маршрутизации алгоритма](../../extensibility/internals/command-routing-algorithm.md).  
  
## <a name="calling-pre-defined-commands"></a>Предварительно определенные команды вызова  
 [UsedCommands элемент](../../extensibility/usedcommands-element.md) позволяет VSPackages для доступа к командам, предоставленных в интегрированной среде разработки или другие пакеты VSPackage. Чтобы сделать это, создайте [UsedCommand элемент](../../extensibility/usedcommand-element.md) имеет идентификатор GUID и идентификатор команды для использования. Это обеспечивает загрузку команда средой Visual Studio, даже если он не является частью текущей конфигурации Visual Studio. Дополнительные сведения см. в разделе [UsedCommand элемент](../../extensibility/usedcommand-element.md).  
  
## <a name="interface-element-appearance"></a>Внешний вид элемента интерфейса  
 Ниже приведены рекомендации по выбору и размещение элементов команды:  
  
-   [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]предлагает множество элементов пользовательского интерфейса, которые выглядят по-разному в зависимости от размещения.  
  
-   Элемент пользовательского интерфейса, который определяется с помощью `DefaultInvisible` флаг не будет отображаться в Интегрированной среде разработки, если он не является либо по его реализации VSPackage отображаются <xref:EnvDTE.IDTCommandTarget.QueryStatus%2A>метода или связанный с конкретным контекстом пользовательского интерфейса в `VisibilityConstraints` разделе.</xref:EnvDTE.IDTCommandTarget.QueryStatus%2A>  
  
-   Даже успешно позиционированные команда может не отображаться. Это потому, что интегрированная среда разработки автоматически отображает или скрывает некоторые команды, в зависимости от интерфейсов, которые VSPackage содержит (или не содержит) реализуется. Например реализация VSPackage некоторых создавать интерфейсы автоматически отображаться элементы меню, связанные с построением причины.  
  
-   Применение `CommandWellOnly` флаг в определении элемента пользовательского интерфейса означает, что команда может быть добавлено только путем настройки.  
  
-   Команды могут быть доступны только в определенных контекстах пользовательского интерфейса, например, только в том случае, если диалоговое окно отображается, когда IDE находится в режиме конструктора.  
  
-   Чтобы вызвать некоторые элементы пользовательского интерфейса для отображения в Интегрированной среде разработки, необходимо реализовать один или несколько интерфейсов или написать код.  
  
## <a name="see-also"></a>См. также  
 [Расширение меню и команд](../../extensibility/extending-menus-and-commands.md)