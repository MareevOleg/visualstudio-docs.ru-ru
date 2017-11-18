---
title: "Функция SccDirDiff | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccDirDiff"
helpviewer_keywords: 
  - "Функция SccDirDiff"
ms.assetid: 26c9ba92-e3b9-4dd2-bd5e-76b17745e308
caps.latest.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 15
---
# Функция SccDirDiff
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Эта функция отображает различия между текущий локальный каталог на диске клиента и соответствующий проект в системе управления версиями.  
  
## Синтаксис  
  
```cpp#  
SCCRTN SccDirDiff(  
   LPVOID    pContext,  
   HWND      hWnd,  
   LPCSTR    lpDirName,  
   LONG      dwFlags,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### Параметры  
 pContext  
 \[in\] Структура подключаемого модуля контекста исходного элемента управления.  
  
 hWnd  
 \[in\] Дескриптор окна интегрированной среды разработки, подключаемый модуль системы управления версиями можно использовать в качестве родительского для все диалоговые окна, которые он предоставляет.  
  
 lpDirName  
 \[in\] Полный путь к локальному каталогу, для которого необходимо отобразить visual различие.  
  
 dwFlags  
 \[in\] Команда флагов \(см. Примечания раздела\).  
  
 pvOptions  
 \[in\] Параметры конкретного подключаемого модуля системы управления версиями.  
  
## Возвращаемое значение  
 Реализации подключаемого модуля управления источника этой функции должен возвращать одно из следующих значений:  
  
|Значение|Описание|  
|--------------|--------------|  
|SCC\_OK|В каталоге на диске совпадает проекта в системе управления версиями.|  
|SCC\_I\_FILESDIFFER|В каталоге на диске отличается от проекта в системе управления версиями.|  
|SCC\_I\_RELOADFILE|Файл или проект должен быть перезагружен.|  
|SCC\_E\_FILENOTCONTROLLED|Каталог не существует в системе управления версиями.|  
|SCC\_E\_NOTAUTHORIZED|Для выполнения этой операции не разрешено пользователю.|  
|SCC\_E\_ACCESSFAILURE|Произошла ошибка при доступе к системе управления версиями, вероятно, из\-за проблемы с сетью или конфликтов. Рекомендуется повторить операцию.|  
|SCC\_E\_NONSPECIFICERROR<br /><br /> SCC\_E\_UNKNOWNERROR|Неспецифическая ошибка.|  
|SCC\_E\_FILENOTEXIST|Не удалось найти локальный каталог.|  
  
## Заметки  
 Эта функция используется для указания системы управления версиями, подключаемый модуль для отображения пользователю список изменений в указанном каталоге. Подключаемый модуль открывается отдельное окно, в формате его выбор, чтобы отобразить различия между пользователя каталог на диске и соответствующий проект в системе управления версиями.  
  
 Если подключаемый модуль поддерживает сравнение каталоги вообще, он должен поддерживать сравнение каталогов на основе имени файла, даже если параметры «быстрое diff», не поддерживаются.  
  
|`dwFlags`|Интерпретация|  
|---------------|-------------------|  
|SCC\_DIFF\_IGNORECASE|Сравнение без учета регистра \(может использоваться для быстрого копирования или визуального\).|  
|SCC\_DIFF\_IGNORESPACE|Игнорирует пробелы \(может использоваться для быстрого копирования или визуального\).|  
|SCC\_DIFF\_QD\_CONTENTS|Если поддерживается подключаемый модуль системы управления версиями, автоматически сравнивает каталоге байт за байтом.|  
|SCC\_DIFF\_QD\_CHECKSUM|Если поддерживается подключаемый модуль, автоматически сравнивает каталогу через контрольной суммы или, если не поддерживается, возвращается к SCC\_DIFF\_QD\_CONTENTS.|  
|SCC\_DIFF\_QD\_TIME|Если поддерживается подключаемый модуль, автоматически сравнивает каталогу через его отметки времени или, если не поддерживается, возвращается на SCC\_DIFF\_QD\_CHECKSUM или SCC\_DIFF\_QD\_CONTENTS.|  
  
> [!NOTE]
>  Эта функция использует те же флаги команды, как [SccDiff](../extensibility/sccdiff-function.md). Тем не менее подключаемый модуль системы управления версиями, можно не поддерживают операции «быстрое diff» для каталогов.  
  
## См. также  
 [Функции API подключаемого модуля источника элемента управления](../extensibility/source-control-plug-in-api-functions.md)