---
title: Сортировка, фильтрация и группирование (обозреватель XML-схем) | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a914de0-9ffc-4526-9603-92e460e52513
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 49bd65d0ca9be83665f5f364f5e1f2115279cf5c
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49229740"
---
# <a name="sorting-filtering-and-grouping-xml-schema-explorer"></a>Сортировка, фильтрация и группирование (обозреватель XML-схем)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
В этом разделе описываются параметры, доступные через **параметры группирование, сортировка и фильтрация** меню на панели инструментов обозревателя XML-схем.  
  
## <a name="filter-options"></a>Параметры фильтрации  
 Доступны следующие параметры фильтра: По умолчанию **Показать пространства имен** и **Показать файлы схемы** параметры выбраны.  
  
-   **Показать пространства имен**.  
  
-   **Показать файлы схемы**.  
  
-   **Показать компоновщики (последовательность/Выбор/все)**.  
  
## <a name="sorting-options"></a>Параметры сортировки  
 Доступны следующие параметры сортировки: По умолчанию используется **Сортировка по типу**. Параметры «Сортировка по» не применимы к файлам и пространствам имен.  
  
-   **Сортировать по типу**.  
  
-   **Сортировка по имени**.  
  
-   **Порядок документа**.  
  
### <a name="sort-by-type"></a>Сортировка по типу  
 Когда **Сортировка по типу** параметр выбран, глобальные узлы сортируются в следующем порядке. Внутри каждой группы узлы сортируются в алфавитном порядке.  
  
1.  Узлы `import`.  
  
2.  Узлы `include`.  
  
3.  Узлы `redefine`.  
  
4.  Узлы `attribute`.  
  
5.  Узлы `attributeGroup`.  
  
6.  Узлы `complexType`.  
  
7.  Узлы `simpleType`.  
  
8.  Узлы `element`.  
  
9. Узлы `group`.  
  
### <a name="sort-by-name"></a>Сортировка по имени  
 Когда **Сортировка по имени** параметр выбран, глобальные узлы сортируются в следующем порядке:  
  
1.  Узлы `import` (в алфавитном порядке по пространствам имен).  
  
2.  Узлы `include` (в алфавитном порядке по атрибутам `schemaLocation`).  
  
3.  Узлы `redefine` (в алфавитном порядке по атрибутам `schemaLocation`).  
  
4.  Другие глобальные узлы в алфавитном порядке.  
  
### <a name="document-order"></a>Порядок документа  
 **Порядке документа** параметр доступен, если **Показать файлы схемы** выбран параметр. Когда **порядке документа** выбран, глобальные узлы отображаются в порядке, в котором они появляются в файле схемы.  
  
## <a name="persisting-sortfilter-options"></a>Сохранение сортировки/Параметры фильтрации  
 Параметры сортировки, фильтрации и группирования хранятся в реестре для каждого пользователя, независимо от того, какое решение или файлы были открыты в момент изменения настроек.





