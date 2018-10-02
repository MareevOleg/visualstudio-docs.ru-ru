---
title: Глоссарий пакета SDK для Visual Studio | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- glossary [Visual Studio SDK]
ms.assetid: b64d432b-c39b-4904-ad18-3c3218b6e3aa
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 453826081ae3d0b747d948212e713dd672550b31
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47568272"
---
# <a name="visual-studio-sdk-glossary"></a>Глоссарий пакета SDK для Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [глоссарий пакета SDK для Visual Studio](https://docs.microsoft.com/visualstudio/extensibility/visual-studio-sdk-glossary).  
  
В этом глоссарии содержатся определения для терминов, используемых в [!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)] документации.  
  
## <a name="terms"></a>Термины  
 надстройка  
 Служебное приложение, драйвер или другое программное обеспечение, добавляемый основного приложения. В среде разработки Visual Studio (IDE) надстройка — это приложения с поддержкой автоматизации, который расширяет возможности интегрированной среды разработки.  
  
 модель автоматизации  
 Модель автоматизации, известен в предыдущих версиях Visual Studio в качестве модели расширяемости, — это программный интерфейс, который предоставляет доступ к базовым подпрограммам диска интегрированной среды разработки. Надстройки, мастера и макросы использовать объекты в модель автоматизации для элемента управления или расширить функциональные возможности интегрированной среды разработки.  
  
 контекст команды пользовательского интерфейса  
 Связывание GUID с видимостью команды пользовательского интерфейса или элемент, такой как панель инструментов. Контекст команды пользовательского интерфейса — в отличие от выбора контекста, в том, что он не присоединен к окну.  
  
 Контекст команды пользовательского интерфейса можно использовать для:  
  
-   Назначьте идентификатор GUID панели инструментов, которое появляется при активации определенного окна.  
  
-   Назначьте идентификатор GUID на доступность команды без необходимости загрузки или выполнения пакета VSPackage.  
  
-   Назначьте идентификатор GUID, влияют на привязки ключа.  
  
-   Назначьте идентификатор GUID, чтобы включить запись макроса.  
  
