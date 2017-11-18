---
title: "Создание и настройка приложения из моделей | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4dc8f572-a09e-4d19-a92d-f1df383e728b
caps.latest.revision: 7
author: alexhomer1
ms.author: ahomer
manager: douge
translation.priority.ht:
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
ms.sourcegitcommit: 8f84f22444a5df5b9f4f4af44cd8ee9136403467
ms.openlocfilehash: 864963f32fe703ada943f7e5202d7ebf6bf21e51
ms.lasthandoff: 02/22/2017

---
# <a name="generate-and-configure-your-app-from-models"></a>Создание и настройка приложения на основе моделей
Вы можете создавать или настраивать части приложения на основе модели.
  
 Модель представляет требования более непосредственно, чем код. Выводя поведение приложения непосредственно из модели, можно реагировать на изменение требований намного быстрее и надежнее, чем путем обновления кода. Хотя для настройки такого вывода требуется проделать определенную начальную работу, эти затраты окупятся, если ожидаются изменения требований или планируется создание нескольких версий продукта.  
  
## <a name="generating-the-code-of-your-application-from-a-model"></a>Создание кода приложения на основе модели  
 Самый простой способ создания кода — это использование текстовых шаблонов. При создании кода, в том же [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] решения, в котором сохранить модель. Дополнительные сведения:  
  
-   [Создание кода во время разработки с помощью текстовых шаблонов T4](../modeling/design-time-code-generation-by-using-t4-text-templates.md)  
  
-   [Создание кода из доменного языка](../modeling/generating-code-from-a-domain-specific-language.md)  
  
 Этот метод легко применять последовательно. Начните с приложения, которое работает только для определенного случая, и выберите несколько его частей, которые должны изменяться в соответствии с моделью. Переименуйте исходные файлы этих частей, чтобы они стали файлами текстовых шаблонов (TT). На этом этапе исходные файлы CS будут автоматически созданы из файлов шаблонов, поэтому приложение будет работать точно так же, как и до этого.  
  
 Затем можно взять одну часть кода и заменить ее выражением текстового шаблона, которое считывает модель и создает данную часть исходного файла. По крайней мере одно значение модели должно создавать первоначальный исходный код, чтобы приложение можно было запустить снова и оно работало так же, как и раньше. После проверки различных значений модели можно перейти к следующему этапу и вставить выражения шаблона в другую часть кода.  
  
 Такой последовательный метод означает, что создание кода обычно является подходом с низким уровнем риска. Получающиеся приложения обычно работают почти так же хорошо, как и вручную написанная версия.  
  
 Однако если начинать работу на основе существующего приложения, может оказаться, что для разделения различных поведений, управляемых моделью, требуется обширный рефакторинг, чтобы можно было изменять поведения независимо. Рекомендуется рассматривать этот аспект приложения при оценке стоимости проекта.  
  
## <a name="configuring-your-application-from-a-model"></a>Настройка приложения на основе модели  
 Если нужно изменять поведение приложения во время выполнения, невозможно использовать генерирование кода, при котором исходный код создается до компиляции приложения. Вместо этого можно разработать приложение для чтения модели и изменяло свое поведение. Дополнительные сведения:  
  
-   [Практическое руководство. Открытие модели из файла в коде программы](../modeling/how-to-open-a-model-from-file-in-program-code.md)  
  
 Этот метод также может применяться последовательно, но вначале нужно выполнить больший объем работы. Необходимо написать код, который будет считывать модель, и настроить структуру, обеспечивающую доступ к ее значениям для переменных частей. Создание универсальных переменных частей требует больших затрат, чем генерирование кода.  
  
 Универсальное приложение обычно работает хуже, чем его специализированный аналог. Если производительность имеет критическое значение, план проекта должен включать в себя оценку этого риска.  
  
## <a name="developing-a-derived-application"></a>Разработка производного приложения  
 Приведенные ниже общие рекомендации могут оказаться полезными.  
  
-   **Начинайте с конкретного, потом обобщайте.** Сначала напишите конкретную версию приложения. Эта версия должна работать при одном наборе условий. Когда будет определено, что приложение работает правильно, часть его можно сделать производной от модели. Расширяйте производные части постепенно.  
  
     Например, перед разработкой веб-приложения, представляющего определяемые моделью страницы, разработайте веб-сайт, содержащий определенный набор веб-страниц.  
  
-   **Создайте модель переменных аспектов.** Определите аспекты, которые либо будут различаться в разных развертываниях, либо будут изменяться с течением времени по мере изменения требований. Эти аспекты должны определяться моделью.  
  
     Например, если набор веб-страниц и связи между ними изменяются, но стиль и формат этих страниц всегда остаются неизменными, то модель должна описывать связи, но не обязана описывать формат этих страниц.  
  
-   **Разделите области ответственности.** Если переменные аспекты можно разделить на независимые области, используйте отдельные модели для каждой из них. С помощью ModelBus можно определить операции, влияющие как на модели, так и на их ограничения.  
  
     Например, используйте одну модель для определения перехода между веб-страницами и другую модель — для определения макета страниц.
  
-   **Моделируйте требование, а не решение.** Разработка модели таким образом, чтобы он описывал требования пользователя. Не следует разрабатывать нотацию в соответствии с переменными аспектами реализации.  
  
     Например, модель веб-навигации должна представлять веб-страницы и гиперссылки между ними. Она не должна представлять фрагменты кода HTML или классы в приложении.  
  
-   **Генерирование или Интерпретация?** Если требования для конкретного развертывания будут изменяться редко, создайте код программы на основе модели. Если возможны частые изменения требований или в одном развертывании могут сосуществовать несколько вариантов, напишите приложение, способное считывать и интерпретировать модель.  
  
     Например, если модель веб-сайта используется для разработки ряда различных отдельно устанавливаемых веб-сайтов, следует создавать код сайта на основе модели. Но если модель используется для управления ежедневно изменяющимся сайтом, то лучше написать веб-сервер, считывающий модель и соответствующим образом представляющий сайт.  
  
-   **UML или DSL?** Рассмотрите возможность создания нотации моделирования с использованием стереотипов для расширения UML. Определите модель DSL при отсутствии схемы UML, удовлетворяющей конкретной цели. Однако избегайте нарушения стандартной семантики языка UML.  
  
     Например, схема классов UML представляет собой набор прямоугольников и стрелок. Теоретически с помощью этой нотации можно определить все что угодно. Однако схему классов рекомендуется использовать только в том случае, если вы действительно описываете набор типов. Например, можно адаптировать схемы классов для описания различных типов веб-страниц.  
  
## <a name="see-also"></a>См. также  
 [Создание кода из доменного языка](../modeling/generating-code-from-a-domain-specific-language.md)   
 [Практическое руководство: открытие модели из файла в программном коде](../modeling/how-to-open-a-model-from-file-in-program-code.md)   
 [Создание кода во время разработки с помощью текстовых шаблонов T4](../modeling/design-time-code-generation-by-using-t4-text-templates.md)