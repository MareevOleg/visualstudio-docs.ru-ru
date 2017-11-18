---
title: "Схемы зависимостей: Ссылаться | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.teamarch.layerdiagram.layerexplorer.artifactlink
- vs.teamarch.layerdiagram.layerexplorer.artifactlink.properties
- vs.teamarch.layerdiagram.diagram
- vs.teamarch.UMLModelExplorer.layerdiagram
- vs.teamarch.layerdiagram.layerexplorer
- vs.teamarch.layerdiagram.shapes.properties
- vs.teamarch.layerdiagram.toolbox
helpviewer_keywords:
- architecture, dependency diagrams
- dependency diagrams
- diagrams - modeling, layer
- constraints, architectural
ms.assetid: f26c986c-1e79-420e-b29a-a283e6d8a71d
caps.latest.revision: "33"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.openlocfilehash: ce4a203fd0843fd6b15bfbf85019e85032defbd6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2017
---
# <a name="dependency-diagrams-reference"></a>Схемы зависимостей: Справочник
В Visual Studio можно использовать *Диаграмма зависимостей* для визуализации высокого уровня и логическую архитектуру системы. Диаграмма зависимостей организует физические артефакты системы в логические, абстрактные группы, называемые *слои*. Слои описывают основные компоненты системы или задачи, выполняемые этими артефактами. Каждый слой может также содержать вложенные слои, описывающие более подробные задачи.  
  
 Чтобы узнать, какие версии Visual Studio поддерживают эту функцию, см. раздел [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
 Между слоями можно установить предполагаемые или существующие зависимости. Эти зависимости, представленные в виде стрелок, показывают, какие слои могут использовать или в настоящее время используют функциональные возможности, представленные другими слоями. Организуя системы в слои, описывающие различные роли и функции, диаграмма зависимостей может помочь сделать проще для понимания, повторное использование и обслуживание кода.  
  
 С помощью схемы зависимостей помогают выполнять следующие задачи:  
  
-   представлять существующую или предполагаемую логическую архитектуру системы;  
  
-   выявлять конфликты между существующим кодом и предполагаемой архитектурой;  
  
-   визуализировать влияние изменений на предполагаемую архитектуру при рефакторинге, обновлении или развитии системы;  
  
-   дополнительно контролировать предполагаемую архитектуру в процессе разработки и обслуживания кода за счет добавления проверки операций возврата и построения.  
  
 В этом разделе описаны элементы, которые можно использовать на схеме зависимостей. Более подробные сведения о способах создания и схем зависимостей см. в разделе [схемы зависимостей: рекомендации по](../modeling/layer-diagrams-guidelines.md). Дополнительные сведения о шаблонах слоев посетите [сайт шаблоны и приемы](http://go.microsoft.com/fwlink/?LinkId=145794).  
  
## <a name="reading-dependency-diagrams"></a>Чтение схем зависимостей  
 ![Элементы на схемах зависимостей](../modeling/media/uml_layerrefreading.png "UML_LayerRefReading")  
  
 Следующая таблица описывает элементы, которые можно использовать на схеме зависимостей.  
  
|**Фигуры**|**Элемент**|**Описание**|  
|---------------|-----------------|---------------------|  
|1|**Слой**|Логическая группа физических артефактов в системе. Артефактами могут быть пространства имен, проекты, классы, методы и т. п.<br /><br /> Для просмотра связанных со слоем артефактов, откройте контекстное меню слоя и выберите **Просмотр ссылок** Открытие **обозреватель слоев**.<br /><br /> Дополнительные сведения см. в разделе [обозреватель слоев](#Explorer).<br /><br /> -   **Запрещенные зависимости пространства имен** -указывает, что артефакт, связанный с этим слоем, не может зависеть от указанного пространства имен.<br />-   **Запрещено пространства имен** -указывает, артефакты, связанные с этим слоем, не могут принадлежать указанному пространству имен.<br />-   **Необходимые пространства имен** -указывает, что артефакт, связанный с этим слоем должны принадлежать к одному из указанных пространств имен.|  
|2|**Зависимости**|Указывает, что один слой может использовать функции другого слоя, но не наоборот.<br /><br /> -   **Направление** -указывает направление зависимости.|  
|3|**Двунаправленная зависимость**|Указывает, что один слой может использовать функции другого слоя и наоборот.<br /><br /> -   **Направление** -указывает направление зависимости.|  
|4|**Комментарий**|Используется для добавления общих примечаний к схеме или ее элементам.|  
|5|**Ссылка на комментарий**|Используется для связи комментариев с элементами на схеме.|  
  
##  <a name="Explorer"></a>Обозреватель слоев  
 Каждый слой можно связать с артефактами в решении, например с проектами, классами, пространствами имен, файлами проекта и другими частями программного обеспечения. Число на слое обозначает количество связанных с этим слоем артефактов. Число артефактов в слое следует толковать с учетом следующих факторов.  
  
-   Если слой связан с артефактом, содержащим другие артефакты, но слой не связан с другими артефактами напрямую, то число включает только связанный артефакт. Однако для анализа в ходе проверки слоя включаются другие артефакты.  
  
     Например, если слой связан с одним пространством имен, то число связанных артефактов равно 1, даже если пространство имен содержит классы. Если слой также связан с каждым классом в пространстве имен, то число будет включать эти связанные классы.  
  
-   Если слой содержит другие слои, связанные с артефактами, то слой-контейнер также связан с этими артефактами, даже если число в слое-контейнере не включает эти артефакты.  
  
 Дополнительные сведения о связывании слоев и артефактов см. в разделах:  
  
-   [Схемы зависимостей: рекомендации](../modeling/layer-diagrams-guidelines.md)  
  
-   [Создание схем зависимостей на основе кода](../modeling/create-layer-diagrams-from-your-code.md)  
  
#### <a name="to-examine-the-linked-artifacts"></a>Просмотр связанных артефактов  
  
-   На диаграмме зависимостей, откройте контекстное меню для одного или нескольких слоях и выберите **Просмотр ссылок**.  
  
     **Обозреватель слоя** открывает и показаны артефакты, связанные с выбранными уровнями. **Обозреватель слоя** содержит столбец, показывающий свойства ссылок на артефакты.  
  
    > [!NOTE]
    >  Если все эти свойства не отображается, разверните **обозреватель слоев** окна.  
  
    |**Столбец в обозревателе слоев**|**Описание**|  
    |----------------------------------|---------------------|  
    |**Категории**|Вид артефакта, например класс, пространство имен, исходный файл и т. д.|  
    |**Слой**|Связанный с артефактом слой|  
    |**Поддержка проверки**|Если **True**, то процесс проверки слоев можно проверить, что проект соответствует зависимостям к или из этого элемента.<br /><br /> Если **False**, то связь не участвует в процесс проверки слоев.<br /><br /> Дополнительные сведения см. в разделе [схемы зависимостей: рекомендации по](../modeling/layer-diagrams-guidelines.md).|  
    |**Идентификатор**|Ссылка на связанный артефакт|  
  
## <a name="see-also"></a>См. также  
 [Создание моделей для приложения](../modeling/create-models-for-your-app.md)