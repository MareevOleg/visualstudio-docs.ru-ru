---
title: "Средства оценки для Visual Studio | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 94e0e9a3-440c-4943-ad7b-772ed742e034
caps.latest.revision: 3
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 3
---
# Средства оценки для Visual Studio
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

## Контрольный список мастерства для Visual Studio  
 Используйте этот контрольный список для оценки качества работы пользователя подробности взаимодействие и visual.  
  
### Обзор  
  
-   Убедитесь, что все команды в обратной связи, который сообщает пользователям, что их команды была выполнена.  
  
-   Убедитесь, что все элементы пользовательского интерфейса и элементы управления отображаются все темы и в режиме высокой контрастности.  
  
-   Убедитесь, что выбор неактивными всегда отличаются, как стандартные и режима высокой контрастности.  
  
-   Убедитесь, что фокус всегда является видимым и очевидным.  
  
### Производительность  
  
-   Убедитесь, что некоторые индикатор вида «занят» отображаются, если команда имеет более чем одну секунду.  
  
-   Убедитесь, что если команды занимает более 10 секунд для выполнения явного индикатор, либо определенный \(рекомендуется\) или не определен, отображается.  
  
### Текст пользовательского интерфейса  
  
-   Убедитесь, что все метки, предложения или заглавные буквы и текст не является полностью нижнего регистра.  
  
    ||Исправление|Неверный|  
    |-|-----------------|--------------|  
    |**Текст команды \(все\)**|Регистр предложения:<br /><br /> **Имя каталога:**|Имя каталога:|  
    |**Текст кнопки \(клиент\)**|Заглавные символы:<br /><br /> **\[Установить по умолчанию\]**|SET AS DEFAULT|  
    |**Текст кнопки \(в сети\)**|Регистр предложения:<br /><br /> **\[По умолчанию\]**||  
  
-   Убедитесь, что все метки, за исключением заголовков групп и кнопок, заканчиваться точкой с запятой и предшествовать элемента управления, с которыми они сопоставляются.  
  
-   Убедитесь, что кнопки, команды и ссылки на команды, запустить пользовательский Интерфейс для захвата ввод данных пользователем заканчиваются многоточие **\[...\]**.  
  
     Примеры  
  
    -   **\[Дополнительно\]** кнопку в диалоговом окне.  
  
    -   Параметры команды в меню «Сервис» \(**Сервис \> Параметры**\) не должны получить многоточие, поскольку запуск самого диалогового окна является целью команды.  
  
-   Убедитесь, что пользовательский Интерфейс содержит без сокращений, за исключением стандартных терминов. Например HTML, ни TCP\/IP необходимо уточнять, хотя нехватки памяти \(недостаточно памяти\) и PII \(персональные данные\) должны.  
  
### Доступ с клавиатуры  
  
-   Убедитесь, что существует способ выполнения каждой задачи с помощью клавиатуры. Обычно это достигается через использование клавиатуры для каждого элемента управления, но для некоторых наглядные областей приемлемо обходной путь, например перейти в представление кода.  
  
-   Убедитесь, что нажатии клавиши Tab между элементами управления в логическом порядке \(справа налево и сверху вниз\). Хотя это рекомендуется для большинства элементов управления, не все элементы управления требуют этот подход. Например проверьте этот переключатель, элементы управления в группе на одну позицию табуляции.  
  
-   Убедитесь, что все элементы управления имеют метки, а каждая метка имеет назначенный \(исключения включать некоторые элементы управления не с меткой, которые может выполнить с меткой элемента управления на вкладке\).  
  
-   Убедитесь, что нет назначенной конфликтов.  
  
### Шрифты  
  
-   Убедитесь, что все шрифты \(шрифта, размер, цвет\) используются постоянно и поддержания иерархии.  
  
-   Убедитесь, что все элементы пользовательского интерфейса в службе шрифт среды. \(См. [Шрифты и форматирование для Visual Studio](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md)\)  
  
     Чтобы проверить, используется ли служба, перейдите к **Сервис \> Параметры \> шрифты и цвета**. В раскрывающемся списке параметров выберите шрифт среды разработки и изменить начертание шрифта stylistically \(например Шашков или комикс Sans\) и задайте размер 12 пт. Нажмите кнопку ОК. Может потребоваться перезапуск IDE, но большинство пользовательского интерфейса изменяется немедленно. Области, которые не обнаружат изменений шрифта даже при перезапуске не используется шрифт среды разработки.  
  
