---
title: "Свойства компоновщика Clang (Android C++) | Документы Майкрософт"
ms.custom: 
ms.date: 10/23/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 66e88848-116c-4eb0-bc57-183394d35b57
author: corob
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.VCLinkerTool.OutputFile
- VC.Project.VCLinkerTool.ShowProgress
- VC.Project.VCLinkerTool.Version
- VC.Project.VCLinkerTool.VerboseOutput
- VC.Project.VCLinkerTool.IncrementalLink
- VC.Project.VCLinkerTool.SharedLibrarySearchPath
- VC.Project.VCLinkerTool.AdditionalLibraryDirectories
- VC.Project.VCLinkerTool.UnresolvedReferences
- VC.Project.VCLinkerTool.OptimizeForMemory
- VC.Project.VCLinkerTool.IgnoreDefaultLibraryNames
- VC.Project.VCLinkerTool.ForceSymbolReferences
- VC.Project.VCLinkerTool.ForceFileOutput
- VC.Project.VCLinkerTool.OmitDebuggerSymbolInformation
- VC.Project.VCLinkerTool.GenerateMapFile
- VC.Project.VCLinkerTool.Relocation
- VC.Project.VCLinkerTool.FunctionBinding
- VC.Project.VCLinkerTool.NoExecStackRequired
- VC.Project.WholeArchive
- VC.Project.AdditionalOptionsPage
- VC.Project.VCLinkerTool.AdditionalDependencies
- VC.Project.VCLinkerTool.LibraryDependencies
ms.workload: xplat-cplusplus
ms.openlocfilehash: f74ad5934d48c941195da30d9228c35483479f69
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="clang-linker-properties-android-c"></a>Свойства компоновщика Clang (Android C++)

Свойство. | Описание: | Варианты
--- | ---| ---
Выходной файл | Параметр переопределяет стандартное имя и расположение программы, которую создает компоновщик. (-o)
Отображать ход выполнения | Печатает сообщения хода выполнения компоновщика.
Версия | Параметр -version сообщает компоновщику о том, что нужно поместить номер версии в заголовок исполняемого файла.
Включить подробные выходные данные | Параметр -verbose сообщает компоновщику о том, что нужно вывести подробные сообщения для отладки.
Включить инкрементную компоновку | Параметр сообщает компоновщику о том, что нужно включить инкрементную компоновку.
Путь поиска общих библиотек | Позволяет пользователю указать путь поиска общих библиотек.
Дополнительные каталоги библиотек | Разрешает пользователю переопределять путь окружения библиотеки. (-L folder).
Сообщить о неразрешенных ссылках на символы | Если этот параметр включен, он будет сообщать о неразрешенных ссылках на символы.
Оптимизировать использование памяти | Оптимизация использования памяти путем повторного чтения таблиц символов по мере необходимости.
Игнорировать конкретные стандартные библиотеки | Указывает одно или несколько имен пропускаемых библиотек по умолчанию.
Принудительно включать ссылки на символы | Принудительный ввод символа в выходной файл в качестве неопределенного символа.
Символьная отладочная информация | Символьная отладочная информация из выходного файла. | **Включить все**<br>**Пропустить символы, которые не требуются для обработки перемещения**<br>**Пропустить только символьную отладочную информацию**<br>**Пропустить всю символьную информацию**<br>
Упаковка символьной отладочной информации | Удалить символьную отладочную информацию перед упаковкой.  Для отладки будет использоваться копия исходного двоичного файла.
Имя файла сопоставления | Параметр "Сопоставление" сообщает компоновщику о том, что нужно создать файл сопоставления с именем, указанным пользователем.
Отметить переменные как доступные только для чтения после перемещения | Параметр отмечает переменные как доступные только для чтения после перемещения.
Включить немедленное связывание функций | Этот параметр отмечает объект для немедленного связывания функций.
Требовать исполняемый стек | Этот параметр отмечает выходные данные как не требующие исполняемого стека.
Весь архив | Весь архив использует весь код из источников и дополнительных зависимостей.
Дополнительные параметры | Дополнительные параметры.
Дополнительные зависимости | Указывает дополнительные элементы для добавления в командную строку компоновки.
Зависимости библиотеки | Этот параметр позволяет указать дополнительные библиотеки для добавления в командную строку компоновщика. Они будут добавлены в конец этой строки с префиксом "lib" и расширением "A" или "SO".  (-lFILE)