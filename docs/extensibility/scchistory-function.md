---
title: "Функция SccHistory | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccHistory
helpviewer_keywords:
- SccHistory function
ms.assetid: a636d9d3-47c1-4b48-ac6b-bcfde19d6cf9
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
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
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 0efb8505fa59957f8178214d64c7ac0d979a3359
ms.contentlocale: ru-ru
ms.lasthandoff: 09/26/2017

---
# <a name="scchistory-function"></a>Функция SccHistory
Эта функция отображает журнал указанные файлы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
SCCRTN SccHistory(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pvContext`  
 [in] Исходная структура подключаемого модуля контекста элемента управления.  
  
 `hWnd`  
 [in] Дескриптор окна интегрированной среды разработки, подключаемый модуль системы управления версиями можно использовать в качестве родительского для все диалоговые окна, которые он предоставляет.  
  
 `nFiles`  
 [in] Число файлов, указанных в `lpFileName` массива.  
  
 `lpFileName`  
 [in] Массив полных имен файлов.  
  
 `fOptions`  
 [in] Команда флаги (в настоящее время не используется).  
  
 `pvOptions`  
 [in] Параметры для конкретного подключаемого модуля системы управления версиями.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Реализация подключаемого модуля управления источника этой функции должен возвращать одно из следующих значений:  
  
|Значение|Описание|  
|-----------|-----------------|  
|SCC_OK|Журнал версий был успешно получен.|  
|SCC_I_RELOADFILE|Система управления версиями фактически изменения файла на диске при получении журнала (например, путем получения более старые версии), поэтому интегрированной среды разработки следует перезагрузить этот файл.|  
|SCC_E_FILENOTCONTROLLED|Файл не существует в системе управления версиями.|  
|SCC_E_OPNOTSUPPORTED|Система управления версиями не поддерживает эту операцию.|  
|SCC_E_NOTAUTHORIZED|Для выполнения этой операции не разрешено пользователю.|  
|SCC_E_ACCESSFAILURE|Возникла проблема с доступом к системе управления версиями, возможно, из-за проблемы с сетью или конфликтов. Рекомендуется повторить операцию.|  
|SCC_E_PROJNOTOPEN|Проект не был открыт.|  
|SCC_E_NONSPECIFICERROR|Неспецифичную сбоя. Не удалось получить файл журнала.|  
  
## <a name="remarks"></a>Примечания  
 Подключаемый модуль системы управления версиями может отображать свое собственное диалоговое окно для отображения каждого файла журнала с помощью `hWnd` как родительское окно. Кроме того, дополнительный текст вывода обратного вызова передаваемое функции [SccOpenProject](../extensibility/sccopenproject-function.md) можно использовать, если он поддерживается.  
  
 Обратите внимание, что при определенных обстоятельствах, анализируемый файл может измениться во время выполнения этого вызова. Например [!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)] журнал команды предоставляет пользователю возможность получения старой версии файла. В этом случае система управления подключаемый модуль возвращает `SCC_I_RELOAD` , чтобы предупредить интегрированной среды разработки, что необходимо перезагрузить файл.  
  
> [!NOTE]
>  Если подключаемый модуль системы управления версиями не поддерживает эту функцию для массива файлов, могут отображаться только истории файлов для первого файла.  
  
## <a name="see-also"></a>См. также  
 [Функции API подключаемого модуля управления источника](../extensibility/source-control-plug-in-api-functions.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)