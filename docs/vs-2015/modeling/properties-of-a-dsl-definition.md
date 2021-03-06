---
title: Свойства определения доменного языка | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, definition file
ms.assetid: 38debcfe-e1a6-4a3f-9d69-3ab07520f2b6
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 50b4325d2329bbaf402dcf2f059c51b5a796bdcd
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49197370"
---
# <a name="properties-of-a-dsl-definition"></a>Свойства определения доменного языка
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Определение свойств DslDefinition *доменный язык* определения свойств, таких как нумерация версий. Свойства DslDefinition отображаются в **свойства** окна, щелкнув пустую область схемы в *конструктора доменного языка*.  
  
 Дополнительные сведения см. в разделе [способ определения доменного языка](../modeling/how-to-define-a-domain-specific-language.md). Дополнительные сведения об использовании этих свойств см. в разделе [Настройка и расширение доменного языка](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
 DslDefinition имеет свойства, в следующей таблице.  
  
|Свойство.|Описание|Значение по умолчанию|  
|--------------|-----------------|-------------|  
|Модификатор доступа|Определяет, является ли модификатор доступа для доменного класса открытым или внутренними.|public|  
|Настраиваемые атрибуты|Пользовательские атрибуты для доменного класса.<br /><br /> **Примечание** нажать кнопку обзора, чтобы добавить атрибут.|\<None >|  
|Название организации|Имя текущего имени компании в системном реестре.|Текущее имя компании|  
|name|Имя данного доменного класса.|Текущее имя|  
|Пространство имен|Пространство имен, связанное с этим доменным классом.|Текущее пространство имен|  
|Идентификатор Guid пакета|Идентификатор guid для [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] пакета, созданного для этого языка DSL.|\<None >|  
|Пространство имен пакета|Пространство имен для [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] пакета, созданного для этого языка DSL.|\<None >|  
|Название продукта|Имя продукта, которое будет зарегистрировано для [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] пакета, созданного для этого языка DSL.|\<None >|  
|Примечания|Заметки, связанные с этим доменным классом.|\<None >|  
|Описание|Описание для данного доменного класса.|\<None >|  
|Отображаемое имя|Имя, которое будет отображаться в созданном конструкторе для данного доменного класса.|\<None >|  
|Ключевое слово Help|Ключевое слово справки, связанный с этим доменным классом.|\<None >|  
|Построить|Номер инкрементное построение для данного определения доменного языка.|0|  
|Основной номер версии|Добавочные основной номер сборки для этого определения доменного языка.|1|  
|Дополнительный номер версии|Добавочные дополнительного номера построения для данного определения доменного языка.|0|  
|Номер редакции|Добавочные версии номер сборки для этого определения доменного языка.|0|  
  
## <a name="see-also"></a>См. также  
 [Глоссарий по средствам доменного языка работы](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)