-   Назначьте идентификатор GUID для активации режима отладки или для переключения между режимами разработки и выполнения в редакторе.  
  
 component  
 Часть программного обеспечения, могут быть сделаны часть функциональных возможностей приложения без этого приложения, которое имеет любые существующие сведения о программном обеспечении. Передача данных между компонентом и приложения является исключительно через интерфейсы OLE стиля.  
  
 Диспетчер компонентов  
 Службы `SOleComponentManager`, которая предоставляет службы координации без пользовательского интерфейса для верхнего уровня компонентов. `SOleComponentManager` Службы реализует `IOleComponentManager` интерфейс.  
  
 Диспетчер компонентов пользовательского интерфейса  
 Службы `SOleComponentUIManager`, которая предоставляет службы координации интерфейса пользователя. `SOleComponentUIManager` Службы реализует `IOleComponentUIManager` и `IOleInPlaceComponentUIManager` интерфейсов.  
  
 контейнер контекста  
 `IVsUserContext` Объекта (COM), присоединен к компоненту среды. Этот объект содержит ключевые слова поиска, ключевые слова F1 и атрибуты, относящиеся к компоненту. Кроме того контекста контейнеры указывать любой подконтекстов, связанных с ними.  
  
 контекст поставщика  
 Компонент в интегрированной среде разработки с контейнером контекста, связанные с ней. Такие компоненты включают окна инструментов, редактора или иерархии проекта.  
  
 конструктор  
 Программный интерфейс, который позволяет пользователям управлять элементы пользовательского интерфейса (форм, кнопок и других элементов управления).  
  
 DocData  
 COM-объект, инкапсулирующий базовых данных документа в мире, когда существует разделение документов и представлений (например, в случае редактор текста, это будет текстового буфера, базовый всех представлений редактора текста). Если для класса EditorFactory не поддерживает этот объект, интегрированной среды разработки могут производить один от его имени. Ответственность за этот объект является управление постоянного хранения и семантика общего доступа для нескольких представлений за этот же `DocData`. Если `DocData` поддерживает `IOleCommandTarget` интерфейс, он будет включен в маршрутизации команд UIShell.  
  
 DocObject  
 Технология, используемая для размещения пользовательского интерфейса в рамке, предоставленный средой размещения. В частности, этот термин относится к внедрению, поддерживающий `IOleDocument` и соответствующие интерфейсы. Эта технология имеет много потенциальных приложений, таких как деталь реализации COM документов, окон инструментов в Visual Basic 5.0, в конструкторы ActiveX в Visual Basic 6.0 и т. д.  
  
 документ  
 Используется для обозначения к документу в целом — как `DocData` и `DocView`. Например, содержит DocumentFrame `DocView`, но он также сохраняет ссылку на `DocData` для обработки сохраняемости.  
  
 DocView  
 DocObject/внедрения/области окна с помощью которого пользователь взаимодействует для просмотра и управления базового `DocData`. Обратите внимание на то, что пользователи не могут использовать разделения документов и представлений, который является частью `DocObject` разработка интерфейса. Пользователям использовать весь DocObject в качестве представления вместо использования более абстрактными (и менее Формализованная) понятие базовых данных, известный как `DocData`. `DocView` объекты всегда внедряются с объектами фрейма документа (дочерних окон интерфейса MDI), интегрированной среды разработки.  
  
 DTE  
 `DTE` Объект (расширения средств разработки) является точкой доступа верхнего уровня в модели автоматизации Visual Studio, который позволяет программно автоматизации и расширения интегрированной среды разработки.  
  
 Окно динамической справки  
 Окно инструментов, реализованным в интегрированной среде разработки и отображает список ключевое слово поиска или разделы справки F1.  
  
 редактор  
 Код (класса CLSID), который реализует `DocView`. Он также реализует `DocData` Если поддерживается разделение представления или данных.  
  
 расширение  
 Функция, которая изменяет, настраивает или добавляет интегрированная среда разработки. Создании расширений с помощью модели автоматизации или пакеты VSPackage.  
  
 внешний редактор  
 Редактор, который не относится к интегрированной среде разработки, таких как Microsoft Word. Он был зарегистрирован через собственные механизмы и может использоваться за пределами интегрированной среды разработки. Если этот редактор можно внедрять, он отображается в окне в интегрированной среде разработки. Если он не может быть внедрен, создается отдельным окном верхнего уровня.  
  
 иерархия  
 Дерево узлов, каждый узел, связанный с набором свойств.  
  
 независимый компонент верхнего уровня  
 Компонент, который использует немодальное окна верхнего уровня и может эффективно работать как окно автономного приложения, но реализован в виде объекта в процессе. Таким образом — независимый компонент верхнего уровня необходимо согласовать модальности и циклических служб сообщений с помощью интегрированной среды разработки. В процессе объекты не имеют собственный цикл обработки сообщений.  
  
 Поставщик сведений о  
 Поставщика данных — это модуль, который можно ключевые слова поиска и возвращает список разделов, в виде `IVsUserContextItem` объектов. Чтобы предоставить элементы ключевое слово F1 и поиска для поставщика данных, зарегистрируйте скомпилированном файле справки (. HxS) в системе. Разделы справки в эти файлы используются для предоставления список разделов, отображаемых в окне «Динамическая справка» и отображается ли пользователь нажимает клавишу F1.  
  
 компонент на месте  
 Объект VSPackage, реализующий интерфейс `IOleInPlaceComponent` интерфейс для управления окном, визуально содержащийся в окне документа, принадлежащие интегрированной среды разработки. Компоненты на месте не участвуют в стандартный OLE-слияние меню; Вместо этого они интегрировать свои элементы пользовательского интерфейса в интегрированной среде разработки.  
  
 Существует два типа компонентов на месте: жесткую привязку на месте компонентов и элементов управления компонент.  
  
 Компоненты на месте жесткую привязку имеют меню, панелей инструментов и команды, которые тесно интегрированы в пользовательском интерфейсе интегрированной среды разработки, отображаются в виде, если они были созданы непосредственно в интегрированной среде разработки.  
  
 Элементы управления компонента имеет свои собственные элементы пользовательского интерфейса, интегрированы в интегрированной среде разработки; Вместо этого они используют, меню, команд и панелей инструментов интегрированной среды разработки. Например можно полужирным команды будут выводиться полужирным шрифтом слова в элемент управления форматированным текстом, внедренного в форму. Тем не менее элементы управления компонентов можно запросить отображение элементов пользовательского интерфейса динамически установленных специфических для компонентов.  
  
 языковая служба  
 Набор объектов, которая позволяет разработчикам VSPackage для реализации возможностей редакторов кода языка компьютера, такие как текст, пометки и выделения цветом.  
  
 Проект прочих файлов  
 Проект, используемый для дома открытых файлов, которые не являются в любом проекте. Список элементов в этом проекте не сохраняется.  
  
 проект  
 Проекты состоят из объектов иерархии или COM-объекты, реализующие `IVsHierarchy` интерфейс.  
  
 Конструктор конкретного проекта или редактор  
 Конструктор, который не может использоваться независимо от типа проекта. Все конструкторы конкретного проекта должен ввести данные фабрики редактора в реестре. Интегрированной среды разработки можно создать экземпляр конструктора при открытии файлов определенных типов в конкретного проекта.  
  
 окно проекта  
 Окно, которое постоянно отслеживает текущий активный проект иерархии и элемента из контекста глобального выделения. Использовать тип проекта windows `SVsTrackSelectionEx` предупредите IDE, изменения и отображения обратной связи пользователю службы. Обозреватель решений — пример окна тип проекта.  
  
 Окно \"Свойства\"  
 Прежнее название — обозреватель свойств.  
  
 Ссылки проектов  
 Проект, не требуются файлы проекта должны находиться в том же каталоге. Вместо этого ссылки на файлы из других каталогов несвязанных хранятся и обслуживается в самом проекте.  
  
 таблице выполняющихся документов  
 Внутренняя структура, по которому интегрированная среда разработки поддерживает список всех открытых документов. Этот список включает все открытые документы в памяти независимо от ли документы момент редактируется. Документ является любой элемент, который сохраняется, включая хранимые процедуры, открывается в редакторе, файлы в проекте или основного файла проекта (например, файл *.vcproj).  
  
 Контекст выделения  
 Данные, является частью подробности каждого окна в интегрированной среде разработки и используется для отслеживания active выбранных элементов. Выделенный фрагмент состоит из:  
  
