---
title: "Основы UX для Visual Studio | Документы Microsoft"
ms.custom: 
ms.date: 04/26/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a793cf7a-f230-43ce-88d0-fa5d6f1aa9c7
caps.latest.revision: 7
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9524ecc3cadef58821fba857de8e82e59eea9b43
ms.openlocfilehash: 19db4e41ef35ddbec4f43823d4bf66bb148a854f
ms.contentlocale: ru-ru
ms.lasthandoff: 05/04/2017

---
# <a name="ux-essentials-for-visual-studio"></a>Основы UX для Visual Studio
## <a name="best-practices"></a>Рекомендации  
  
### <a name="1-be-consistent-within-the-visual-studio-environment"></a>1. Быть согласованы в среде Visual Studio.  
  
-   Выполните существующих [шаблоны взаимодействия](interaction-patterns-for-visual-studio.md) в оболочке.  
  
-   Возможности для согласования с языком visual оболочки конструктора и [мастерства требования](evaluation-tools-for-visual-studio.md).  
  
-   Использование общих команд и элементов управления, если они существуют.  
  
-   Понимание иерархии Visual Studio и как он устанавливает контекст и диски пользовательского интерфейса.  
  
### <a name="2-use-the-environment-service-for-fonts-and-colors"></a>2. Используйте службу среды для шрифтов и цветов.  
  
-   Пользовательского интерфейса должны учитывать текущий [шрифта среды](fonts-and-formatting-for-visual-studio.md) параметр, если не предоставляется для настройки на странице шрифты и цвета в диалоговом окне Параметры.  
  
-   Элементы пользовательского интерфейса необходимо использовать [VSColor службы](colors-and-styling-for-visual-studio.md), использование общих среды маркеров или маркеров определенные функции.  
  
### <a name="3-make-all-imagery-consistent-with-the-new-vs-style"></a>3. Настроить все изображения в соответствии со новый стиль VS.  
  
-   Выполните принципы разработки Visual Studio в качестве значков, глифы и другие рисунки.  
  
-   Не помещайте текста в графических элементов.  
  
### <a name="4-design-from-a-user-centric-perspective"></a>4. Разработка с точки зрения ориентированное на пользователей.  
  
-   Создайте поток задач перед отдельные компоненты в ней.  
  
-   Ознакомьтесь с пользователями и предоставляют эти сведения в явном виде в вашей спецификации.  
  
-   При просмотре пользовательского интерфейса следует оценить завершения работы, а также подробные сведения.  
  
-   Разработка своего пользовательского интерфейса, чтобы она оставалась функциональных возможностей и привлекательный независимо от языка или языка.  
  
## <a name="screen-resolution"></a>Разрешение экрана  
  
### <a name="minimum-resolution"></a>Минимальное разрешение  
 - Минимальное разрешение для Visual Studio Dev14 **1280 x 720**. Это означает, что *возможных* в Visual Studio это разрешение, несмотря на то, что может оказаться оптимального взаимодействия с пользователем. Нет никакой гарантии, что все аспекты будет использовать при разрешении 1280 x 720 ниже.  
  
 - Разрешение целевой для Visual Studio — **1366 x 768**. Это наименьшее разрешение, по которому обещаем *хорошо* взаимодействие с пользователем.

 - Максимальная высота первоначальное **меньше, чем 700 пикселей**, поэтому он не превышает минимальное разрешение IDE кадра 96 точек на дюйм.
  
### <a name="high-density-displays"></a>Отображает высокой плотности  
 Пользовательский Интерфейс в Visual Studio должен хорошо работать в все факторы, которые Windows поддерживает готового разрешение DPI: 150%, 200% и 250%.  
  
## <a name="anti-patterns"></a>Антишаблоны  
 Visual Studio содержит много элементов пользовательского интерфейса приведенных ниже примерах наши рекомендации и лучшие методики. В целях согласованными разработчики часто соответствуют аналогично они создаете шаблоны разработки пользовательского интерфейса продукта. Несмотря на то, что это хороший подход, что помогает нам диска взаимодействие с пользователем и визуального проектирования, в некоторых случаях поставляемых возможности с помощью некоторые сведения, которые не соответствуют нашим рекомендациям из-за ограничений расписание или исключить приоритетов. В таких случаях нам не нужно команды копирования одной из этих «антишаблоны», так как они распространением поврежденные и несогласованные пользовательского интерфейса в среде Visual Studio.  
  
### <a name="required-fieldssettings-shown-in-error-state-by-default"></a>Требуемые поля и параметры по умолчанию отображаются в состоянии ошибки  
  
#### <a name="feature-team-goals"></a>Функция командных целей  
  