-   Убедитесь, что шрифты, которые являются производным от службы \(например, увеличенный или полужирным шрифтом\), сохраните их размер и формат относительно текста «обычный», когда изменяется размер шрифта среды.  
  
-   Убедитесь, что нет ошибок обрезки, из\-за увеличенную шрифты. Шрифты, исказиться, скорее всего, в результате элементы управления фиксированную высоту или контейнеры фиксированную высоту.  
  
### Диалоговые окна  
  
-   Убедитесь, что заголовок диалогового окна таким же, как команда, в которой она была запущена.  
  
-   Убедитесь, что все стандартные элементы управления, согласованные с операционной системой: стандартный цвет фона и элементы управления не должны иметь специальные шаблонного re стиль, который делает их отличаться от стандартных элементов управления.  
  
-   Убедитесь, что поля в форме должны быть 12 пикселов и должен отображаться единую.  
  
-   Убедитесь, что диалоговые окна отображаются по центру в оболочке интегрированной среды разработки или окно, которое порождается их.  
  
-   При полезны, диалоговые окна должен быть изменяемым размером. Для диалоговых окон, которые можно изменять убедитесь, что после изменения размера, соответствующие элементы управления, нужно изменить размер хотя другие части диалогового окна остаются постоянными.  
  
-   Убедитесь, что диалоговые окна регулируемого размера сохраняться любого размера корректируется пользователя \(размер, расположение, расширения элементов управления диалоговых окон и т. д.\).  
  
-   Убедитесь, что нет значок в строке заголовка.  
  
-   Убедитесь, что отсутствуют кнопки свертывания и развертывания в строке заголовка.  
  
#### Диалоговое окно кнопок операций \(только клиент VS\)  
  
-   Убедитесь, что операция кнопок в следующем порядке: **ОК**, **Отменить**, **Применить**.  
  
-   Убедитесь, что **ОК** и **Отменить** кнопки имеют стандартный размер: 75 x 23 пикселей.  
  
-   Убедитесь, что **ОК** и **Отменить** кнопки будут одинакового размера независимо от длины строки.  
  
-   Если метка кнопки операция требует кнопки будет больше, чем стандартные, убедитесь, что соответствующие **Отменить** кнопка является одинакового размера.  
  
-   Убедитесь, что отступ 6 пикселей между кнопками и связанные элементы управления.  
  
-   Убедитесь, что **ОК** и **Отменить** кнопки имеют клавиш доступа определяется подчеркнутую букву.  
  
-   Убедитесь, что одна кнопка \(обычно **ОК**\) по умолчанию имеет фокус.  
  
-   Убедитесь, что **Esc** отменяет диалогового окна  
  
-   Убедитесь, что **ВВОД** выполняет кнопку по умолчанию, если фокус установлен не на элемент управления, который обрабатывает ввод.  
  
-   Убедитесь, что **ОК** и **Отменить** кнопки расположены в нижнем правом углу диалогового окна. В редких исключений допустимо для них вертикально в правом верхнем углу.  
  
-   Убедитесь, что вертикальная конфигурация используется только в том случае, если другие кнопки находятся в выравнивание по горизонтали в диалоговом окне.  
  
### Стандарты управления  
  
#### Общие правила  
  
-   Убедитесь, что, когда это возможно, оптимальное значение по умолчанию значения для ускорения взаимодействия с пользователем и предоставить пользователям к безопасным или общий результат.  
  
-   Убедитесь, что стандартные элементы управления ведут себя так же, чтобы пользователи знали, что произойдет на основе опыта предыдущих.  
  
#### Элементы управления Label  
  
-   Проверьте, каждый элемент управления имеет метку, каждая метка визуально объединяется с его элемента управления \(обычно в пределах диапазона точек 4\-6\) и ближе к его соответствующий элемент управления чем для других элементов управления.  
  
-   Убедитесь, что метки располагаются Сброс левого края, если разместить над слева с элементом управления и по центру по горизонтали, чтобы базовые метки выравнивается с базовым планом входного текста, если расположено слева.  
  
-   Убедитесь, что если несколько с накоплением метки и элементы управления вводом располагаются слева от элемента управления, метки левому и никогда не равно расстояние от края диалогового окна, сброса вправо и на одинаковом расстоянии от элементов управления. Пары должен равномерно распределены, если они не требуются дополнительные интервалы для указания группирования.  
  
#### Элементы управления вводом \(текстовые поля и поля со списком\)  
  
