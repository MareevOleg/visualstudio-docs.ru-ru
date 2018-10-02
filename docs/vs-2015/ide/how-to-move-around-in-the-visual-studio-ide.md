---
title: Практическое руководство. Перемещение по интегрированной среде разработки Visual Studio | Документы Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- environments [Visual Studio], navigation
- documents [Visual Studio], navigating
- IDE, navigation
- navigation [Visual Studio]
- files [Visual Studio], navigating between
- windows [Visual Studio], navigating
- Window.NextDocumentWindowNav
- IDE navigator
ms.assetid: 6c36b6eb-c93f-496b-af08-4199f7afd8bd
caps.latest.revision: 33
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 52d5025b4758463c708d80784db71835e2807abd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47559119"
---
# <a name="how-to-move-around-in-the-visual-studio-ide"></a>Практическое руководство. Перемещение по интегрированной среде разработки Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [как: переместить решения в Интегрированной среде разработки Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-move-around-in-the-visual-studio-ide).  
  
Интегрированная среда разработки (IDE) предназначена для перемещения между окнами и между файлами разными способами в зависимости от предпочтений или требований к проекту. Можно выбрать режим циклического перехода между файлами в редакторе либо циклическое переключение между всеми активными окнами инструментов в интегрированной среде разработки. Кроме того, можно непосредственно переходить к любому открытому в редакторе файлу независимо от того, когда он просматривался последний раз. Эти возможности способны повысить производительность при работе в интегрированной среде разработки.  
  
> [!NOTE]
>  Доступные в диалоговых окнах параметры, а также названия и расположение команд меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. При написании этой страницы справки имелось в виду окно **Обычные параметры разработки**. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="keyboard-shortcuts"></a>Сочетания клавиш  
 Почти для всех команд меню в Visual Studio существуют сочетания клавиш. Можно также создать собственные настраиваемые сочетания клавиш. Дополнительные сведения см. в разделе [Определение и настройка сочетаний клавиш в Visual Studio](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md).  
  
## <a name="navigating-among-files-in-the-editor"></a>Перемещение между файлами в редакторе  
 Существует несколько способов перемещения по открытым в редакторе файлам. Можно перемещаться между файлами на основе порядка доступа к ним, использовать навигатор IDE для быстрого поиска любого открытого файл или закреплять избранные файлы на вкладке, чтобы их всегда можно было видеть.  
  
 Циклические переходы назад и вперед по открытым в редакторе файлам в порядке осуществления к ним доступа во многом схожи с функциями перехода назад и вперед в обозревателе Internet Explorer.  
  
#### <a name="to-move-through-open-files-in-order-of-use"></a>Перемещение между открытыми файлами в порядке использования  
  
-   Чтобы активировать открытые документы в порядке, в котором они просматривались последний раз, нажмите сочетание клавиш CTRL + знак "минус".  
  
-   Чтобы активировать открытые документы в обратном порядке, нажмите сочетание клавиш CTRL + SHIFT + знак "минус".  
  
    > [!NOTE]
    >  В меню **Вид** также находятся команды **Переход назад** и **Переход вперед**.  
  
 Можно также перейти к конкретному открытому в редакторе файлу независимо от времени последнего доступа к нему. Для этого используется **Навигатор по интегрированной среде разработки**, список **Активные файлы** в редакторе или диалоговое окно **Окна**.  
  
 **Навигатор по интегрированной среде разработки** работает практически аналогично переключателю между окнами приложений. Он недоступен из меню и открывается только с помощью сочетаний клавиш. Для доступа к **навигатору по интегрированной среде разработки** можно использовать любую из двух команд (приведены ниже), чтобы переключаться между файлами в нужном порядке.  
  
 ![Навигатор интегрированной среды разработки Visual Studio](../ide/media/vs2015-ide-navigator.png "VS2015_IDE_Navigator")  
  
 `Window.PreviousDocumentWindowNav` позволяет переходить к последнему файлу, к которому осуществлялся доступ, а `Window.NextDocumentWindowNav` позволяет перемещаться в обратном порядке. Согласно общим параметрам разработки для `Window.PreviousDocumentWindowNav` назначено сочетание клавиш CTRL + SHIFT + TAB, а для `Window.NextDocumentWindowNav` — CTRL + TAB.  
  
> [!NOTE]
>  Если у используемой комбинации параметров отсутствует сочетание клавиш, назначенное этой команде, на странице **Клавиатура** диалогового окна **Параметры** можно назначить собственную настраиваемую команду. Дополнительные сведения см. в разделе [Определение и настройка сочетаний клавиш в Visual Studio](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md).  
  
#### <a name="to-switch-to-specific-files-in-the-editor"></a>Переход к конкретным файлам в редакторе  
  
-   Нажмите сочетание клавиш CTRL+TAB, чтобы открыть **навигатор по интегрированной среде разработки**. Удерживая нажатой клавишу CTRL, нажимайте клавишу TAB до тех пор, пока не будет выбран файл, к которому нужно перейти.  
  
    > [!TIP]
    >  Чтобы изменить порядок перехода по списку **Активные окна инструментов**, удерживайте нажатыми клавиши CTRL+SHIFT и нажмите клавишу TAB.  
  
     \- или -  
  
-   В правом верхнем углу редактора нажмите кнопку **Активные файлы** и в списке выберите нужный файл.  
  
     \- или -  
  
-   В строке меню выберите **Окно**, **Окна**.  
  
-   В списке выберите файл для просмотра и нажмите кнопку **Активировать**.  
  
## <a name="navigating-among-tool-windows-in-the-ide"></a>Перемещение между окнами инструментов в интегрированной среде разработки  
 **Навигатор по интегрированной среде разработки** позволяет переключаться между окнами инструментов, которые открыты в интегрированной среде разработки. Для доступа к **навигатору по интегрированной среде разработки** можно использовать любую из двух команд, чтобы переключаться между окнами инструментов в нужном порядке. `Window.PreviousToolWindowNav` позволяет переходить к последнему файлу, к которому осуществлялся доступ, а `Window.NextToolWindowNav` позволяет перемещаться в обратном порядке. Согласно общим параметрам разработки для `Window.PreviousDocumentWindowNav` назначено сочетание клавиш SHIFT + ALT + F7, а для `Window.NextDocumentWindowNav` — ALT + F7.  
  
> [!NOTE]
>  Если у используемой комбинации параметров отсутствует сочетание клавиш, назначенное этой команде, на странице **Клавиатура** диалогового окна **Параметры** можно назначить собственную настраиваемую команду. Дополнительные сведения см. в разделе [Определение и настройка сочетаний клавиш в Visual Studio](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md).  
  
#### <a name="to-switch-to-a-specific-tool-window-in-the-ide"></a>Переход к конкретному окну инструмента в интегрированной среде разработки  
  
-   Нажмите сочетание клавиш ALT+F7, чтобы открыть **навигатор по интегрированной среде разработки**. Удерживая нажатой клавишу ALT, нажимайте клавишу F7 до тех пор, пока не появится окно, в которое нужно переключиться.  
  
    > [!TIP]
    >  Чтобы изменить порядок перехода по списку **Активные окна инструментов**, удерживайте нажатыми клавиши SHIFT+ALT и нажмите клавишу F7.  
  
## <a name="see-also"></a>См. также  
 [Настройка макетов окон](../ide/customizing-window-layouts-in-visual-studio.md)   
 [Сочетания клавиш по умолчанию](../ide/default-keyboard-shortcuts-in-visual-studio.md)