-   Предупреждать пользователей о том, что они добавлены элемент, который необходимо настроить.  
  
-   Привлечь внимание пользователя к области, которые необходимо входных данных.  
  
#### <a name="anti-pattern-solution"></a>Антишаблон решения  
 Как только пользователь запустил действие до завершения задачи, немедленно разместите значки критическая ошибка рядом с областей, которые требуется настройка.  
  
#### <a name="example-manifest-designer-declarations"></a>Пример: Объявления конструктора манифестов  
 Добавить объявление в список немедленно переводит ее в состояние ошибки, который продолжает существовать, пока пользователь установит необходимые свойства.  
  
 В этом случае имеется дополнительные значения, так как содержит значок, используемый для предупреждения "&times;" значок, поэтому нельзя использовать общий значок удаления рядом с ней. В результате пользовательского интерфейса используется кнопка "Удалить", более неуклюжим управления.  
  
 ![Размещение пользовательского интерфейса в состоянии ошибки по умолчанию — это шаблон от Visual Studio.](~/extensibility/ux-guidelines/media/manifestdesignererrordeclarationsanti-pattern.png "ManifestDesignererrordeclarationsanti-pattern")<br />Размещение пользовательского интерфейса в состоянии ошибки по умолчанию — это шаблон от Visual Studio.
  
#### <a name="alternatives"></a>Альтернативные варианты  
 Будет намного более удачным решением этой проблемы:  
  
-   Позволяет пользователю добавить объявление без предупреждения, а затем переместите немедленно для задания свойств элемента.  
  
-   Добавить значок предупреждения (золотой треугольник) при перемещении фокуса с элемента, например, чтобы добавить другое объявление в список или предпринята попытка изменить вкладок в конструкторе.  
  
-   Если пользователь пытается изменить вкладки перед заданием свойств на все объявления, pop о том, что приложение не будет построен диалогового окна (или любые последствия) пока предупреждения будут разрешены. Если пользователь закрывает диалоговое окно и изменяет вкладки все равно затем значка (критическое или предупреждения, в зависимости от необходимости) добавляется вкладку "объявления".  
  
### <a name="multiple-clicks-to-dismiss-ui"></a>Несколько щелчков, чтобы закрыть пользовательского интерфейса  
  
#### <a name="feature-team-goals"></a>Функция командных целей  
 Не разрешает пользователю закрыть пользовательский Интерфейс без первого просмотра текст пояснения.  
  
#### <a name="anti-pattern"></a>Антишаблон  
 Вставка ссылки на видео в различных областях пользовательского интерфейса VS команды решил не общий шаблон "&times;" Закрыть кнопки и подсказка объяснение, как для взаимодействия с Пользователем и реализован в раскрывающемся списке и связать «Больше не показывать».  

