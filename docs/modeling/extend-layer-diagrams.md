---
title: "Расширение схемы зависимостей | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-techdebt
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dependency diagrams, creating extensions
- layer models
ms.assetid: 83fca301-b008-485a-87eb-218050e71451
caps.latest.revision: 39
author: alexhomer1
ms.author: ahomer
manager: douge
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3d07f82ea737449fee6dfa04a61e195654ba35fa
ms.openlocfilehash: ad673b1bc7d3089c37717dd7e1f1fce4e86d8100
ms.lasthandoff: 02/22/2017

---
# <a name="extend-dependency-diagrams"></a>Расширение схемы зависимостей
Можно написать код для создания и обновления схемы зависимостей, а также для проверки структуры программного кода по схемам зависимостей в Visual Studio. Вы можете добавить команды, которые отображаются в контекстном меню схем, настроить жесты перетаскивания, а также получить доступ к модели слоев из текстовых шаблонов. Вы можете упаковать эти расширения в расширение Visual Studio Integration Extension (VSIX) и предоставить их другим пользователям Visual Studio.  
  
 Дополнительные сведения о схемах зависимостей см.:  
  
-   [Схемы зависимостей: Справочник](../modeling/layer-diagrams-reference.md)  
  
-   [Схемы зависимостей: рекомендации](../modeling/layer-diagrams-guidelines.md)  
  
-   [Создание схем зависимостей в коде](../modeling/create-layer-diagrams-from-your-code.md)  
  
-   [Проверка кода по схемам зависимостей](../modeling/validate-code-with-layer-diagrams.md)  
  
##  <a name="a-nameprereqsa-requirements"></a><a name="prereqs"></a> Требования  
 На компьютере, где планируется разрабатывать расширения слоев, должны быть установлены следующие компоненты:  
  
-   Visual Studio  
  
-   [Пакет SDK для Visual Studio](../extensibility/visual-studio-sdk.md)  
  
-   Пакет SDK моделирования для Visual Studio  


[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

  
 На компьютере, где планируется выполнять расширения слоев, должна быть установлена подходящая версия Visual Studio. Дополнительные сведения см. в разделе [развертывание расширения модели слоев](../modeling/deploy-a-layer-model-extension.md).  
  
 Чтобы узнать, какие версии Visual Studio поддерживают схемы зависимостей, см. раздел [поддержка версий для инструментов моделирования и архитектуры](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="in-this-section"></a>Содержание  
 [Добавление команд и жестов в схемы зависимостей](../modeling/add-commands-and-gestures-to-layer-diagrams.md)  
  
 [Добавление пользовательской проверки архитектуры в схемы зависимостей](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)  
  
 [Добавление пользовательских свойств в схемы зависимостей](../modeling/add-custom-properties-to-layer-diagrams.md)  
  
 [Перемещение по моделям слоев в коде программы и их обновление](../modeling/navigate-and-update-layer-models-in-program-code.md)  
  
 [Развертывание расширения модели слоев](../modeling/deploy-a-layer-model-extension.md)  
  
 [Устранение неполадок расширений для схем зависимостей](../modeling/troubleshoot-extensions-for-layer-diagrams.md)  
  
## <a name="see-also"></a>См. также  
 [Определение и Установка расширения моделирования](../modeling/define-and-install-a-modeling-extension.md)   
 [Схемы зависимостей: Справочник](../modeling/layer-diagrams-reference.md)   
 [Схемы зависимостей: рекомендации](../modeling/layer-diagrams-guidelines.md)   
 [Создание схем зависимостей в коде](../modeling/create-layer-diagrams-from-your-code.md)   
 [Проверка кода по схемам зависимостей](../modeling/validate-code-with-layer-diagrams.md)   
