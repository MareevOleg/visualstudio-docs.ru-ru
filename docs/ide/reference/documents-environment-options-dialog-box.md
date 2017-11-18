---
title: "Страница \"Документы\", папка \"Среда\", диалоговое окно \"Параметры\" | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.Environment.Documents
- VS.ToolsOptionsPages.Environment.Documents
- VS.ToolsOptionsPag.Environment.Documents
helpviewer_keywords:
- Documents Environment Options dialog box
- defaults, directories
- error messages, customizing
- files [Visual Studio], default options
- files [Visual Basic], auto-loading modified
- windows, customizing environment
- in-memory editing
- folders [Visual Studio], specifying where Open File goes
- Open File dialog box
- windows, enabling re-use of current
- notifications, files changed
- files [Visual Studio], displaying in Solution Explorer
- default directories
- read-only files, editing
- Options dialog box, showing Miscellaneous Files
- directories [Visual Studio], IDE environment options
- Options dialog box, Documents page
- warnings, files changed
- Solution Explorer, displaying files in
ms.assetid: 4e3ccf1b-cd68-4db6-9470-710c911b47fc
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c7d9f7cef6c0dfa35a4a718c0918fbc55409af04
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
---
# <a name="documents-environment-options-dialog-box"></a>Страница "Документы", папка "Среда", диалоговое окно "Параметры"
Используйте эту страницу диалогового окна **Параметры** для управления отображением документов в интегрированной среде разработки (IDE), а также внешними изменениями, вносимыми в документы и файлы. Чтобы перейти к этому диалоговому окну, щелкните пункт **Параметры** в меню **Сервис**, а затем разверните узел **Среда** и выберите пункт **Документы**. Если страница **Документы** отсутствует в списке, выберите **Показать все параметры** в диалоговом окне **Параметры**.  
  
> [!NOTE]
>  Доступные в диалоговых окнах параметры, а также названия и расположение команд меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](../../ide/personalizing-the-visual-studio-ide.md).  
  
 **Открывать новый файл в том же окне, если текущий сохранен**  
 Если этот флажок установлен, текущий документ закрывается, если он был сохранен, и в том же окне открывается новый документ. Если текущий документ не был сохранен, он остается открытым, а новый документ открывается в отдельном окне. Если этот флажок снят, новый документ всегда открывается в отдельном окне.  
  
 Используйте этот параметр, если вы редко выполняете операции вырезания и вставки в нескольких документах и хотите свести к минимуму число открытых документов и окон в рабочей области.  
  
 **Обнаруживать факт изменения файла вне среды**  
 Если этот флажок установлен, сообщение немедленно уведомляет вас о внесении изменений в открытый файл, если эти изменения были сделаны с помощью редактора за пределами интегрированной среды разработки. Сообщение позволяет повторно загрузить файл из хранилища.  
  
 **Автоматически загружать изменения, сделанные вне среды**  
 Если установлен флажок **Обнаруживать факт изменения файла вне среды**, то при внесении изменений в файл, открытый в IDE, за пределами среды разработки по умолчанию выводится предупреждающее сообщение. Если этот флажок установлен, предупреждение не выводится и документ повторно загружается в интегрированную среду разработки с учетом внешних изменений.  
  
 **Изменение файлов только для чтения с запросом при сохранении**  
 Если этот флажок установлен, можно открывать и редактировать файлы только для чтения. По завершении работы с файлом необходимо использовать команду **Сохранить как**, чтобы сохранить файл под новым именем, если требуется сохранить запись изменений.  
  
 **Открывать файлы в каталоге текущего активного документа**  
 Если этот флажок установлен, параметр задает отображение в диалоговом окне **Открыть файл** каталога активного документа. Если этот флажок снят, в диалоговом окне **Открыть файл** отображается каталог, из которого был открыт последний файл.  
  
 **Проверять при загрузке окончания строк на однотипность**  
 Установите этот флажок, чтобы редактор проверял окончания строк в файле и выводил сообщение, если в форматировании символов конца строки обнаружены несоответствия.  
  
 **Выводить предупреждение, когда глобальная отмена затрагивает измененные файлы**  
 Установите этот флажок, чтобы выводить сообщение, если команда **глобальной отмены** приводит к откату изменений рефакторинга в файлах, которые также были изменены после операции рефакторинга. Возврат файла в состояние до рефакторинга может привести к сбросу последующих изменений, внесенных в файл.  
  
 **Показывать прочие файлы в обозревателе решений**  
 Установите этот флажок для отображения узла **Прочие файлы** в **обозревателе решений**. Прочие файлы — это файлы, не связанные с проектом или решением, которые тем не менее могут отображаться в **обозревателе решений** для вашего удобства.  
  
> [!NOTE]
>  Установите этот флажок, чтобы включить команду **Просмотреть в браузере** в меню **Файл** для веб-документов, не входящих в активное веб-приложение.  
  
 **\<** *n* **> Количество прочих файлов в списке**  
 Указывает количество файлов для хранения в папке **Прочие файлы** **обозревателя решений**. Эти файлы будут отображаться в списке, даже если они больше не открыты в редакторе. Можно указать любое целое число от 0 до 256. По умолчанию задано значение 0.  
  
 Например, если значение этого параметра — 5 и вы открываете 10 прочих файлов, при закрытии всех 10 файлов первые 5 файлов будут по-прежнему отображаться в папке **Прочие файлы**.  
  
 **Сохранять документы в формате Юникод, если данные невозможно сохранить в выбранной кодировке**  
 Установите этот флажок, чтобы файлы, содержащие данные, которые не совместимы с выбранной кодовой страницей, по умолчанию сохранялись в кодировке Юникод.  
  
## <a name="see-also"></a>См. также  
 [Диалоговое окно "Параметры среды"](../../ide/reference/environment-options-dialog-box.md)   
 [Прочие файлы](../../ide/reference/miscellaneous-files.md)   
 [Поиск и замена текста](../../ide/finding-and-replacing-text.md)