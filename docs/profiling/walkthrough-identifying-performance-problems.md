---
title: "Пошаговое руководство. Выявление проблем с производительностью | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- profiling tools, walkthroughs
- performance tools, walkthroughs
- performance, analyzing
- profiling applications, walkthroughs
ms.assetid: 36f6f123-0c14-4763-99c3-bd60ecb95b87
caps.latest.revision: 53
author: mikejo5000
ms.author: mikejo
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: ca7c86466fa23fb21a932f26dc24e37c71cf29b4
ms.openlocfilehash: a20a64818982484a56ba7dc82af890c729da40e4
ms.lasthandoff: 04/05/2017

---
# <a name="walkthrough-identifying-performance-problems"></a>Пошаговое руководство. Выявление проблем с производительностью
В этом пошаговом руководстве показано, как выполнить профилирование приложения для выявления проблем производительности.  
  
 В этом руководстве приводится пошаговое описание процесса профилирования управляемого приложения. Для поиска и определения проблем производительности приложения используются методы выборки и инструментирования.  
  
 В этом пошаговом руководстве выполняются следующие действия:  
  
-   профилирование приложения с помощью метода выборки;  
  
-   анализ результатов профилирования с выборкой для выявления и исправления проблем производительности;  
  
-   профилирование приложения с помощью метода инструментирования;  
  
-   анализ результатов профилирования с инструментированием для выявления и исправления проблем производительности.  
  
## <a name="prerequisites"></a>Предварительные требования  
  
-   Средний уровень знания языка C#.  
  
-   Копия [примера PeopleTrax](../profiling/peopletrax-sample-profiling-tools.md).  
  
 Для работы со сведениями, полученными при профилировании, рекомендуется включить отладочные символы.  
  
## <a name="profiling-by-using-the-sampling-method"></a>Профилирование с помощью метода выборки  
 Выборка — это метод профилирования, при котором анализируемый процесс периодически опрашивается с целью определения активной функции. Полученные данные показывают, как часто анализируемая функция находилась на вершине стека вызовов при выборочном опросе процесса.  
  
#### <a name="to-profile-an-application-by-using-the-sampling-method"></a>Профилирование приложения с помощью метода выборки  
  
1.  Откройте среду [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] с правами администратора. Выполнение с правами администратора необходимо для профилирования.  
  
2.  Откройте решение PeopleTrax.  
  
     Решение PeopleTrax отобразится в обозревателе решений.  
  
3.  Установите для параметра конфигурации проекта значение **Выпуск**.  
  
     Для обнаружения проблем с производительностью приложения следует использовать сборку выпуска. Сборка выпуска рекомендуется для профилирования по той причине, что отладочная сборка содержит дополнительные скомпилированные сведения, которые могут отрицательно сказаться на производительности и не позволят адекватно продемонстрировать проблемы производительности.  
  
4.  В меню **Анализ** выберите пункт **Профилировщик производительности**, затем **Мастер производительности** и нажмите **Запустить**.  
  
     Откроется мастер производительности.  
  
5.  Убедитесь в том, что выбран параметр **Выборка циклов ЦП (рекомендуется)**, и нажмите кнопку **Далее**.  
  
6.  В поле **Какое приложение выбрано для профилирования** выберите PeopleTrax, а затем нажмите кнопку **Далее**.  
  
     [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] выполнит сборку проекта и запустит профилирование приложения. Откроется окно приложения **PeopleTrax**.  
  
7.  Щелкните **Get People** (Получить пользователей).  
  
8.  Щелкните **Export Data** (Экспорт данных).  
  
     В Блокноте откроется новый файл, содержащий данные, экспортированные из приложения **PeopleTrax**.  
  
9. Закройте Блокнот и приложение **PeopleTrax**.  
  
     Профилировщик создает файл данных профилирования (\*.vsp), указывает имя этого файла в разделе "Отчеты" окна обозревателя производительности и автоматически загружает представление **Сводка** файла данных в главном окне [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)].  
  
#### <a name="to-analyze-sampled-profiling-results"></a>Анализ результатов профилирования с выборкой  
  
1.  В представлении "Сводка" отображается временная шкала загрузки ЦП в процессе выполнения профилирования, список **Горячий путь**, представляющий наиболее активную ветвь в дереве вызовов приложения, и список **Функции, выполняющие максимальную индивидуальную работу**, в котором приведены функции, во время выполнения кода в теле которых производилась наиболее интенсивная выборка.  
  
     Проанализируйте список **Горячий путь** и обратите внимание на то, что метод PeopleNS.People.GetNames является функцией PeopleTrax, ближайшей к концу списка. Его положение делает его отличным кандидатом для анализа. Щелкните имя этой функции для отображения сведений о GetNames в представлении **Сведения о функции**.  
  