#### <a name="example-video-links-in-team-explorer"></a>Пример: ссылки на видео в Team Explorer
Принудительное пользователю выполнять чтение пояснительного текста перед закрытием пользовательского интерфейса является антишаблонов в среде Visual Studio. Правильно разработанное, видео ссылки должны отображаться подсказка с дополнительными сведениями о при наведении указателя мыши и выбрав пункт «&times;» следует закрыть сообщение без необходимости дальнейшей взаимодействовать.


 ![Пояснительный текст anti &#45; шаблон &#45; Неверный](~/extensibility/ux-guidelines/media/incorrectuseofmultipleclicks.png "Incorrectuseofmultipleclicks")<br />Шаблон неправильную ссылку на видео
  
#### <a name="result"></a>Результат  
 Вместо простого кнопка закрытия (одним щелчком мыши) пользователь вынужден позволяет просто закрыть пользовательский Интерфейс в каждом месте, отображаются ссылки на видео с двумя отдельными щелчками.  
  
#### <a name="alternatives"></a>Альтернативные варианты  
 Правильный подход для этой ситуации можно выполнить общий шаблон для Internet Explorer, Microsoft Office и Visual Studio: при наведении курсора мыши, пользователь может видеть описание элемента tooltip и одним щелчком мыши скрывает пользовательский Интерфейс.  
  
 ![Пояснительный текст anti &#45; шаблон &#45; Правильно](~/extensibility/ux-guidelines/media/explanatorytextanti-pattern-correct.png "Explanatorytextanti-pattern-correct")<br />Шаблон правильные ссылки на видео
  
### <a name="using-command-bars-for-settings"></a>Использование командной строки для параметров  
 **Рисунок А** представляет этот антишаблон: размещение параметр под Командная кнопка, применяется не только в команду. В этот эскиз есть команды, помимо начать отладку, как и представление в браузере, запуск без отладки и шаг с заходом —, будут использовать выбранный параметр.  

  ![На рисунке ответ антишаблон командной панели](~/extensibility/ux-guidelines/media/commandbaranti-pattern-figurea.png "Commandbaranti-pattern-FigureA")<br />На рисунке ответ антишаблон командной панели
  
 Немного лучше, но по-прежнему нежелательным, помещает параметры этого типа в панели инструментов, как показано в **рисунок В**. Разворачивающиеся кнопки занимают меньше места и, следовательно улучшение по раскрывающимся спискам, оба проекта по-прежнему используется панель инструментов для повышения уровня, то, что на самом деле не команды.  
 
 ![На рисунке B: лучше, но по-прежнему антишаблон командной панели](~/extensibility/ux-guidelines/media/commandbaranti-pattern-figureb.png "Commandbaranti-pattern-FigureB")<br />На рисунке B: лучше, но по-прежнему антишаблон командной панели
 
  В правильный подход, показанный в **рисунок С**, параметр привязан к ряд команд. Нет глобального параметра устанавливается, и мы просто переключении между четырьмя командами. Это единственный случай, в котором допустимы команд на панели инструментов. 

 ![Рисунок C: правильное использование панели команд Visual Studio](~/extensibility/ux-guidelines/media/commandbaranti-pattern-figurec.png "Commandbaranti-pattern-FigureC")<br />Рисунок C: правильное использование панели команд Visual Studio
   
### <a name="control-anti-patterns"></a>Антишаблоны управления  
 Некоторые антишаблоны являются просто неправильное использование или внешний вид элемента управления или группы элементов управления.  
  
#### <a name="underlining-used-as-a-group-label-not-a-hyperlink"></a>Подчеркивание, используется в качестве метки группы, не гиперссылки  
 Подчеркивание текста следует использовать только для гиперссылки.  
  
 **Неправильный:**    
 ![Подчеркнутый текст, не являющегося гиперссылкой это шаблон от Visual Studio.](~/extensibility/ux-guidelines/media/0102-g_grouplabelincorrect.png "0102-g_GroupLabelIncorrect")<br />Подчеркнутый текст, не являющегося гиперссылкой это шаблон от Visual Studio.
  
 **Хороший:**   
 ![Стиль правильно, не гиперссылки текст отображается без каких-либо шрифт среды разработки.](~/extensibility/ux-guidelines/media/0102-h_grouplabelcorrect.png "0102-h_GroupLabelCorrect")<br />Стиль правильно, не гиперссылки текст отображается без каких-либо шрифт среды разработки.
  
#### <a name="clicking-on-a-check-box-results-in-a-pop-up-dialog"></a>Щелкнув флажок результатов в всплывающем диалоговом окне  
 Щелкнув флажок «Включить удаленный рабочий стол для всех ролей» в мастере «Публикация приложения Windows Azure» немедленно появится всплывающее диалоговое окно Visual Studio антишаблон. Кроме того, поле флажок не заполняет с флажком после выбора, другой антишаблон взаимодействия.  
  
 ![Открывая диалоговое окно после нажатием флажков антишаблон Visual Studio.](~/extensibility/ux-guidelines/media/0102-i_checkboxpopup.png "0102-i_CheckboxPopup")<br />Открывая диалоговое окно после нажатием флажков антишаблон Visual Studio.
  
### <a name="hyperlink-anti-patterns"></a>Антишаблоны гиперссылки  
 В следующем примере содержится два антишаблоны.  
  
1.  Включение красный при наведении курсора мыши переднего плана означает, что задан правильный цвет общей службой шрифта не используется.  
  
2.  «Дополнительные сведения» не соответствующий текст для получения ссылки на раздел общих понятий. Задача пользователя — не узнать больше, это понимать последствия по своему выбору.  
  
 ![Пропуск службы цвет и с помощью «Дополнительные» для гиперссылки, антишаблоны Visual Studio.](~/extensibility/ux-guidelines/media/0102-j_hyperlinkincorrect.png "0102-j_HyperlinkIncorrect")<br />Пропуск службы цвет и с помощью «Дополнительные» для гиперссылки, антишаблоны Visual Studio.  
  
 **Лучшие решения:** вводить вопрос, пользователь будет запросом, щелкнув ссылку.  
  
-   Как работают службы Windows Azure?  
  
-   Если требуется проект мобильных служб Windows Azure?  
  
#### <a name="using-click-here-for-links"></a>С помощью «Щелкните здесь» для ссылок  
 Гиперссылки должен быть описательные. Это антишаблон, чтобы использовать «Щелкните здесь» или любой аналогичные вариации.  
  
 **Ошибочный:** «Щелкните здесь для получения инструкций о том, как создать новый проект.»
  
 **Хорошее:** «Создание нового проекта?»