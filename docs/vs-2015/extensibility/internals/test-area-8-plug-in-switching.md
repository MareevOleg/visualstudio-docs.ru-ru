---
title: 'Области тестирования 8: Переключение подключаемых модулей | Документация Майкрософт'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- source control [Visual Studio SDK], switching plug-ins
- source control plug-ins, switching
ms.assetid: 01370792-b5da-4e46-9ce2-7dd326587141
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6633c2bd2f2f968f10aef215f395203f95c99da1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47568829"
---
# <a name="test-area-8-plug-in-switching"></a>Области тестирования 8. Переключение подключаемых модулей
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [8 область тестирования: переключение подключаемых модулей](https://docs.microsoft.com/visualstudio/extensibility/internals/test-area-8-plug-in-switching).  
  
[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Интегрированной среды разработки (IDE) имеет пользовательский интерфейс (UI), чтобы изменить текущий модуль управления версиями. Эта область тестирования предоставляет тестовые случаи для процесса комплектации подключаемый модуль для решений системы управления версиями.  
  
## <a name="command-menu-access"></a>Доступ к меню команды  
 Следующие [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] в тестовых случаях используются пути меню в среде разработки.  
  
-   Текущий модуль управления версиями: **средства** -> **параметры** -> **системы управления версиями** -> **Выбор подключаемых модулей** .  
  
-   Изменить источник привязку системы управления: **файл** -> **системы управления версиями** -> **Смена системы управления версиями**...  
  
## <a name="common-expected-behavior"></a>Распространенное ожидаемое поведение  
 Изменение системы управления версиями, подключаемый модуль для решения возможен без выхода из Visual Studio или повторная загрузка решения. Кроме того текущий модуль управления версиями автоматически изменится на один, используемые в решении, при загрузке этого решения.  
  
## <a name="test-cases"></a>Тестовые случаи  
 Ниже приведены определенные тестовые случаи для подключаемого модуля коммутации область тестирования.  
  
### <a name="case-8a-automatic-change"></a>Case 8a: автоматическое изменение  
  
#### <a name="expected-behavior"></a>Ожидаемое поведение  
 Когда пользователь загружает решение, в системе управления версиями, решение автоматически загружается, и подключаемый модуль системы управления соответствующий источник выбирается наиболее актуальная.  
  
|Действие|Шаги теста|Ожидаемые результаты для проверки|  
|------------|----------------|--------------------------------|  
|Подключаемый модуль изменение автоматической источника элемент управления|1.  Выберите подключаемый модуль, в разделе тестирования наиболее актуальная (**средства** -> **параметры** -> **системы управления версиями** -> **подключаемого модуля Выбор**.)<br />2.  Создайте новый проект.<br />3.  Чтобы добавьте решение в систему управления версиями.<br />4.  Выберите другой подключаемый модуль (например, [!INCLUDE[vsvss](../../includes/vsvss-md.md)]).<br />5.  Напоминание о выгрузке решения.<br />6.  Снова откройте решение с диска.|Открытого решения.<br /><br /> Подключаемый модуль тестируемого текущий модуль управления версиями.|  
  
### <a name="case-8b-solution-based-change"></a>Case 8b: изменение на основе решений  
  
#### <a name="expected-behavior"></a>Ожидаемое поведение  
 Решения могут иметь его соответствующий системы управления версиями подключаемого модуля изменить.  
  
|Действие|Шаги теста|Ожидаемые результаты для проверки|  
|------------|----------------|--------------------------------|  
|Изменение подключаемого модуля для решения|1.  Выберите подключаемый модуль, в разделе тестирования наиболее актуальная (**средства** -> **параметры** -> **системы управления версиями** -> **подключаемого модуля Выбор**).<br />2.  Создание нового проекта и решения.<br />3.  Чтобы добавьте решение в систему управления версиями.<br />4.  Отменить привязку решения из системы управления версиями (с помощью **Смена системы управления версиями** диалоговое окно).<br />5.  Выберите другой подключаемый модуль (например, [!INCLUDE[vsvss](../../includes/vsvss-md.md)]).<br />6.  Перезагрузите решение с диска, если выгружен.<br />7.  Чтобы добавьте решение в систему управления версиями.<br />8.  Отменить привязку решения из системы управления версиями (с помощью **Смена системы управления версиями** диалоговое окно).<br />9. Выберите подключаемый модуль теста еще раз.<br />10. Перезагрузите решение с диска, если выгружен.<br />11. Привязать решение в исходное расположение (используя **Смена системы управления версиями** диалоговое окно).|Добавить решение в систему управления версиями с помощью выбранного подключаемого модуля.|  
  
## <a name="see-also"></a>См. также  
 [Руководство по тестированию подключаемых модулей системы управления версиями](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)
