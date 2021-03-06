---
title: 'Практическое: исходный код отладки .NET Framework | Документация Майкрософт'
ms.custom: ''
ms.date: 11/19/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- debugging, .NET Framework source
ms.assetid: fc12e472-ac6a-4e77-8e22-a769e13a03b8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 234d9979ea1a16b917111e2a8937ad71dd55224f
ms.sourcegitcommit: dd839de3aa24ed7cd69f676293648c6c59c6560a
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2018
ms.locfileid: "52389284"
---
# <a name="how-to-debug-net-framework-source"></a>Практическое руководство. Отладка исходного кода .NET Framework

Чтобы выполнить отладку исходного кода .NET Framework, необходимо сделать следующее:

- Включение захода в исходный код .NET Framework.  
  
- Иметь доступ к символам отладки для кода. 
  
  Вы можете загрузить отладочные символы немедленно, или задать параметры для загрузки более поздней версии. Если не загрузить символы немедленно, они будут загрузить при очередном запуске отладки приложения. Во время отладки, можно также использовать **модули** или **стек вызовов** windows для загрузки и загрузить символы.  
  
### <a name="to-enable-stepping-into-net-framework-source"></a>Включение захода в исходный код .NET Framework 
  
1. В разделе **средства** (или **Отладка**) > **параметры** > **отладки** > **Общие**выберите **исходный код .NET Framework включить пошаговое выполнение**.  
   
   - Если был включен режим "Только мой код", появится диалоговое окно с предупреждением об отключении этого режима. Нажмите кнопку **ОК**.  
   
   - Если кэш символов — локальные значение не было, диалоговое окно предупреждения о том, что кэш символов по умолчанию установлена. Нажмите кнопку **ОК**.  
   
1. Выберите **ОК** закрыть **параметры** диалоговое окно.
  
### <a name="to-set-or-change-symbol-source-locations-and-loading-behavior"></a>Чтобы задать или изменить источник расположения символов и поведения при загрузке

1. Выберите **символы** категорию **средства** (или **Отладка**) > **параметры** > **Отладка**.  
  
1. На **символы** раздела **символов (PDB)** выберите **серверы символов Microsoft** для доступа к символы с открытых серверов символов Майкрософт. Выберите кнопки панели инструментов, чтобы добавить другие расположения символов и порядок их загрузки. 
   
1. Чтобы изменить локальные символы кэша, изменить или перейдите в другое расположение, в разделе **кэшировать символы в каталоге**.  
   
1. Чтобы загрузить символы немедленно, выберите **загрузить все символы**. Эта кнопка доступна только во время отладки.  
   
   Если не загружать символы прямо сейчас, они будут загружены при очередном запуске отладки.  
   
1. Выберите **ОК** закрыть **параметры** диалоговое окно.  
  
### <a name="to-load-symbols-from-the-modules-or-call-stack-windows"></a>Чтобы загрузить символы из модулей или стек вызовов windows  
  
1. Во время отладки, откройте окно, выбрав **Отладка** > **Windows** > **модули** или **стек вызовов** . 
   
1. Щелкните правой кнопкой мыши модуль, для которого не загружены символы. В **модули** окно, выполняется загрузка состояния символов **состояние символов** столбца. В **стек вызовов** находится в состоянии окна, в **состояние кадра** столбец и кадр закрашены серым. 
   
   - Выберите **загрузить символы** меню, чтобы найти и загрузить файлы символов из папки на компьютере. 
   
   - Выберите **сведения о загрузке символов** для отображения расположения отладчик поиск символов.  
   
   - Выберите **параметры символов** открыть **символы** страницы. На **символы** раздела **символов (PDB)** выберите **серверы символов Microsoft** для доступа к символы с открытых серверов символов Майкрософт. Выберите кнопки панели инструментов, чтобы добавить другие расположения символов и порядок их загрузки. Выберите **ОК** чтобы закрыть диалоговое окно. 
  
### <a name="see-also"></a>См. также  
 [Отладка управляемого кода](../debugger/debugging-managed-code.md)   
 [Указание файлов символов (.pdb) и файлов с исходным кодом](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)