-   Убедитесь, что при использовании среды шрифта по умолчанию, высота отображения текстовые поля, раскрывающиеся списки и кнопки все пиксели 23.  
  
-   Если используется текст подсказки, убедитесь, что цвет `Environment.ControlEditHintText` с помощью службы цвет.  
  
-   Если поле является обязательным, должны быть определены таким образом, проверьте:  
  
    -   Задаваемое фон `Environment.ControlEditRequiredBackground` и переднего плана `Environment.ControlEditRequiredHintText`  
  
    -   что является пояснительный текст в элементе управления, который отображается в виде **«\< необходимые \>»**  
  
#### Кнопочные элементы управления  
  
-   Убедитесь, что кнопки минимальный размер 75 x 23 пикселов, если не поддерживает более длинный текст.  
  
-   Убедитесь, что кнопок остался и правой 3\-5 пикселов, а также заполнения содержимого поля.  
  
-   Допускается использовать небольшой квадратную кнопку с многоточием только **\[...\]** на его вместо **\[Обзор...\]** кнопки \(или аналогичную функциональность\). Если используется, проверьте кнопки 23 x 23 размер.  
  
-   Если имеется более одного **\[Обзор...\]** кнопку в диалоговом окне, а затем убедитесь, что укороченная версия \(только с многоточием **\[...\]**\) используется для всех.  
  
-   Убедитесь, что многоточие **\[...\]** кнопки имеют назначенный. Когда фокус находится на элемент управления рядом с ним, одна вкладка следует переместить фокус на кнопку с многоточием.  
  
-   Проверьте, кнопки, команды и ссылки на команды, запуска дополнительного пользовательского интерфейса, которое собирает дополнительные входные данные пользователя должны завершаться в многоточие **\[...\]**.  
  
#### Гиперссылки  
  
-   Убедитесь, что элемент управления hyperlink никогда не мигает красным, когда активны. Это является признаком цвет службы не выполняется использования  
  
-   Убедитесь, что используемые цвета VS:  
  
    -   `Environment.ControlLinkText`  
  
    -   `Environment.ControlLinkTextHover`  
  
    -   `Environment.ControlLinkTextPressed`  
  
-   Убедитесь, что гиперссылки синей линией не Если встроен в абзаце.  
  
#### Флажки  
  
-   Если флажок имеет многострочный текст, убедитесь, что поле выравнивается с первой строки текста, не по центру по вертикали во всех строках.  
  
-   Убедиться, что флажки всегда указывают двоичный Выбор и не направления пользователей или открытия новых окон или страниц.  
  
-   Если флажок представляет параметр, относящиеся к элементу управления вводом, убедитесь, что он расположен непосредственно слева и очень близко под этим элементом управления, чтобы указать его связь.  
  
-   Убедитесь, что флажок **никогда не** использоваться в качестве средства, чтобы включить все содержимое страницы или диалоговое окно.  
  
#### Группы полей  
  
-   Убедитесь, что диалоговое окно не содержат одну группу поле внутри него, содержащий все содержимое диалогового окна.  
  
-   Убедитесь, что по крайней мере два элемента управления в каждой группы.  
  
-   Редко должно быть более чем две группы в диалоговом окне.  
  
-   Убедитесь, что нет вложенных групп.  
  
### Значки  
  
-   Убедитесь, что значки отображаются правильно инвертированный в темной темы.  
  
-   Убедитесь, что все значки основаны на основные понятия.  
  
-   Убедитесь, что каждый значок distinct, легко распознавать и не содержит более двух концепций \(без модификатора состояния и язык\).  
  
-   Убедитесь, что базовый значок отображается по центру в пространстве.  
  
-   Убедитесь, что все значки отображаются разборчивым в режиме высокой контрастности.  
  
-   Проверьте, цвет, используемый соответствует стандартам использование цвета.  
  
-   Убедитесь, что не Ореолы \(границы\) вокруг значков. \(Если он имеется, halo должен соответствовать цвет фона соседних элементов пользовательского интерфейса\).  
  
### Поддержка сенсорного ввода пользовательского интерфейса  
  
-   Убедитесь, что достаточно велик, чтобы быть легко физические — минимальный интерактивные элементы управления **пикселей 23 x 23** размер  
  
-   Убедитесь, что по крайней мере, наиболее часто используемые элементы управления **40 x 40 пикселей** в размере.  
  
-   Убедитесь, что интерактивные элементы управления имеют по крайней мере **5 точек интервала** между ними