2.  В представлении **Сведения о функции** имеются два окна. В окне "Распределение стоимости" содержится графическое представление работы, выполняемой данной функцией, работы, выполняемой функциями, которые она вызывает, а также влияние функций, вызвавших данную функцию, на число экземпляров, для которых выполняется выборка. Щелкнув имя функции, можно изменить функцию, для которой в представлении отображаются данные. Например, можно щелкнуть PeopleNS.People.GetPeople, чтобы выбранной функцией стала функция GetPeople.  
  
     В окне **Представление кода функции** отображается исходный код выбранной функции, если он доступен, и выделяются ее наиболее ресурсоемкие строки. Если выбран метод GetNames, то, как можно видеть, эта функция считывает строку из ресурсов приложения, а затем использует <xref:System.IO.StringReader> для добавления каждой строки кода в строке в коллекцию <xref:System.Collections.ArrayList>. Очевидный способ оптимизации этой функции отсутствует.  
  
3.  Так как PeopleNS.People.GetPeople — это единственная вызывающая функция GetNames, щелкните GetPeople в окне "Распределение стоимости", чтобы проанализировать код. Этот метод возвращает коллекцию <xref:System.Collections.ArrayList> объектов PersonInformationNS.PersonInformation из списка имен лиц и названий компаний, созданных методом GetNames. Однако GetNames вызывается дважды при каждом создании объекта PersonInformation. Как можно видеть, метод можно легко оптимизировать, создав списки только один раз при запуске метода и проиндексировав их во время цикла создания PersonInformation.  
  
4.  Вместе с примером кода приложения предоставляется альтернативная версия GetPeople. Оптимизированную функцию можно вызвать, добавив символ условной компиляции в свойства сборки. В окне "Обозреватель решений" щелкните правой кнопкой мыши проект People и выберите пункт **Свойства**. Выберите пункт **Сборка** в меню страницы свойств и введите **OPTIMIZED_GETPEOPLE** в текстовом поле символа условной компиляции. Оптимизированная версия GetPeople заменит исходный метод при следующей сборке.  
  
5.  Перезапустите сеанс анализа производительности. На панели инструментов обозревателя производительности щелкните **Запустить с профилированием**. Щелкните **Get People**, а затем выберите **Export Data**. Закройте появившееся окно Блокнота, а затем закройте приложение PeopleTrax.  
  
     Создается файл данных профилирования, а в главном окне [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] для новых данных отображается представление **Сводка**.  
  
6.  Для сравнения двух сеансов профилирования выберите два файла данных в обозревателе производительности, щелкните их правой кнопкой мыши, а затем выберите команду **Сравнить отчеты о производительности**. В главном окне [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] отобразится окно "Отчет о сравнении". В столбце **Разностная версия** показана разница между более ранним **базовым** значением производительности функций и более поздним **сравнительным** значением. В раскрывающемся списке **Столбец** можно выбрать значения для сравнения. Выберите **Включающие выборки %**.  
  
     Обратите внимание, что методы GetPeople и GetNames демонстрируют достаточно высокий прирост производительности.  
  
## <a name="profiling-by-using-the-instrumentation-method"></a>Профилирование с помощью метода инструментирования  
 Инструментирование — это метод профилирования, в котором профилировщик вставляет функции-зонды в специально созданные версии профилируемых двоичных файлов. Функции-зонды собирают сведения о времени входа в функции и выхода из них в инструментированных модулях и во всех местах вызова в этих функциях. Процесс инструментирования полезен для анализа проблем, связанных с операциями ввода-вывода, такими как запись на диск и обмен данными по сети. Инструментирование предоставляет более подробные сведения, чем выборка, однако сильнее влияет на выполнение процесса и приводит к созданию большего объема служебных данных. Кроме того, инструментированные двоичные файлы больше по размеру, чем двоичные файлы для отладки или выпуска, и не предназначены для развертывания.  
  
 В этом разделе пошагового руководства метод инструментирования будет использован для выявления дополнительного кода, пригодного для оптимизации, в приложении PeopleTrax, которое профилировалось ранее. С помощью фильтра временной шкалы представления "Сводка" в качестве основного объекта анализа будет выбран сценарий экспорта данных в профилируемом приложении, в котором список лиц записывается в файл в Блокноте.  
  
