---
title: "Постоянные узлы | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c798a50-a2d7-459b-9879-ad4ad8290c9b
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a47eb4e129ac90e8a397c936922a8cc3aeb80277
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
---
# <a name="constant-nodes"></a>Постоянные узлы
В конструкторе шейдеров постоянные узлы представляют литеральные значения и интерполированные атрибуты вершин в вычислениях построителя текстуры. Так как атрибуты вершины интерполированы и поэтому различны для каждого пикселя, каждый экземпляр построителя текстуры получает разную версию константы. Это дает каждому пикселю уникальный внешний вид.  
  
## <a name="vertex-attribute-interpolation"></a>Интерполяция атрибута вершины  
 Изображение трехмерной сцены в игре или приложении создается путем математического преобразования ряда объектов — определяемых вершинами, атрибутами вершин и определениями примитивов — в экранные пиксели. Все сведения, необходимые для придания пикселю его уникального внешнего вида, предоставляются через атрибуты вершины, смешанные в соответствии с близостью пикселя к различным вершинам, составляющим его *примитив*. Примитив — базовый элемент отрисовки; иными словами, простая фигура, например точка, линия или треугольник. Пиксель, очень близко расположенный к одной из вершин, получает константы, почти идентичные этой вершине, но пиксель, равноудаленный от всех вершин примитива, получает константы, представляющие собой среднее для этих вершин. В программировании графики говорят, что константы, которые получают пиксели, *интерполируются*. Предоставление пикселям данных констант таким образом дает очень хорошее визуальное качество и в то же время снижает требования к памяти и пропускной способности.  
  
 Хотя каждый экземпляр построителя текстуры получает только один набор постоянных значений и не может изменять эти значения, разные экземпляры построителя текстуры получают различные наборы данных константы. Такой подход позволяет программе шейдера создавать другой цветовой вывод для каждой пикселя в примитиве.  
  
## <a name="constant-node-reference"></a>Справочник по постоянным узлам  
  
|Узел|Подробные сведения|Свойства|  
|----------|-------------|----------------|  
|**Вектор камеры**|Вектор, построенный из текущего пикселя к камере в абсолютном пространстве.<br /><br /> Этот вектор можно использовать для вычисления отражений в абсолютном пространстве.<br /><br /> **Выходные данные**<br /><br /> `Output`: `float3`<br /> Вектор из текущего пикселя к камере.|Нет|  
|**Константа цвета**|Значение постоянного цвета.<br /><br /> **Выходные данные**<br /><br /> `Output`: `float4`<br /> Значение цвета.|**Выходные данные**<br /> Значение цвета.|  
|**Константа**|Постоянное скалярное значение.<br /><br /> **Выходные данные**<br /><br /> `Output`: `float`<br /> Скалярное значение.|**Выходные данные**<br /> Скалярное значение.|  
|**2D-константа**|Двухкомпонентная константа вектора.<br /><br /> **Выходные данные**<br /><br /> `Output`: `float2`<br /> Векторное значение.|**Выходные данные**<br /> Векторное значение.|  
|**3D-константа**|Трехкомпонентная константа вектора.<br /><br /> **Выходные данные**<br /><br /> `Output`: `float3`<br /> Векторное значение.|**Выходные данные**<br /> Векторное значение.|  
|**4D-константа**|Четырехкомпонентная константа вектора.<br /><br /> **Выходные данные**<br /><br /> `Output`: `float4`<br /> Значение цвета.|**Выходные данные**<br /> Векторное значение.|  
|**Нормализованное положение**|Позиция текущего пикселя, выраженная в нормализованных координатах устройства.<br /><br /> Координата х и координата y имеют значения в диапазоне [–1, 1], координата z имеет значение в диапазоне [0, 1], а компонент w имеет значение глубины точки в пространстве представления; значение w не нормализовано.<br /><br /> **Выходные данные**<br /><br /> `Output`: `float4`<br /> Позиция текущего пикселя.|Нет|  
|**Цвет точки**|Диффузный цвет текущего пикселя, который является сочетанием диффузного цвета материала и цветовых атрибутов вершины.<br /><br /> **Выходные данные**<br /><br /> `Output`: `float4`<br /> Диффузный цвет текущего пикселя.|Нет|  
|**Глубина точки**|Глубина текущего пикселя в пространстве представления.<br /><br /> **Выходные данные**<br /><br /> `Output`: `float`<br /> Глубина текущего пикселя.|Нет|  
|**Нормализованная глубина точки**|Глубина текущего пикселя, выраженная в нормализованных координатах устройства.<br /><br /> Результирующее значение лежит в диапазоне [0, 1].<br /><br /> **Выходные данные**<br /><br /> `Output`: `float`<br /> Глубина текущего пикселя.|Нет|  
|**Положение на экране**|Позиция текущего пикселя, выраженная в координатах экрана.<br /><br /> Координаты экрана основаны на текущем окне просмотра. Компоненты x и y содержат координаты экрана, компонент z содержит глубину, нормализованную до диапазона [0, 1], а компонент w содержит значение глубины в пространстве представления.<br /><br /> **Выходные данные**<br /><br /> `Output`: `float4`<br /> Позиция текущего пикселя.|Нет|  
|**Нормаль к поверхности**|Нормаль к поверхности, построенная из текущего пикселя в пространстве объекта.<br /><br /> Эту нормаль можно использовать для вычисления добавочного освещения и отражений в пространстве объекта.<br /><br /> **Выходные данные**<br /><br /> `Output`: `float3`<br /> Нормаль к поверхности, построенная из текущего пикселя.|Нет|  
|**Вектор камеры в пространстве касательных**|Вектор, построенный из текущего пикселя к камере в пространстве касательных.<br /><br /> Этот вектор можно использовать для вычисления отражений в пространстве касательных.<br /><br /> **Выходные данные**<br /><br /> `Output`: `float3`<br /> Вектор из текущего пикселя к камере.|Нет|  
|**Направление света в пространстве касательных**|Вектор, определяющий направление, в котором излучается свет из источника света в пространстве касательных текущего пикселя.<br /><br /> Этот перпендикуляр можно использовать для вычисления добавочного освещения и отражений в пространстве касательных.<br /><br /> **Выходные данные:**<br /><br /> `Output`: `float3`<br /> Вектор из текущего пикселя к источнику света.|Нет|  
|**Нормаль в системе мировых координат**|Нормаль к поверхности, построенная из текущего пикселя в абсолютном пространстве.<br /><br /> Эту нормаль можно использовать для вычисления добавочного освещения и отражений в абсолютном пространстве.<br /><br /> **Выходные данные**<br /><br /> `Output`: `float3`<br /> Нормаль к поверхности, построенная из текущего пикселя.|Нет|  
|**Положение в мировых координатах**|Позиция текущего пикселя в абсолютном пространстве.<br /><br /> **Выходные данные:**<br /><br /> `Output`: `float4`<br /> Позиция текущего пикселя.|Нет|