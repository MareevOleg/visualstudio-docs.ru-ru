---
title: "Свойства роли домена | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a7bb18c-638e-45e8-9d79-9aa6a9e14b0e
caps.latest.revision: "9"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: e85c47133509e3f7bf7c54b8cfa7f2121a26b04b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2017
---
# <a name="properties-of-domain-roles"></a>Свойства доменных ролей
Свойства в следующей таблице сопоставлены роли домена. Сведения о роли домена см. в разделе [Общие сведения о моделях, классы и отношения](../modeling/understanding-models-classes-and-relationships.md). Дополнительные сведения об использовании этих свойств см. в разделе [настройку и расширение доменного языка](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
|Свойство|Описание|По умолчанию|  
|--------------|-----------------|-------------|  
|Тип коллекции|Если эта роль имеет кратность 0.. * или 1.. \*, это свойство настраивает универсальный тип, который используется для хранения коллекции ссылок.|`(none)` - <xref:Microsoft.VisualStudio.Modeling.LinkedElementCollection%601>используется|  
|Настраиваемые атрибуты|Атрибуты, указанные здесь добавляются как атрибуты к классу созданного кода.|< none\>|  
|Отображается свойство|Если `True`, и если кратность связи от 0 до 1 или 1.. 1, можно просмотреть свойства роли пользователя в **свойства** окна. Свойство отображает имя элемента на другом конце связи.|`True`|  
|Свойство генератор|Если `True`, для этой роли, можно использовать для обхода связи в программном коде создается свойство роли. При выборе значения false, можно переходить по связи менее эффективным способом с помощью статических методов доменной связи.|`True`|  
|Модификатор доступа метода считывания свойства|Модификатор доступа для метода получения значения для свойства созданного (`public`, `internal`, `private`, `protected`, или `protected internal`).|`public`|  
|Модификатор доступа метода задания свойства|Модификатор доступа для задания для свойства созданного (`public`, `internal`, `private`, `protected`, или `protected internal`).|`public`|  
|Кратность|Количество элементов модели, которые можно воспроизвести противоположной роли (`0..1`, `1..1`, `0..*`, или `1..*`). Если кратность `0..*` или `1..*`, вновь созданное свойство представляет коллекцию; в противном случае созданное свойство представляет элемент одной модели.|Зависит от типа связи и является ли роль источника или целевого объекта, в связи.|  
|Имя|Имя роли домена. Это свойство не может содержать пробелы.|Имя класса исполнитель роли домена для этой роли.|  
|Распространяет копирования|`DoNotPropagateCopy`-Исполнителя роли копируются будет копия этой ссылки.<br /><br /> `PropagateCopyToLinkOnly`-Скопированную ссылку указывает на существующий противоположный исполнитель роли.<br /><br /> `PropagateCopyToLinkAndOppositeRolePlayer`— Скопированный ссылка указывает на копию исполнителю противоположной роли.|`PropagateCopyToLinkAndOppositeRolePlayer`для роли источника внедрений.<br /><br /> `DoNotPropagateCopy`для других ролей.<br /><br /> Дополнительные сведения см. в разделе [Настройка функции копирования](../modeling/customizing-copy-behavior.md)|  
|Распространяет Delete|`True`Чтобы удалить элемент, который играет этой роли, при удалении соответствующей ссылки.|`True`в качестве целевого объекта внедряемой роли.<br /><br /> `False`для других ролей.<br /><br /> Дополнительные сведения см. в разделе [Настройка поведения удаления](../modeling/customizing-deletion-behavior.md).|  
|Имя свойства|Имя свойства, создаваемые в коде исполнителя роли. Это имя не может содержать пробелы.|Имя противоположной роли, если эта роль имеет ноль к одному или один к одному кратности; в противном случае имя pluralized противоположной роли.|  
|Исполнитель роли|Класс домена элемента, который может играть эту роль в отношении. Это свойство доступно только для чтения.|Класс домена исполнителя роли для этой роли.|  
|Примечания|Неформальные заметки, связанные с ролью домена.|< none\>|  
|Категория|Категория, в котором созданное свойство отображается в **свойства** окно в конструкторе созданный. Если это свойство пусто, то созданное свойство отображается в узле **Прочее** категории|< none\>|  
|Описание|Описание, которое используется для документирования кода и используется в пользовательском Интерфейсе созданный конструктором.<br /><br /> Описание появляется в подсказке Intellisense для свойства в созданный класс проигрывателя ролей.|`Description for`*полное имя роли*|  
|Отображаемое имя|Имя, которое отображается в конструкторе, созданного для роли домена.|Скорректированное значение свойства Name.|  
|Ключевое слово Help|Необязательное ключевое слово, используемое для индексации справки F1 для роли домена.|\<None >|  
|Отображаемое имя свойства|Имя, которое отображается в конструкторе, созданный для свойства созданных ролей.|Скорректированное значение свойства имени свойства.|  
  
> [!NOTE]
>  Отображаемое имя по умолчанию основан на значение связанного свойства посредством вставки пробелов перед каждый символ верхнего регистра, которому предшествует символ в нижнем регистре и, не следуют другие символы верхнего регистра.  
  
## <a name="see-also"></a>См. также  
 [Свойства доменных связей](../modeling/properties-of-domain-relationships.md)