#### <a name="to-profile-an-existing-application-by-using-the-instrumentation-method"></a>Профилирование существующего приложения с помощью метода инструментирования  
  
1.  При необходимости откройте приложение PeopleTrax в Visual Studio.  
  
     Убедитесь в том, что приложение открыто с правами администратора и что для конфигурации сборки решения задано значение **Выпуск**.  
  
2.  В обозревателе производительности щелкните **Инструментирование**.  
  
3.  На панели инструментов обозревателя производительности щелкните **Запустить с профилированием**.  
  
     Профилировщик выполнит сборку проекта и запустит профилирование приложения. Откроется окно приложения PeopleTrax.  
  
4.  Щелкните **Get People** (Получить пользователей).  
  
     Таблица PeopleTrax заполнится данными.  
  
5.  Подождите примерно 10 секунд и нажмите кнопку **Export Data**.  
  
     В **Блокноте** откроется новый файл, содержащий список людей из приложения PeopleTrax. Ожидание упрощает определение процедуры экспорта данных для фильтрации.  
  
6.  Закройте **Блокнот** и приложение **PeopleTrax**.  
  
     [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] создает отчет сеанса производительности (*.vsp).  
  
#### <a name="to-analyze-instrumented-profiling-results"></a>Анализ результатов профилирования с инструментированием  
  
1.  На временной шкале представления **Сводка** отчета отображается загрузка ЦП программой на протяжении сеанса профилирования. Операция экспорта данных должна выглядеть как большой пик или полка в правой части графа. Чтобы вывести и проанализировать только данные, собранные в ходе операции экспорта, можно отфильтровать сеанс анализа производительности. Щелкните слева от точки на графе, в которой началась операция экспорта данных. Щелкните еще раз справа от операции. Затем в списке ссылок справа от временной шкалы щелкните ссылку **Фильтр по выделенному**.  
  
     В дереве **Горячий путь** будет указано, что метод <xref:System.String.Concat%2A>, вызываемый методом PeopleTrax.Form1.ExportData, занимает большой процент времени. Так как метод **System.String.Concat** также находится вверху списка **Функции с максимальной индивидуальной работой**, сокращение времени, затрачиваемого в функции, — один из потенциальных путей оптимизации.  
  
2.  Дважды щелкните метод **System.String.Concat** в любой из таблиц сводки для просмотра дополнительных сведений в представлении "Сведения о функции".  
  
3.  Как можно видеть, PeopleTrax.Form1.ExportData — это единственный метод, который вызывает метод Concat. Щелкните **PeopleTrax.Form1.ExportData** в списке **Вызывающие функции**, чтобы выбрать этот метод в качестве целевого объекта представления "Сведения о функции".  
  
4.  Проанализируйте метод в окне "Представление кода функции". Обратите внимание на отсутствие непосредственных вызовов метода **System.String.Concat**. Вместо этого в коде несколько раз используется операнд +=, который компилятор заменяет вызовом функции **System.String.Concat**. Любые изменения строки в платформе .NET Framework приводят к выделению памяти для новой строки. В .NET Framework имеется класс <xref:System.Text.StringBuilder>, оптимизированный для объединения строк.  
  
5.  Чтобы заменить эту проблемную область оптимизированным кодом, добавьте символ условной компиляции OPTIMIZED_EXPORTDATA в проект PeopleTrax.  
  
6.  В обозревателе решений щелкните правой кнопкой мыши проект PeopleTrax и выберите пункт **Свойства**.  
  
     Откроется форма свойств проекта PeopleTrax.  
  
7.  Перейдите на вкладку **Сборка**.  
  
8.  В текстовом поле **Символы условной компиляции** введите **OPTIMIZED_EXPORTDATA**.  
  
9. Закройте форму свойств проекта и при появлении соответствующего запроса выберите **Сохранить все**.  
  
 Если запустить приложение еще раз, можно заметить, что производительность заметно повысилась. Рекомендуется запустить сеанс профилирования еще раз даже в том случае, если наблюдается очевидное повышение производительности. После устранения проблемы важно еще раз просмотреть данные, так как первая проблема могла скрывать некоторые другие проблемы.  
  
## <a name="see-also"></a>См. также  
 [Разделы общих сведений](../profiling/overviews-performance-tools.md)   
 [Начало работы](../profiling/getting-started-with-performance-tools.md)   
 [/Z7, /Zi, /ZI (формат отладочной информации)](/cpp/build/reference/z7-zi-zi-debug-information-format)