-   Указатель на `IVsHierarchy` интерфейс иерархии проекта.  
  
-   Идентификатор элемента проекта.  
  
-   Указатель на `ISelectionContainer` интерфейса, предоставляя доступ к свойствам для активных объектов.  
  
-   Массив значений элементов.  
  
 служба  
 Контракт для набора интерфейсов COM, которые находятся в одном объекте COM. При создании службы, которая определяется GUID, можно определить набор COM-интерфейсов, который выполняет служба. COM-объекты использовать службы для взаимодействия друг с другом.  
  
 Решение  
 Группа связанных проектов, с которыми работает пользователь.  
  
 стандартный конструктор  
 Конструктор, который может использоваться не зависят от типа проекта. Все стандартные конструкторы должен ввести данные фабрики редактора в реестре. Интегрированной среде разработки можно создать экземпляр конструктора при открытии файла с определенным расширением. Данные необходимо сохранить в файле.  
  
 стандартный редактор  
 Редактор, который может использоваться независимо от любого конкретного типа проекта. Такие редакторы кода используют EditorFactories зарегистрирован в реестре. Это позволяет интегрированной среды разработки найти и запустить редактор.  
  
 стандартный редактор ОС  
 Внедрение, который не является Visual Studio конкретных. Он зарегистрирован с помощью хорошо известных ключей Win32 (например, в обозревателе Win32 может вызвать). Если могут быть встроены такие редактор, редактор будет по-прежнему отображаться в его место в интегрированной среде разработки. В противном случае такие редакторов создается отдельным окном верхнего уровня.  
  
 контейнер вложенного контекста  
 `IVsUserContext` Объект, связанный с контейнером контекста. Этот объект содержит ключевые слова поиска, ключевые слова F1 и атрибуты для выделения в пределах компонента интегрированной среды разработки. Подконтекста примеры команды в окно инструментов или ключевое слово в редакторе.  
  
 Список задач  
 Окно инструментов, который реализуется с помощью IDE и отображается список активных задач.  
  
 Текстовый буфер  
 Общее имя для объекта `VSTextBuffer`.  
  
 Представление текста  
 Общее имя для объекта `VSTextView`.  
  
 Средство компонент верхнего уровня  
 Компонент, который действует как немодальные всплывающее окно, тесно координацию с пользовательским интерфейсом интегрированной среды разработки. Как независимые компоненты верхнего уровня средство верхнего уровня компонентов также необходимо согласовать модальности и циклических служб сообщений с помощью интегрированной среды разработки.  
  
 компонент верхнего уровня  
 Объект VSPackage, который управляет немодальное окно верхнего уровня, а не клиентской области окна интегрированной среды разработки. Компоненты верхнего уровня реализуют `IOleComponent` интерфейс, чтобы воспользоваться преимуществами циклических служб сообщений, таких как доступ к времени простоя.  
  
 Активным в пользовательском Интерфейсе  
 Объект VSPackage, который является видимым и в данный момент имеет фокус.  
  
 Иерархии пользовательского интерфейса  
 COM-объект, реализующий `IVsUIHierarchy` интерфейс, позволяющий отображать иерархию. Реализует окно иерархии пользовательского интерфейса `ISelectionContainer` интерфейс для обновления окна свойств; в других типов проектов windows можно использовать эту реализацию, при необходимости.  
  
 VSCT  
 Visual Studio Command Table. Vsct-файл содержит сведения о размещении и поведение меню, панелей инструментов и команды в формате XML.  
  
 VSPackage  
 Устанавливаемые часть программного обеспечения, который расширяет возможности Visual Studio IDE, задавая один или несколько из следующих: пользовательский интерфейс, служб, типы проектов или редактора или конструктора. VSPackage состоит из COM-объект, реализующий `IVsPackage` интерфейс и один или несколько других COM-объектов, которые реализуют другие интерфейсы для поддержки выбора и другие функции. Кроме того пакет VSPackage потребуются определенной регистрации.
