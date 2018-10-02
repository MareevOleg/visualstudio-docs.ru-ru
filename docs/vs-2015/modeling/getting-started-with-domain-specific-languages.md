---
title: Приступая к работе с доменными языками | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 024392a2-2c04-404f-a27b-7273553c3b60
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 128c96c6bd400f74ac698df550fdba70ffec2eed
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47557571"
---
# <a name="getting-started-with-domain-specific-languages"></a>Начало работы с доменными языками
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [Приступая к работе с доменными языками](https://docs.microsoft.com/visualstudio/modeling/getting-started-with-domain-specific-languages).  
  
В этом разделе приводятся основные концепции в определении и использовании доменный язык (DSL), созданных с помощью пакета SDK моделирования для Visual Studio.  
  
 Если вы не знакомы с DSL впервые, мы советуем работать через **лаборатории средства DSL**, который можно найти на этом сайте: [пакет и пакет SDK моделирования](http://go.microsoft.com/fwlink/?LinkID=186128)  
  
## <a name="what-can-you-do-with-a-domain-specific-language"></a>Что можно сделать с помощью предметно-ориентированного языка?  
 Доменный язык представляет собой нотацию, обычно графическом, предназначены для использования для определенной цели. Напротив языки, такие как UML, общего назначения. В DSL можно определить типы элементов модели и их отношений и, как они будут представлены на экране.  
  
 При созданной DSL можно распределить его как часть пакета Visual Studio Integration Extension (VSIX). Пользователи работают с DSL в [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]:  
  
 ![Схема семейного дерева элементов и обозревателе](../modeling/media/familyt-instance.png "FamilyT_Instance")  
  
 Нотация является только частью DSL. Надпись пакет VSIX включает средства, пользователи могут применять для редактирования и формирования материала из своих моделей.  
  
 Одно из приложений участника доменных языков — создавать программный код, файлы конфигурации и другие артефакты. Особенно в крупных проектах и линии товаров, где будут создаваться несколько вариантов продукта, создании многие аспекты из доменных языков можно предоставить значительное увеличение надежности и очень быстрого реагирования на изменения требований.  
  
 Остальная часть в этом обзоре — Пошаговое руководство, которое представляет основные операции создания и использования доменного языка в [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для определения доменного языка необходимо установить следующие компоненты.  
  
|||  
|-|-|  
|[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185579](http://go.microsoft.com/fwlink/?LinkId=185579)|  
|[!INCLUDE[vssdk_current_short](../includes/vssdk-current-short-md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185580](http://go.microsoft.com/fwlink/?LinkId=185580)|  
|Пакет SDK моделирования для Visual Studio|[Скачайте MSDK](http://www.microsoft.com/download/details.aspx?id=40754)|  
  
## <a name="creating-a-dsl-solution"></a>Создание решения DSL  
 Чтобы создать новый доменный язык, создайте новый [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] решения с помощью шаблона проекта доменного языка.  
  
#### <a name="to-create-a-dsl-solution"></a>Создание решения DSL  
  
1.  В меню **Файл** выберите пункт **Создать**, а затем команду **Проект**.  
  
2.  В разделе **типы проектов**, разверните **другие типы проектов** и щелкните **расширяемости**.  
  
3.  Нажмите кнопку **конструктора доменного языка**.  
  
     ![Создание диалогового окна DSL](../modeling/media/create-dsldialog.png "Create_DSLDialog")  
  
4.  В **имя** введите **FamilyTree**. Нажмите кнопку **ОК**.  
  
     **Мастер доменного языка** открывает и отображает список шаблонов решений DSL.  
  
     Нажмите на каждый шаблон, чтобы просмотреть описание,  
  
     Шаблоны полезны отправные точки. Каждая из них предоставляет полный рабочий DSL, который можно изменить в соответствии с потребностями. Обычно выбирается шаблон ближайшего вы хотите создать.  
  
5.  В этом пошаговом руководстве выберите **минимальный язык** шаблона.  
  
6.  Введите расширение имени файла для DSL на соответствующей странице мастера. Это расширение будут использовать файлы, содержащие экземпляры DSL.  
  
    -   Выберите расширение, которое не связан с любым приложением, на своем компьютере или на любом компьютере, где вы хотите установить DSL. Например **docx** и **htm** использовать нельзя расширений.  
  
    -   Мастер предупредит, если расширение уже используется в качестве DSL. В этом случае выберите другое расширение имени файла. Можно также сбросить экземпляр экспериментального пакета SDK для Visual Studio, чтобы удалить старые экспериментальные конструкторы. Нажмите кнопку **запустить**, нажмите кнопку **все программы**, **Microsoft Visual Studio 2010 SDK**, **средства**, а затем **Сброс Microsoft Visual Studio 2010 экспериментальный экземпляр**.  
  
7.  Просмотреть другие страницы, а затем нажмите кнопку **Готово**.  
  
     Создается решение, который содержит два проекта. Они называются Dsl и DslPackage. Файл схемы откроется то есть именованный DslDefinition.dsl.  
  
    > [!NOTE]
    >  Большая часть кода, который можно увидеть в папках в двух проектах, созданный DslDefinition.dsl. По этой причине большинство со своим DSL изменений в этот файл.  
  
 После этого пользовательский интерфейс примет следующий вид:  
  
 ![Конструктор DSL](../modeling/media/dsl-designer.png "dsl_designer")  
  
 Данное решение определяет доменный язык. Дополнительные сведения см. в разделе [Обзор пользовательского интерфейса средства доменного языка](../modeling/overview-of-the-domain-specific-language-tools-user-interface.md).  
  
## <a name="the-important-parts-of-the-dsl-solution"></a>Важные части решения DSL  
 Обратите внимание, что следующие аспекты новое решение.  
  
-   **Dsl\DslDefinition.DSL** это файл, что вы видите, при создании решения DSL. Практически весь код в решении создается из этого файла, и большинство изменений, внесенные в определении DSL совершенные здесь. Дополнительные сведения см. в разделе [работа со схемой определений доменных ЯЗЫКОВ](../modeling/working-with-the-dsl-definition-diagram.md).  
  
-   **Проект DSL** этот проект содержит код, который определяет доменный язык.  
  
-   **Проект DslPackage** этот проект содержит код, который позволяет экземпляры DSL, чтобы открыть и редактировать в [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
##  <a name="Debugging"></a> Под управлением DSL  
 В решение DSL можно запустить сразу же после его создания. Позже можно изменить определение DSL постепенно, при запуске решения еще раз после каждого изменения.  
  
#### <a name="to-experiment-with-the-dsl"></a>Чтобы поэкспериментировать с DSL  
  
1.  Нажмите кнопку **преобразовать все шаблоны** в панели инструментов обозревателя решений. Будет повторно создан большую часть исходного кода из DslDefinition.dsl.  
  
    > [!NOTE]
    >  При каждом изменении DslDefinition.dsl, необходимо нажать кнопку **преобразовать все шаблоны** перед перестроением решения. Этот шаг можно автоматизировать. Дополнительные сведения см. в разделе [как автоматизировать преобразовать все шаблоны](http://msdn.microsoft.com/en-us/b63cfe20-fe5e-47cc-9506-59b29bca768a).  
  
2.  Нажмите клавишу F5, или на **Отладка** меню, щелкните **начать отладку**.  
  
     DSL, сборок и является в экспериментальном экземпляре [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
     Запустится экспериментальный экземпляр [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Экспериментальный экземпляр принимает его параметры из отдельное поддерево реестра, где [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] зарегистрировать расширения для целей отладки. Обычный экземпляров [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] не имеют доступа к расширениям, зарегистрированы.  
  
3.  В экспериментальном экземпляре [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], откройте файл модели, с именем **теста** из **обозревателе решений**.  
  
     \- или -  
  
     Щелкните правой кнопкой мыши проект "Отладка", выберите пункт **добавить**, а затем нажмите кнопку **элемент**. В **Добавление элемента** диалоговое окно, выберите тип файла в вашего DSL.  
  
     Файл модель открывается как пустая диаграмма.  
  
     Панели элементов открывает и отображает средства, соответствующие типу схемы.  
  
4.  Средства для создания фигур и соединителей на схеме.  
  
    1.  Для создания фигур, перетащите из средства пример фигуры на схему.  
  
    2.  Для соединения двух форм, средство пример соединителя, первая фигура и затем нажмите кнопку эту фигуру.  
  
5.  Выберите метки, фигур, чтобы изменить их.  
  
 Экспериментальный экземпляр [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] будет выглядеть следующим образом:  
  
 ![](../modeling/media/dsl-min.png "DSL_min")  
  
### <a name="the-content-of-a-model"></a>Содержимое модели  
 Содержимое файла, который является экземпляром класса DSL называется *модели*. В модели содержится *модели ** элементы* и *ссылки* между элементами. Определение DSL определяет, какие типы элементов модели и ссылки могут существовать в модели. Например в DSL, созданном из шаблона минимальный язык, имеется один тип элемента модели и одного типа ссылки.  
  
 Определение DSL можно указать, каким образом модель отображается на схеме. Можно выбрать из множества стилей фигур и соединителей. Можно указать, что некоторые фигуры отображаются внутри других фигур.  
  
 Модель можно просмотреть в виде дерева в **Explorer** просмотра при изменении модели. Добавление фигуры в схему, элементы модели также отображаются в обозревателе. Даже при наличии нет схемы, можно использовать обозреватель.  
  
 Если не отображается в обозревателе в экземпляре отладки [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]на **представление** пункты меню **Other Windows**и нажмите кнопку  *\<ваш язык >* **Explorer**.  
  
### <a name="the-api-of-your-dsl"></a>API-Интерфейс доменного языка  
 DSL создает API, который дает возможность чтения и обновления моделей, которые являются экземплярами класса DSL. Одно приложение API-интерфейса — Создание текстовых файлов из модели. Дополнительные сведения см. в разделе [создание кода во время разработки с помощью текстовых шаблонов T4](../modeling/design-time-code-generation-by-using-t4-text-templates.md).  
  
 В решении "Отладка" откройте файл шаблона с расширением «.tt». Эти примеры демонстрируют, как создание текста из моделей и использовать при тестировании API вашего DSL. Один из примеров создается на языке [!INCLUDE[vbprvb](../includes/vbprvb-md.md)], другие в [!INCLUDE[csprcs](../includes/csprcs-md.md)].  
  
 В каждом шаблоне файл является файлом, он создает. Разверните узел файла шаблона в обозревателе решений и откройте созданный файл.  
  
 Файл шаблона содержит краткое сегмент кода, который перечисляет все элементы в модели.  
  
 Созданный файл содержит результат.  
  
 Когда вы изменяете файл модели, вы увидите соответствующие изменения в созданные файлы после повторного создания файлов.  
  
##### <a name="to-regenerate-text-files-after-you-change-the-model-file"></a>Чтобы повторно создать текстовые файлы, после изменения файла модели  
  
1.  В экспериментальном экземпляре [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], сохраните файл модели.  
  
2.  Убедитесь, что параметр имени файла в каждый tt-файл ссылается на файл модели, используемой для экспериментов. Сохраните tt-файл.  
  
3.  Нажмите кнопку **преобразовать все шаблоны** на панели инструментов в **обозревателе решений**.  
  
     \- или -  
  
     Щелкните правой кнопкой мыши шаблоны, которые вы хотите повторно создать, а затем нажмите кнопку **пользовательское средство**.  
  
 Можно добавить любое количество файлов текстового шаблона в проект. Каждый шаблон создает один файл результатов.  
  
> [!NOTE]
>  При изменении определения DSL, код примера текстового шаблона не будет работать, пока разработчик не обновит его.  
  
 Дополнительные сведения см. в разделе [создание кода из доменного языка](../modeling/generating-code-from-a-domain-specific-language.md) и [написание кода для настройки доменного языка](../modeling/writing-code-to-customise-a-domain-specific-language.md).  
  
## <a name="customizing-the-dsl"></a>Настройка DSL  
 Если вы хотите изменить определение DSL, Закройте экспериментальный экземпляр и обновить определение главного [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] экземпляра.  
  
> [!NOTE]
>  После изменения определения DSL, то можно потерять сведения тестирования моделей, созданных с помощью предыдущих версий.  Например решение для отладки содержит файл с именем примера, который содержит несколько фигур и соединителей. После начала разработки Определение DSL, они не будут видны, и они будут потеряны при сохранении файла.  
  
 Можно внести самые разнообразные расширения DSL. Следующие примеры обеспечит с будущими возможности.  
  
 После каждого изменения, сохраните определение DSL, нажмите кнопку **преобразовать все шаблоны** в **обозревателе решений**, а затем нажмите клавишу **F5** экспериментировать с измененные DSL.  
  
### <a name="rename-the-types-and-tools"></a>Переименование типов и средства  
 Переименование существующих классов доменов и отношений. Например начиная от определения Dsl, созданные на основе шаблона минимальный язык, удалось выполнить следующие операции переименования, чтобы DSL представляют семейства деревьев.  
  
##### <a name="to-rename-domain-classes-relationships-and-tools"></a>Чтобы переименовать классов доменов, связи и средства  
  
1.  В диаграмме DslDefinition Переименуйте **ExampleModel** для **FamilyTreeModel**, **ExampleElement** для **Person**,  **Целевые объекты** для **родителям**, и **источников** для **дочерние элементы**. Если щелкнуть каждой метки, чтобы изменить его.  
  
     ![Схема определения DSL &#45; семейного древа Тюдор](../modeling/media/familyt-person.png "FamilyT_Person")  
  
2.  Переименуйте элемент и соединитель средства.  
  
    1.  Откройте окно обозревателя DSL на вкладке под обозревателем решений. Если вы не может его найти, в **представление** пункты меню **Other Windows** и нажмите кнопку **обозреватель DSL**. Обозреватель DSL является видимым только в том случае, если в схему определения DSL является активным окном.  
  
    2.  Откройте окно свойств и поместите его так, чтобы вы видите обозреватель DSL и свойства в то же время.  
  
    3.  В обозревателе DSL разверните **редактор**, **вкладки панели элементов**,  *\<DSL >*, а затем **средства**.  
  
    4.  Нажмите кнопку **ExampleElement**. Это элемент панели инструментов, который используется для создания элементов.  
  
    5.  В окне «Свойства» измените **имя** свойства **Person**.  
  
         Обратите внимание, что **заголовок** повлечет за собой изменение.  
  
    6.  Таким же образом, изменить имя **ExampleConnector** средство для **ParentLink**. ALTER **заголовок** свойство, так что он не является копией имени свойства. Например, введите **родительская ссылка**.  
  
3.  Перестройте DSL.  
  
    1.  Сохраните файл определения DSL.  
  
    2.  Нажмите кнопку **преобразовать все шаблоны** на панели инструментов в обозревателе решений  
  
    3.  Нажмите клавишу F5. Подождите, пока экспериментальный экземпляр [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] отображается.  
  
4.  В решении "Отладка" в экспериментальном экземпляре [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], откройте файл модели тестирования. Перетащите элементы на его из области элементов. Обратите внимание, что средство заголовки и имена типов в обозревателе DSL были изменены.  
  
5.  Сохраните файл модели.  
  
6.  Откройте tt-файл и замените вхождения старые имена типов и свойств с новыми именами.  
  
7.  Убедитесь, что имя файла, который указан в tt-файл указывает модели тестирования.  
  
8.  Сохраните tt-файл. Откройте созданный файл, чтобы просмотреть результат выполнения кода в tt-файл. Убедитесь, что он работает.  
  
### <a name="add-domain-properties-to-classes"></a>Добавление свойств домена в классы  
 Добавьте свойства в класс домена, например для представления год рождения и смерти человека.  
  
 Чтобы отобразить новые свойства на схеме, необходимо добавить *декораторы* форма, которая отображает элемент модели. Также необходимо сопоставить свойства декораторы.  
  
##### <a name="to-add-properties-and-display-them"></a>Для добавления свойств и их отображения  
  
1.  Добавьте свойства.  
  
    1.  В схеме определения DSL, щелкните правой кнопкой мыши **Person** доменного класса, выберите пункт **добавить**, а затем нажмите кнопку **свойства домена**.  
  
    2.  Введите список новые имена свойств, таких как **рождения** и **смерти**. Нажмите клавишу **ввод** после каждого из них.  
  
2.  Добавление декораторов, которые будут отображаться свойства в фигуре.  
  
    1.  Выполните, серую линию, начиная с класса Person домена другой стороне схемы. Это карта элементов схемы. Доменный класс ссылки на класс shape.  
  
    2.  Щелкните правой кнопкой мыши данного класса фигур, выберите пункт **добавить**, а затем нажмите кнопку **текстовый декоратор**.  
  
    3.  Добавить два декораторов с именами, например **BirthDecorator** и **DeathDecorator**.  
  
    4.  Выберите каждый новый декоратор и в окне «Свойства» задайте **позиции** поля. Определяет, где значение свойства домена будет отображаться на фигуре. Например, задать **InnerBottomLeft** и **InnerBottomRight**.  
  
         ![Определение фигуры секции](../modeling/media/familyt-compartment.png "FamilyT_Compartment")  
  
3.  Сопоставьте декораторы к свойствам.  
  
    1.  Откройте окно сведений DSL. Обычно это происходит на вкладке рядом с окном выходных данных. Если не видна, в **представление** последовательно выберите пункты **Other Windows**, а затем нажмите кнопку **подробные сведения о DSL**.  
  
    2.  В схеме определения DSL, щелкните линию, соединяющую **Person** доменного класса для класса shape.  
  
    3.  В **подробные сведения о DSL**на **сопоставления декораторов** , затем щелкните флажок на несопоставленный декоратор. В **отображаемое свойство**, выберите свойство домена, в который будет выполняться сопоставление. Например, сопоставить **BirthDecorator** для **рождения**.  
  
4.  Сохраните DSL, щелкните Преобразовать все шаблоны и нажмите клавишу F5.  
  
5.  В пример модели схемы убедитесь, что можно теперь позиций, на который вы выбрали пункт и введите значения в них. Кроме того, при выборе **Person** фигуры в окне «Свойства» отображаются свойства нового рождения и смерти.  
  
6.  В tt-файл можно добавить код, который получает свойства каждого человека.  
  
 ![Схема семейного дерева элементов и обозревателе](../modeling/media/familyt-instance.png "FamilyT_Instance")  
  
### <a name="define-new-classes"></a>Определять новые классы  
 Классы доменов и отношений можно добавить в модель. Например можно создать новый класс для представления городам и создать связь для представления, что пользователь жили в городе.  
  
 Чтобы сделать distinct различные типы на схеме модели, можно сопоставить доменных классов для различных видов фигур или фигур с другими параметрами и цвета.  
  
##### <a name="to-add-and-display-a-new-domain-class"></a>Чтобы добавить и вывести новый класс домена  
  
1.  Добавление класса домена и дочернего элемента корневого элемента модели.  
  
    1.  В схеме определения DSL щелкните **отношение внедрения** инструмент, щелкните корневой класс **FamilyTreeModel**, а затем щелкните пустую область схемы.  
  
         Новый класс домена появится, который подключен к FamilyTreeModel с отношение внедрения.  
  
         Присвойте ему имя, например **города**.  
  
        > [!NOTE]
        >  Каждый класс домена за исключением корневого модели должен быть целевым объектом хотя бы одного отношения внедрения или наследоваться от класса, который является целевым объектом внедрения. По этой причине часто удобно создать класс домена, используя средство отношение внедрения.  
  
    2.  Добавьте свойство домена в новый класс, например **имя**.  
  
2.  Добавьте отношение ссылки между Person и города.  
  
    1.  Нажмите кнопку **ссылочное отношение** средство, щелкните человека и нажмите кнопку города.  
  
         ![Фрагмент определения DSL: корень семейного дерева](../modeling/media/familyt-root.png "FamilyT_Root")  
  
        > [!NOTE]
        >  Ссылочные отношения представляют перекрестные ссылки из одной части дерева модели в другую.  
  
3.  Добавление фигуры для представления городам на схемах модели.  
  
    1.  Перетащите **геометрическая фигура** из панели элементов на схему и переименуйте его, например **TownShape**.  
  
    2.  В окне «Свойства» задайте внешний вид поля новой фигуры, такие как цвет заливки и Geometry.  
  
    3.  Добавьте декоратор для отображения названия города и переименуйте его NameDecorator. Задайте его свойства Position.  
  
4.  Сопоставьте доменный класс города TownShape.  
  
    1.  Нажмите кнопку **карту элементов схемы** средство, а затем щелкните доменного класса города, а затем класс фигуры TownShape.  
  
    2.  В **оформителя** вкладке **подробные сведения о DSL** выбранное окно с соединителем карты, проверьте NameDecorator и задать **отображаемое свойство** к имени.  
  
5.  Создание соединителя для отображения отношения между Person и городам.  
  
    1.  Перетащите соединительную линию из области элементов на схему. Переименуйте его и задайте его свойства внешнего вида.  
  
    2.  Используйте **карту элементов схемы** , которая позволяет связать новый соединитель связь между Person и города.  
  
         ![Определение семейного дерева с добавленной картой фигур](../modeling/media/familyt-shapemap.png "FamilyT_ShapeMap")  
  
6.  Создание средства элемента для внесения new городе.  
  
    1.  В **обозреватель DSL**, разверните **редактор** затем **вкладки панели элементов**.  
  
    2.  Щелкните правой кнопкой мыши  *\<DSL >* и нажмите кнопку **добавить новое средство элемента**.  
  
    3.  Задайте **имя** свойство новое средство, и задайте его **класс** свойство к работе.  
  
    4.  Задайте **значок панели элементов** свойство. Нажмите кнопку **[...]**  и в **имя файла** выберите файл значка.  
  
7.  Создайте соединитель инструмент для создания ссылки между городам и людей.  
  
    1.  Щелкните правой кнопкой мыши  *\<DSL >* и нажмите кнопку **добавить новое средство соединитель**.  
  
    2.  Установите свойство имени нового инструмента.  
  
    3.  В **ConnectionBuilder** свойства, выберите построитель, который содержит имя человека Городской связи.  
  
    4.  Задайте **значок панели элементов**.  
  
8.  Сохранить определение DSL, нажмите кнопку **преобразовать все шаблоны**, а затем нажмите клавишу **F5**.  
  
9. В экспериментальном экземпляре [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], откройте файл модели тестирования. Используйте новые средства для создания городам и ссылки между городам и лиц. Обратите внимание на то, что можно создать только связи между правильные типы элемента.  
  
10. Создание кода, который перечисляет города, в котором живет каждого пользователя. Текстовые шаблоны являются одним из мест, где можно запустить такой код. Например можно изменить существующий файл Sample.tt отладка решения, чтобы он содержал следующий код:  
  
    ```  
    <#@ template inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation" debug="true" #>  
    <#@ output extension=".txt" #>  
    <#@ FamilyTree processor="FamilyTreeDirectiveProcessor" requires="fileName='Sample.ftree'" #>  
  
    <#  
      foreach (Person person in this.FamilyTreeModel.People)  
      {  
    #>  
        <#= person.Name #><#if (person.Town != null) {#> of <#= person.Town.Name #> <#}#>  
  
    <#  
          foreach (Person child in person.Children)  
      {  
    #>  
                <#= child.Name #>  
    <#  
      }  
      }  
    #>  
  
    ```  
  
     При сохранении файла *.tt, он создаст создается дочерний файл, содержащий список людей и их residences. Дополнительные сведения см. в разделе [создание кода из доменного языка](../modeling/generating-code-from-a-domain-specific-language.md).  
  
## <a name="validation-and-commands"></a>Проверка и команды  
 Можно разработать дальнейшей этот DSL путем добавления ограничения проверки. Эти ограничения являются методами, которые вы можете определить, убедитесь, что модель находится в правильном состоянии. Например можно определить ограничение, чтобы убедиться в том, Дата рождения дочернего более поздняя, чем из его родительских объектов. Функция проверки отображает предупреждение, если пользователь DSL пытается сохранить модель, которая разбивает никакие ограничения. Дополнительные сведения см. в разделе [проверка в доменных языках](../modeling/validation-in-a-domain-specific-language.md).  
  
 Можно также определить команды меню, которые пользователь может вызывать. Команды можно изменить модель. Они также могут взаимодействовать с другими моделями в [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] и с внешними ресурсами. Дополнительные сведения см. в разделе [как: изменение стандартной команды меню](../modeling/how-to-modify-a-standard-menu-command-in-a-domain-specific-language.md).  
  
## <a name="deploying-the-dsl"></a>Развертывание DSL  
 Чтобы разрешить другим пользователям использовать доменный язык, распространении [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] файл расширения (VSIX). Это будет создано при построении решения DSL.  
  
 Найдите VSIX-файл в папке bin для вашего решения. Скопируйте его на компьютер, на котором вы хотите установить его. На этом компьютере дважды щелкните VSIX-файл. DSL можно использовать во всех экземплярах [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] на этом компьютере.  
  
 Можно использовать ту же процедуру для установки DSL на своем компьютере, таким образом, нет необходимости использовать экспериментальный экземпляр [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
 Дополнительные сведения см. в разделе [развертывание решений предметно-ориентированного языка](../modeling/deploying-domain-specific-language-solutions.md).  
  
##  <a name="Reset"></a> Удалить старые экспериментальные доменных языков  
 Если вы создали экспериментальный доменных языков, вы больше не требуется, можно удалить с компьютера, сбросив [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] экспериментальный экземпляр.  
  
 Это приведет к удалению с компьютера все экспериментальные доменных языков и другие экспериментальные [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] расширения. Это расширения, которые были выполнены в режиме отладки.  
  
 Эта процедура не приводит к удалению DSL или другой [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] расширения, которые были полностью установлены, выполнив файл VSIX.  
  
#### <a name="to-reset-the-visual-studio-experimental-instance"></a>Чтобы сбросить экземпляр экспериментального Visual Studio  
  
1.  Нажмите кнопку **запустить**, нажмите кнопку **все программы**, **Microsoft Visual Studio 2010 SDK**, **средства**, а затем **Сброс Microsoft Visual Studio 2010 экспериментальный экземпляр**.  
  
2.  Перестроить все экспериментальные DSL или другие экспериментальные [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] расширений, которые по-прежнему хотите использовать.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о моделях, классах и отношениях](../modeling/understanding-models-classes-and-relationships.md)   
 [Способ определения доменного языка](../modeling/how-to-define-a-domain-specific-language.md)   
 [Пакет SDK пакет и моделирование](http://go.microsoft.com/fwlink/?LinkID=186128)


