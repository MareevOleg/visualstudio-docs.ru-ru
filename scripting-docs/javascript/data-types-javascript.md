---
title: "Типы данных (JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "boolean - тип данных, поддерживаемые типы данных"
ms.assetid: c7a6bd3a-4b1c-4dbe-8505-106dbf483b41
caps.latest.revision: 35
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 35
---
# Типы данных (JavaScript)
В [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] есть три основных типа данных, два составных типа данных и два специальных типа данных.  
  
## Основные типы данных  
 Основными \(базовыми\) типами данных являются:  
  
-   Строка.  
  
-   Number  
  
-   Boolean  
  
## Составные типы данных  
 Составными \(ссылочными\) типами данных являются:  
  
-   Объект.  
  
-   Массив  
  
## Специальные типы данных  
 Специальными типами данных являются:  
  
-   Null  
  
-   Не определено  
  
## Тип данных String  
 Строковое значение представляет собой цепочку, состоящую из нуля или более знаков Юникода \(букв, цифр или знаков пунктуации\).  Строковый тип данных используется для представления текста в [!INCLUDE[javascript](../javascript/includes/javascript-md.md)].  Для включения в скрипты строковых литералов, их необходимо заключить в одинарные или двойные кавычки.  В строках, заключенных в одинарные кавычки, можно использовать двойные кавычки, а в строках, заключенных в двойные кавычки, можно использовать одинарные кавычки.  Ниже представлены примеры строк.  
  
```javascript  
"Happy am I; from care I'm free!"  
'"Avast, ye lubbers!" roared the technician.'   
"45"  
'c'  
```  
  
 Обратите внимание, что [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] не имеет типа для представления одиночного символа.  Для представления отдельного символа в [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] создается строка, которая состоит только из одного символа.  Строка, содержащая нуль знаков \(""\) называется пустой строкой \(или строкой нулевой длины\).  
  
 Для представления знаков, которые невозможно ввести без преобразования, в [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] предусмотрены escape\-последовательности, включаемые в строки.  Например, `\t` задает символ табуляции.  Для получения дополнительной информации см. [Специальные символы](../javascript/advanced/special-characters-javascript.md).  
  
## Тип данных Number  
 В [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], нет различия между целым числом и числом с плавающей запятой; число [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] может быть и тем, и тем \(по сути, [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] представляет все числа в качестве значения с плавающей запятой\).  
  
