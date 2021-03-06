---
title: Функция SccGetCommandOptions | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccGetCommandOptions
helpviewer_keywords:
- SccGetCommandOptions function
ms.assetid: bbe4aa4e-b4b0-403e-b7a0-5dd6eb24e5a9
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 10f47a193a3ff47412249e094c1c9364653350ae
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51810095"
---
# <a name="sccgetcommandoptions-function"></a>Функция SccGetCommandOptions
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Эта функция запрашивает у пользователя Дополнительные параметры для определенной команды.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp#  
SCCRTN SccGetCommandOptions(  
   LPVOID pvContext,  
   HWND hWnd,  
   enum SCCCOMMAND iCommand,  
   LPCMDOPTS* ppvOptions  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 pvContext  
 [in] Структура подключаемого модуля контекста исходного элемента управления.  
  
 hWnd  
 [in] Дескриптор окна интегрированной среды разработки, подключаемый модуль системы управления версиями можно использовать в качестве родительского для любой диалоговых окон, которые он предоставляет.  
  
 iCommand  
 [in] Команда, для которого запрашиваются Дополнительные параметры (см. в разделе [код команды](../extensibility/command-code-enumerator.md) возможные значения).  
  
 ppvOptions  
 [in] Структура параметров (также может быть `NULL`).  
  
## <a name="return-value"></a>Возвращаемое значение  
 Подключаемый модуль реализации элемента управления источника этой функции должен возвращать одно из следующих значений:  
  
|Значение|Описание:|  
|-----------|-----------------|  
|SCC_OK|Выполнено.|  
|SCC_I_ADV_SUPPORT|Подключаемый модуль системы управления версиями поддерживает дополнительные параметры для команды.|  
|SCC_I_OPERATIONCANCELED|Пользователь отменил исходный элемент управления подключаемого модуля в **параметры** диалоговое окно.|  
|SCC_E_OPTNOTSUPPORTED|Подключаемый модуль системы управления версиями не поддерживает эту операцию.|  
|SCC_E_ISCHECKEDOUT|Невозможно выполнить эту операцию с файлом, который в данный момент извлечен.|  
|SCC_E_ACCESSFAILURE|Возникла проблема с доступом к системе управления версиями, возможно, из-за проблемы с сетью или конфликтов. Рекомендуется повторить операцию.|  
|SCC_E_NONSPECIFICERROR|Обнаружена неспецифическая ошибка.|  
  
## <a name="remarks"></a>Примечания  
 Интегрированная среда разработки вызывает эту функцию в первый раз с `ppvOptions` = `NULL` для определения того, если подключаемый модуль системы управления версиями поддерживает функцию Дополнительные параметры для заданной команды. Если подключаемый модуль поддерживает функцию, для этой команды, интегрированной среды разработки вызывает эту функцию снова, когда пользователь запрашивает дополнительные параметры (обычно реализуются как **Дополнительно** кнопку в диалоговом окне) и предоставляет НЕНУЛЕВОЙ указатель для `ppvOptions` , указывающий `NULL` указатель. Подключаемый модуль сохраняет любые дополнительные параметры, указанные пользователем в структуру частного и возвращает указатель на этой структуре в `ppvOptions`. Эта структура передается ко всем функциям API подключаемых модулей исходного элемента управления, которые нужно знать о нем, включая последующие вызовы `SccGetCommandOptions` функции.  
  
 Пример может помочь прояснить ситуацию.  
  
 Пользователь выбирает **получить** команда и интегрированной среды разработки отображается **получить** диалоговое окно. Интегрированная среда разработки вызовы `SccGetCommandOptions` функционировать с `iCommand` присвоено `SCC_COMMAND_GET` и `ppvOptions` присвоено `NULL`. Это значение интерпретируется системой управления версиями, подключаемый модуль в виде вопрос, «У вас есть любые дополнительные параметры для этой команды?» Если подключаемый модуль возвращает `SCC_I_ADV_SUPPORT`, среда интегрированной разработки отобразит **Дополнительно** кнопку в его **получить** диалоговое окно.  
  
 В первый раз пользователь нажимает кнопку **Дополнительно** кнопки, интегрированной среды разработки снова вызывает `SccGetCommandOptions` функции, теперь отличного`NULL``ppvOptions` , указывающий `NULL` указатель. Подключаемый модуль отображает свой собственный **получить параметры** диалоговое окно запрашивает у пользователя сведения помещает эту информацию в отдельную структуру и возвращает указатель на этой структуре в `ppvOptions`.  
  
 Если пользователь нажимает кнопку **Дополнительно** снова вызывает интегрированной среды разработки в том же диалоговом окне `SccGetCommandOptions` функцию еще раз без изменения `ppvOptions`, так что структуры передается обратно подключаемого модуля. Это позволяет подключаемого модуля, чтобы повторно инициализировать его диалоговое окно со значениями, которые пользователь ранее было задано. Подключаемый модуль изменяет структуру на месте перед возвратом.  
  
 Наконец, когда пользователь щелкает **ОК** в интегрированной среде разработки **получить** диалоговое окно, интегрированная среда разработки вызывает [SccGet](../extensibility/sccget-function.md), передачи структуры, возвращаемые в `ppvOptions` , содержащий Дополнительные параметры.  
  
> [!NOTE]
>  Команда `SCC_COMMAND_OPTIONS` используется, когда интегрированная среда разработки отображает **параметры** диалоговое окно, которое позволяет пользователю задать параметры, определяющие работы интеграции. Если указать собственное диалоговое окно установки подключаемого модуля системы управления версиями, его можно отобразить из **Дополнительно** кнопку в диалоговое окно настроек интегрированной среды разработки. Подключаемый модуль не отвечает за получение и сохранять эти данные; Интегрированная среда разработки не использовать его, или измените ее.  
  
## <a name="see-also"></a>См. также  
 [Функции API подключаемого модуля управления источника](../extensibility/source-control-plug-in-api-functions.md)   
 [Код команды](../extensibility/command-code-enumerator.md)

