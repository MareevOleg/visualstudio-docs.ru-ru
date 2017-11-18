---
title: "Команды Visual Studio | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Visual Studio, команды"
  - "команды, Visual Studio"
  - "синтаксис команд"
ms.assetid: 76ffa394-ee89-4629-aba9-1a62b72e6cc1
caps.latest.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 16
---
# Команды Visual Studio
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Команды Visual Studio позволяют вызвать команду из окна **Команды**, окна **Интерпретация** или поля **Поиск\/команда**. В каждом случае знак "больше" \(`>`\) используется для указания того, что дальше будет следовать команда, а не операция поиска или отладки.  
  
 Полный список команд и их синтаксис приведены в диалоговом окне **"Параметры" \(страница "Клавиатура", папка "Окружение"\)**.  
  
 Escape\-символом для команд Visual Studio является крышка \(^\) — следующий за ней символ интерпретируется буквально, а не как управляющий символ. Благодаря этому в значение параметра можно внедрить прямые кавычки \("\), пробелы, начальные символы косой черты, крышки или другие знаки, за исключением имен параметров. Например:  
  
```  
>Edit.Find ^^t /regex  
```  
  
 Крышка действует одинаково как внутри кавычек, так и за их пределами. Если крышка является последним символом в строке, она игнорируется.  
  
 В локализованных версиях интегрированной среды разработки имена команд можно вводить на собственном языке среды или на английском языке. Например, вы можете ввести `File.NewFile` или `Fichier.NouveauFichier`  во французской интегрированной среде разработки для выполнения одной и той же команды.  
  
 Многие команды имеют псевдонимы. Список псевдонимов команд см. в разделе [Псевдонимы команд Visual Studio](../../ide/reference/visual-studio-command-aliases.md).  
  
 Приведенные ниже команды принимают аргументы и\/или параметры.  
  
|Имя команды|Описание|  
|-----------------|--------------|  
|[Добавление существующего элемента](../../ide/reference/add-existing-item-command.md)|Добавляет существующий файл в текущее решение и открывает его.|  
|[Добавить существующий проект](../../ide/reference/add-existing-project-command.md)|Добавляет существующий проект в текущее решение.|  
|[Добавить новый элемент](../../ide/reference/add-new-item-command.md)|Добавляет новый элемент решения, такой как HTM, CSS, TXT или набор фреймов, в текущее решение и открывает его.|  
|[Alias](../../ide/reference/alias-command.md)|Создает новый псевдоним для полной команды, полной команды с аргументами или даже для другого псевдонима.|  
|[Вычислить оператор](../../ide/reference/evaluate-statement-command.md)|Вычисляет и отображает заданный оператор.|  
|[Find](../../ide/reference/find-command.md)|Выполняет поиск файлов с использованием подмножества параметров, доступных на элементе управления **Поиск и замена**.|  
|[Поиск в файлах](../../ide/reference/find-in-files-command.md)|Выполняет поиск файлов с использованием подмножества параметров, доступных на элементе [Поиск в файлах](../../ide/find-in-files.md).|  
|[Перейти](../../ide/reference/go-to-command.md)|Перемещение курсор на указанную строку.|  
|[Вывести стек вызовов](../../ide/reference/list-call-stack-command.md)|Отображает текущий стек вызовов.|  
|[Вывести дизассемблированный код](../../ide/reference/list-disassembly-command.md)|Начинает процесс отладки и позволяет указать способ обработки ошибок.|  
|[Вывести память](../../ide/reference/list-memory-command.md)|Отображает содержимое указанного диапазона памяти.|  
|[Вывести модули](../../ide/reference/list-modules-command.md)|Отображает список модулей для текущего процесса.|  
|[Вывести регистры](../../ide/reference/list-registers-command.md)|Отображает список регистров.|  
|[Вывести исходный код](../../ide/reference/list-source-command.md)|Отображает заданные строки исходного кода.|  
|[Вывести потоки](../../ide/reference/list-threads-command.md)|Отображает список потоков в текущей программе.|  
|[Запись вывода окна команд](../../ide/reference/log-command-window-output-command.md)|Копирует все входные и выходные данные из окна команд в файл.|  
|[Создать файл](../../ide/reference/new-file-command.md)|Создает новый файл и добавляет его в выбранный проект.|  
|[Открыть файл](../../ide/reference/open-file-command.md)|Открывает существующий файл и позволяет указать редактор.|  
|[Открытие проекта](../../ide/reference/open-project-command.md)|Открывает существующий проект и позволяет добавить проект в текущее решение.|  
|[Открытие решения](../../ide/reference/open-solution-command.md)|Открывает существующее решение.|  
|[Печать](../../ide/reference/print-command.md)|Вычисляет выражение и отображает результаты или указанный текст.|  
|[Команда Quick Watch](../../ide/reference/quick-watch-command.md)|Отображает выбранный или указанный текст в поле **Выражение** диалогового окна **Контрольное значение**.|  
|[Заменить](../../ide/reference/replace-command.md)|Заменяет текст в файлах с использованием подмножества параметров, доступных на элементе управления **Поиск и замена**.|  
|[Заменить в файлах](../../ide/reference/replace-in-files-command.md)|Заменяет текст в файлах с использованием подмножества параметров, доступных в [Заменить в файлах](../../ide/replace-in-files.md).|  
|[Задать текущий кадр стека](../../ide/reference/set-current-stack-frame-command.md)|Позволяет просматривать определенный кадр стека.|  
|[Задать текущий поток](../../ide/reference/set-current-thread-command.md)|Позволяет просматривать определенный поток.|  
|[Задать основание системы счисления](../../ide/reference/set-radix-command.md)|Определяет количество байтов для просмотра.|  
|[Оболочка](../../ide/reference/shell-command.md)|Запускает программы изнутри [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], как если бы команда выполнялась из командной строки.|  
|[Команда ShowWebBrowser](../../ide/reference/showwebbrowser-command.md)|Отображает URL\-адрес, указанный в окне браузера внутри или вне интегрированной среды разработки \(IDE\).|  
|[Запуск](../../ide/reference/start-command.md)|Начинает процесс отладки и позволяет указать способ обработки ошибок.|  
|[Путь](../../ide/reference/symbol-path-command.md)|Задает список каталогов для поиска символов отладчиком.|  
|[Точка останова](../../ide/reference/toggle-breakpoint-command.md)|Включает или отключает точку останова в зависимости от ее текущего состояния и текущей позиции в файле.|  
|[Команда Watch](../../ide/reference/watch-command.md)|Создает и открывает указанный экземпляр окна **Контрольное значение**.|  
  
## См. также  
 [Окно "Команда"](../../ide/reference/command-window.md)   
 [Поле «Поиск\/Команда»](../../ide/find-command-box.md)   
 [Псевдонимы команд Visual Studio](../../ide/reference/visual-studio-command-aliases.md)