### Целочисленные значения  
 Целочисленные значения могут быть положительными целыми числами, отрицательным целыми числами и 0.  В качестве основы представления этих чисел можно использовать 10 \(десятичное представление\), 16 \(шестнадцатеричное представление\) и 8 \(восьмеричное представление\).  Большинство чисел в [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] записываются в десятичном представлении.  
  
 Все шестнадцатеричные \("hex"\) целые числа содержат префикс "0x" \(ноль и x&#124;X\).  В их состав могут входить только цифры от 0 до 9 и буквы от A до F \(в верхнем или нижнем регистре\).  Буквы A\-F используются для представления десятичных чисел от 10 до 15.  То есть шестнадцатеричное число 0xF эквивалентно десятичному числу 15, а 0x10 эквивалентно числу 16.  
  
 Все восьмеричные целые числа содержат префикс "0" \(ноль\).  В их состав могут входить только цифры от 0 до 7.  Число, которое начинается с цифры "0" и содержит цифры "8" и \(или\) "9", интерпретируется как десятичное.  
  
 Восьмеричные и шестнадцатеричные числа могут быть отрицательными, однако они не могут содержать дробную часть и их невозможно записать в научной \(экспоненциальной\) нотации.  
  
> [!NOTE]
>  Начиная с версии [!INCLUDE[jsv9text](../javascript/includes/jsv9text-md.md)], [parseInt function](../javascript/reference/parseint-function-javascript.md) не обрабатывает строку, которая имеет префикс "0" как восьмеричная.  Когда функция `parseInt` не используется, строки с префиксом "0", однако, по\-прежнему могут интерпретироваться как восьмеричные.  
  
### Значения с плавающей запятой  
 Значения с плавающей запятой могут быть целыми числами с дробной частью.  Кроме того, эти числа можно записать в экспоненциальной нотации.  То есть строчная или прописная "e" обозначает "десять в степени...".  В [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] числа представляются с использованием 8\-байтного стандарта IEEE 754 представления чисел с плавающей запятой.  Это означает, что можно записывать числа такие большие, как 1.79769x10<sup>308</sup>, и такие небольшие, как 5x10<sup>-324</sup>.  Число, содержащие десятичную запятую и имеющее один "0" до десятичной запятой, интерпретируется как десятичное число с плавающей запятой.  
  
 Обратите внимание, что число, которое начинается с "0x" или "00" и содержит десятичную запятую, создает ошибку.  Ниже приведены некоторые примеры чисел [!INCLUDE[javascript](../javascript/includes/javascript-md.md)].  
  
|Number|Описание|Десятичный эквивалент|  
|------------|--------------|---------------------------|  
|.0001, 0.0001, 1e\-4, 1.0e\-4|Четыре эквивалентных представления чисел с плавающей запятой.|0.0001|  
|3,45e2|Число с плавающей запятой.|345|  
|45|Параметр типа Integer \(целое число\).|45|  
|0378|Параметр типа Integer \(целое число\).  Оно выглядит как восьмеричное число \(поскольку начинается с нуля\), однако 8 не является допустимой восьмеричной цифрой, поэтому данное число интерпретируется как десятичное.|378|  
|0377|Восьмеричное целое число.  Обратите внимание, что, хотя внешне оно всего на единицу меньше числа, показанного выше, его фактическое значение совершенно другое.|255|  
|0.0001|Число с плавающей запятой.  Хотя оно и начинается с нуля, однако не является восьмеричным числом, поскольку содержит десятичную запятую.|0.0001|  
|00.0001|Это ошибка.  Два ведущих нуля помечают число как восьмеричное, но восьмеричные числа не могут иметь десятичные компоненты.|Нет \(ошибка компилятора\)|  
|0Xff|Шестнадцатеричное целое число.|255|  
|0x37CF|Шестнадцатеричное целое число.|14287|  
|0x3e7|Шестнадцатеричное целое число.  Обратите внимание, что "e" не интерпретируется здесь как экспонента.|999|  
|0x3,45e2|Это ошибка.  Шестнадцатеричные числа не могут содержать дробных частей.|Нет \(ошибка компилятора\)|  
  
 Кроме того, [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] содержит числа со специальными значениями.  Эти особые значения приведены ниже.  
  
-   NaN \(не число\).  Используется при выполнении математической операции над недопустимыми данными, такими как строки или неопределенное значение  
  
-   Положительная бесконечность.  Используется, если положительное число слишком велико и не может быть представлено в [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]  
  
-   Отрицательная бесконечность.  Используется, если отрицательное число слишком велико и не может быть представлено в [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]  
  
-   Положительный и отрицательный 0.  [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] различает положительный и отрицательный ноль.  
  
## Логический тип данных  
 В то время как строковые и числовые типы данных могут принимать практическое неограниченное число различных значений, логический тип данных может принимать только два значения.  Это литералы `true` и `false`.  Логическое значение является значением истинности: оно определяет, является ли условие истинным или нет.  
  
 Результат сравнения в скриптах всегда будет иметь тип логического значения.  Рассмотрим следующую строку кода [!INCLUDE[javascript](../javascript/includes/javascript-md.md)].  
  
```javascript  
y = (x == 2000);  
```  
  
 Здесь значение переменной `x` сравнивается с числом 2000.  Если равно, результатом сравнения является логическое значение **true**, которое присваивается переменной `y`.  Если значение `x` не равно 2000, результатом сравнения является логическое значение `false`.  
  
 Логические значения особенно полезны в управляющих структурах.  Следующий код объединяет сравнение, которое создает логическое значение, непосредственно с оператором, который использует его.  Рассмотрим следующий пример кода [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]:  
  
```javascript  
if (x == 2000) {  
    z = z + 1;  
}  
else {  
    x = x + 1;  
}  
```  
  
 Оператор `if/else` в [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] выполняет одно действие, если логическое значение равно `true` \(`z = z + 1`\), и другое действие, если логическое значение равно `false` \(`x = x + 1`\).  
  
 В качестве сравнительного выражения можно использовать любое выражение.  Любое выражение, которое возвращает значение 0, null, undefined или пустую строку, интерпретируется как `false`.  Выражение, определяющее какое\-либо другое значение, интерпретируется как `true`.  К примеру, можно использовать такое выражение:  
  
```javascript  
// This may not do what you expect. See below!  
if (x = y + z)   
```  
  
 Обратите внимание, что приведенная выше строка не проверяет, равно ли `x` величине `y + z`, поскольку используется только одинарный знак равенства \(знак присвоения\).  Вместо этого приведенный выше код присваивает значение `y + z` переменной `x`, а затем проверяет, равен ли результат всего выражения \(то есть значение `x`\) нулю.  Чтобы проверить, является ли `x` равным `y + z`, следует использовать следующий код.  
  
```javascript  
// This is different from the code above!  
if (x == y + z)   
```  
  
 Дополнительные сведения о сравнениях см. в разделе [Управление выполнением программы](../javascript/controlling-program-flow-javascript.md).  
  
## Тип данных NULL  
 Тип данных `null` имеет только одно значение в [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]: значение null.  Ключевое слово `null` невозможно использовать в качестве имени функции или переменной.  
  
 Переменная, которая содержит `null`, не содержит допустимых Number, String, Boolean, Array или Object.  Можно стереть содержимое переменной \(не удаляя переменную\), присваивая ей значение `null`.  
  
 Обратите внимание, что в [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] значение `null` — не то же самое, что 0 \(как в C и C\+\+\).  Кроме того, оператор `typeof` в [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] определяет значения `null` как значения типа `Object`, а не типа `null`.  Такое поведение, которое может запутать разработчиков, используется в целях обратной совместимости.  
  
## Неопределенный тип данных  
 Значение `undefined` возвращается при использовании свойства объекта, которое не существует, или переменной, которая была объявлена, но так и не получила значения.  
  
 Можно проверить, существует ли переменная, сравнивая ее с `undefined`, однако можно проверить, является ли ее тип `undefined`, сравнивая тип переменной со строкой "undefined".  В следующем примере показано, как определить, была ли объявлена переменная `x`:  
  
```javascript  
  
var x;  
  
// This method works.  
if (x == undefined) {  
    document.write("comparing x to undefined <br/>");  
}  
.  
// This method doesn't work - you must check for the string "undefined".  
if (typeof(x) == undefined) {  
    document.write("comparing the type of x to undefined <br/>");  
}  
// This method does work.   
if (typeof(x) == "undefined") {  
    document.write("comparing the type of x to the string 'undefined'");  
}  
  
// Output:   
// comparing x to undefined   
// comparing the type of x to the string 'undefined'  
  
```  
  
 Также можно сравнить неопределенное значение с `null`.  Это сравнение дает значение `true`, если свойство `someObject.prop` равно `null`, или если свойство `someObject.prop` не существует.  
  
```javascript  
someObject.prop == null;  
```  
  
 Чтобы узнать, существует ли свойство объекта, можно использовать оператор **in** :  
  
```javascript  
if ("prop" in someObject)  
    // someObject has the property 'prop'  
```  
  
## См. также  
 [Объекты и массивы](../javascript/objects-and-arrays-javascript.md)   
 [Оператор typeof](../javascript/reference/typeof-operator-decrementjavascript.md)