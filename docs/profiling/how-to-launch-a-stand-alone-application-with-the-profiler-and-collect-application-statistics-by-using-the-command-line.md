---
title: "Практическое руководство. Запуск автономного приложения с профилировщиком и сбор статистики приложения с помощью командной строки | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 52dcee2b-f178-4a76-bddc-e36c50bfcb78
caps.latest.revision: 37
caps.handback.revision: 37
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Практическое руководство. Запуск автономного приложения с профилировщиком и сбор статистики приложения с помощью командной строки
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

В этом разделе описан порядок использования программ командной строки средств профилирования [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] для запуска автономного \(клиентского\) приложения и сбора статистики производительности с помощью метода выборки.  
  
> [!NOTE]
>  Функции усиленной безопасности в Windows 8 и Windows Server 2012 требуют значительных изменений в способе сбора данных профилировщиком Visual Studio на этих платформах.  Для Приложений Магазина Windows также требуются новые методы сбора.  См. раздел [Профилирование приложений для Windows 8 и Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
>   
>  Добавление данных об уровневом взаимодействии в сеанс профилирования требует определенных процедур со средствами профилирования командной строки.  См. раздел [Сбор данных взаимодействия уровней](../profiling/adding-tier-interaction-data-from-the-command-line.md).  
  
 Для использования программ командной строки профилировщика необходимо добавить путь в переменную среды PATH окна командной строки или указать этот путь при вызове команды.  Можно запустить средства профилирования на компьютере с установленной Visual Studio из командного окна Visual Studio.  
  
1.  При запуске средства профилирования на компьютере с установленной Visual Studio, командное окно Visual Studio устанавливает правильные пути.  В меню **Сервис** выберите команду **Командная строка VS**.  
  
> [!NOTE]
>  Программы командной строки средств профилирования расположены в подкаталоге \\Team Tools\\Performance Tools каталога установки Visual Studio.  На 64\-разрядных компьютерах доступны 64\-разрядные и 32\-разрядные версии средств.  Для использования программ командной строки профилировщика необходимо добавить путь в переменную среды PATH окна командной строки или указать этот путь при вызове команды.  Для получения дополнительной информации см. [Указание пути к средствам командной строки](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
## Запуск приложения с профилировщиком  
 Чтобы запустить целевое приложение с помощью профилировщика, воспользуйтесь параметрами **\/start** и **\/launch** для инициализации профилировщика и запуска приложения.  Команды **\/start** и **\/launch** с соответствующими параметрами можно указать в одной командной строке.  
  
 Для приостановки сбора данных при запуске целевого приложения можно также добавить параметр **\/globaloff**.  Далее для начала сбора данных используется параметр **\/globalon**.  
  
#### Запуск приложения с использованием профилировщика  
  
1.  Откройте окно командной строки.  
  
2.  Запустите профилировщик.  Type:  
  
     **VSPerfCmd \/start:sample \/output:** `OutputFile` \[`Options`\]  
  
    -   Параметр [\/start](../profiling/start.md)**:sample** обеспечивает инициализацию профилировщика.  
  
    -   Параметр [\/output](../profiling/output.md)**:**`OutputFile` является обязательным при использовании параметра **\/start**.  Параметр `OutputFile` задает имя и расположение файла с данными профилирования \(VSP\-файла\).  
  
     С параметром **\/start:sample** можно использовать любые из следующих параметров.  
  
    |Команда|Описание|  
    |-------------|--------------|  
    |[\/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Задает счетчик производительности Windows, данные которого следует собирать в процессе профилирования.|  
    |[\/automark](../profiling/automark.md) **:** `Interval`|Используйте только с **\/wincounter**.  Задает интервал времени \(в миллисекундах\) между событиями сбора данных счетчика производительности Windows.  Значение по умолчанию — 500 мс.|  
    |[\/events](../profiling/events-vsperfcmd.md) **:** `Config`|Задает событие трассировки событий Windows, данные которого следует собирать в процессе профилирования.  События трассировки событий Windows собираются в отдельный ETL\-файл.|  
  
3.  Запустите целевое приложение.  Введите: **VSPerfCmd \/launch:**`appName` \[`Options`\] \[`Sample Event`\]  
  
     С параметром **\/launch** можно использовать один или несколько следующих параметров.  
  
    |Команда|Описание|  
    |-------------|--------------|  
    |[\/args](../profiling/args.md) **:** `Arguments`|Задает строку, содержащую аргументы командной строки, которые передаются целевому приложению.|  
    |[\/console](../profiling/console.md)|Запускает целевое приложение командной строки в отдельном окне.|  
  
     По умолчанию данные о производительности собираются каждые 10 000 000 циклов тактовой частоты процессора без остановок.  Для процессора с частотой 1 ГГц это приблизительно один раз через каждые 10 секунд.  Чтобы изменить длительность цикла тактовой частоты или задать другое событие выборки, можно воспользоваться одним из следующих параметров.  
  
    |Пример события|Описание|  
    |--------------------|--------------|  
    |[\/timer](../profiling/timer.md) **:** `Interval`|Изменяет интервал выборки на число циклов тактовой частоты без остановок, задаваемое параметром `Interval`.|  
    |[\/pf](../profiling/pf.md)\[**:**`Interval`\]|Изменяет событие выборки на ошибки страниц.  Если указано значение `Interval`, задает количество ошибок страниц между выборками.  По умолчанию используется значение 10.|  
    |[\/sys](../profiling/sys-vsperfcmd.md)\[**:**`Interval`\]|Изменяет событие выборки на системные вызовы ядра операционной системы из процесса \(syscall\).  Если указано значение `Interval`, задает количество вызовов между выборками.  По умолчанию используется значение 10.|  
    |[\/counter](../profiling/counter.md) **:** `Config`|Изменяет событие выборки, интервал для счетчика производительности процессора и значение интервала, задаваемые параметром `Config`.|  
  
## Управление сбором данных  
 Когда выполняется целевое приложение, можно управлять сбором данных путем запуска и остановки записи данных в файл данных профилировщика с помощью параметров **VSPerfCmd.exe**.  Управление сбором данных позволяет собирать данные на различных этапах выполнения программы, например, при запуске или завершении работы приложения.  
  
#### Запуск и остановка сбора данных  
  
-   Следующие пары параметров используются для запуска и остановки сбора данных.  Задайте каждый параметр в отдельной строке командной строки.  Запуск и приостановка сбора данных могут выполняться неоднократно.  
  
    |Команда|Описание|  
    |-------------|--------------|  
    |[\/globalon \/globaloff](../profiling/globalon-and-globaloff.md)|Запускает \(**\/globalon**\) или останавливает \(**\/globaloff**\) сбор данных для всех процессов.|  
    |[\/processon](../profiling/processon-and-processoff.md) **:** `PID`  [\/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Запускает \(**\/processon**\) или останавливает \(**\/processoff**\) сбор данных для процесса с указанным идентификатором процесса \(`PID`\).|  
    |[\/attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [\/detach](../profiling/detach.md)\[**:**{`PID`&#124;`ProcName`}\]|**\/attach** запускает сбор данных для процесса, определяемого идентификатором `PID` или именем процесса \(ProcName\).  **\/detach** останавливает сбор данных для указанного процесса или, если он не задан, для всех процессов.|  
  
## Завершение сеанса профилирования  
 Чтобы завершить сеанс профилирования, нужно отсоединить профилировщик от всех профилируемых процессов и явным образом завершить его работу.  Чтобы отсоединить профилировщик от приложения, для которого выполнялось профилирование методом выборки, закройте приложение или выполните команду **VSPerfCmd \/detach**.  Затем, для завершения работы профилировщика и закрытия файла данных профилирования используется параметр **VSPerfCmd \/shutdown**.  Команда **VSPerfClrEnv \/off** удаляет значения переменных среды, используемые для профилирования.  
  
#### Завершение сеанса профилирования  
  
1.  Чтобы отсоединить профилировщик от целевого приложения, выполните одно из следующих действий.  
  
    -   Закройте целевое приложение.  
  
         – или –  
  
    -   Введите **VSPerfCmd \/detach**.  
  
2.  Завершите работу профилировщика.  Type:  
  
     **VSPerfCmd**  [\/shutdown](../profiling/shutdown.md)  
  
## См. также  
 [Профилирование автономных приложений](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Представления данных метода выборки](../profiling/profiler-sampling-method-data-views.md)