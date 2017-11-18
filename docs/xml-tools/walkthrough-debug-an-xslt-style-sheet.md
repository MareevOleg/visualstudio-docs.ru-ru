---
title: "Пошаговое руководство: отладка таблицы стилей XSLT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3db9fa5a-f619-4cb6-86e7-64b364e58e5d
caps.latest.revision: 2
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 2
---
# Пошаговое руководство: отладка таблицы стилей XSLT
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Шаги в данном пошаговом руководстве демонстрируют, как использовать XSLT\-отладчик.Шаги включают просмотр переменных, задание точек останова и пошаговое прохождение кода.Таблица стилей находит все книги, которые стоят меньше средней цены книги.  
  
### Подготовка к пошаговому руководству  
  
1.  Закройте все открытые решения.  
  
2.  Скопируйте два файла с образцами на локальный компьютер.  
  
## Начало отладки  
  
#### Начало отладки  
  
1.  В меню **Файл** укажите пункт **Открыть**, затем выберите пункт **Файл**.  
  
2.  Найдите файл belowAvg.xsl и нажмите кнопку **Открыть**.  
  
     Таблица стиля откроется в XML\-редакторе.  
  
3.  Нажмите кнопку обзора \(**...**\) в поле **Ввод** окна свойств документа.  
  
4.  Найдите файл books.xml и нажмите кнопку **Открыть**.  
  
     Таким образом задается файл исходного документа, используемого в XSLT\-преобразовании.  
  
5.  Щелкните правой кнопкой мыши начальный тег `xsl:if`, укажите пункт **Точка останова**, затем выберите пункт **Вставить точку останова**.  
  
6.  На панели инструментов редактора XML нажмите кнопку **Отладка XSL**.  
  
 Это запускает процесс отладки и открывает несколько новых окон, которые используются отладчиком.  
  
 Входной документ и таблица стиля отображаются в двух окнах.Отладчик использует эти окна, чтобы показывать текущее состояние выполнения.Отладчик располагается на элементе `xsl:if` таблицы стиля и на первом узле книги файла books.xml.  
  
 Окно локальных значений отображает все локальные переменные и их текущие значения.Сюда относятся переменные, определенные в таблице стиля, а также переменные, используемые отладчиком для отслеживания узлов, которые в настоящий момент находятся в контексте.  
  
 Окно **Ввод XSL** отображает результат XSL\-преобразования.Это окно существует наряду с окном **Вывод Visual Studio**.  
  
## Окно просмотра значений  
  
#### Использование окна просмотра значений  
  
1.  В меню **Отладка** укажите пункты **Окна**, **Просмотр**, затем выберите пункт **Просмотр 1**.  
  
     Отобразится окно «Просмотр 1».  
  
2.  Введите `$bookAverage` в поле **Имя** и нажмите клавишу «ВВОД».  
  
     В окне отобразится значение переменной `$bookAverage`.  
  
3.  Введите `self::node()` в поле **Имя** и нажмите клавишу «ВВОД».  
  
     `self::node()` является выражением XPath, которое вычисляется до текущего узла контекста.Значение `self::node()` выражения XPath является первым узлом книги.Оно меняется по мере прохождения преобразования.  
  
4.  Раскройте узел `self::node()`, а затем узел `price`.  
  
     Это позволяет увидеть значение цены книги, и его можно легко сравнить со значением `$bookAverage`.Так как цена книги ниже средней, условие `xsl:if` должно выполняться.  
  
## Пошаговое прохождение кода  
 Отладчик позволяет выполнять код по одной строке.  
  
#### Пошаговое прохождение кода  
  
1.  Нажмите клавишу **F5**, чтобы продолжить.  
  
     Так как первый узел книги удовлетворяет условию `xsl:if`, узел книги добавляется в окно вывода XSL.Отладчик продолжает выполнение, пока не будет вновь достигнут элемент `xsl:if` в таблице стилей.Теперь отладчик располагается на втором узле книги в файле books.xml.  
  
     В окне «Просмотр 1» значение `self::node()` изменяется на второй узел книги.Проверив значение элемента цены, можно определить, что цена выше средней; таким образом, условие `xsl:if` не выполняется.  
  
2.  Нажмите клавишу **F5**, чтобы продолжить.  
  
     Так как второй узел книги не удовлетворяет условию `xsl:if`, узел книги не добавляется в окно вывода XSL.Отладчик продолжает выполнение, пока не будет вновь достигнут элемент `xsl:if` в таблице стилей.Теперь отладчик располагается на третьем узле `book` в файле books.xml.  
  
     В окне «Просмотр 1» значение `self::node()` изменяется на третий узел книги.Проверив значение элемента `price`, можно определить, что цена ниже средней; таким образом, условие `xsl:if` выполняется.  
  
3.  Нажмите клавишу **F5**, чтобы продолжить.  
  
     Так как условие `xsl:if` выполняется, третья книга добавляется в окно «Вывод XSL».Все книги в XML\-документе обработаны, отладчик прекращает выполнение.  
  
## Файлы образца  
 В этом пошаговом руководстве используются следующие два файла.  
  
### belowAvg.xsl  
  
```  
<?xml version='1.0'?>  
<xsl:stylesheet version="1.0"  
      xmlns:xsl="http://www.w3.org/1999/XSL/Transform">  
  <xsl:output method="xml" encoding="utf-8"/>  
  <xsl:template match="/">  
    <xsl:variable name="bookCount" select="count(/bookstore/book)"/>  
    <xsl:variable name="bookTotal" select="sum(/bookstore/book/price)"/>  
    <xsl:variable name="bookAverage" select="$bookTotal div $bookCount"/>  
    <books>  
      <!--Books That Cost Below Average-->  
      <xsl:for-each select="/bookstore/book">  
        <xsl:if test="price < $bookAverage">  
          <xsl:copy-of select="."/>  
        </xsl:if>  
      </xsl:for-each>  
    </books>  
  </xsl:template>  
</xsl:stylesheet>  
```  
  
### books.xml  
  
```  
<?xml version='1.0'?>  
<!-- This file represents a fragment of a book store inventory database -->  
<bookstore>  
  <book genre="autobiography" publicationdate="1981" ISBN="1-861003-11-0">  
    <title>The Autobiography of Benjamin Franklin</title>  
    <author>  
      <first-name>Benjamin</first-name>  
      <last-name>Franklin</last-name>  
    </author>  
    <price>8.99</price>  
  </book>  
  <book genre="novel" publicationdate="1967" ISBN="0-201-63361-2">  
    <title>The Confidence Man</title>  
    <author>  
      <first-name>Herman</first-name>  
      <last-name>Melville</last-name>  
    </author>  
    <price>11.99</price>  
  </book>  
  <book genre="philosophy" publicationdate="1991" ISBN="1-861001-57-6">  
    <title>The Gorgias</title>  
    <author>  
      <name>Plato</name>  
    </author>  
    <price>9.99</price>  
  </book>  
</bookstore>  
```  
  
## См. также  
 [Отладка XSLT](../xml-tools/debugging-xslt.md)