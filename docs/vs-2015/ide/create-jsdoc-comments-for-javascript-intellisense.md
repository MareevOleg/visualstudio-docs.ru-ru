---
title: Создание комментариев JSDoc для JavaScript IntelliSense | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0dadc81-3755-4a47-bcee-c1010819ff2a
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9d338b2bece99f720670871a1b92c6b2a57c4280
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49908591"
---
# <a name="create-jsdoc-comments-for-javascript-intellisense"></a>Создание комментариев JSDoc для JavaScript IntelliSense
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Технология IntelliSense в Visual Studio отображает сведения, которые добавляются в скрипт с помощью стандартных комментариев JSDoc. Комментарии JSDoc можно использовать для предоставления сведений об элементах кода, например о функциях, полях и переменных.  

## <a name="jsdoc-comment-tags"></a>Теги для комментариев JSDoc  
 В технологии IntelliSense для отображения сведений о коде используются следующие стандартные теги для комментариев JSDoc.  


|  Тег JSDoc   |                       Синтаксис                        |                                                     Примечания                                                      |
|--------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
| @deprecated  |              @deprecated *Описание*              |                                   Указывает устаревшую функцию или метод.                                   |
| @description |             @description *Описание*              |                              Указывает описание для функции или метода.                               |
|    @param    | @param {*тип*} *parameterName*<em>описание</em> | Указывает сведения для параметра в функции или методе.<br /><br /> TypeScript также поддерживает @paramTag. |
|  @property   |          @property {*тип*} *propertyName*          |   Указывает сведения, включая описание, для поля или элемента, который определен в объекте.    |
|   @returns   |                  @returns {*тип*}                  |           Указывает возвращаемое значение.<br /><br /> TypeScript, использовать @returnType вместо @returns.           |
|   @summary   |               @summary *Описание*                |                   Указывает описание функции или метода (аналогично @description).                   |
|    @type     |                   @type {*тип*}                    |                                Указывает тип для константы или переменной.                                |
|   @typedef   |         @typedef {*тип*} *customTypeName*          |                                            Указывает пользовательский тип.                                            |

### <a name="examples"></a>Примеры  
 В следующем примере показано использование @description, @param, и @return JSDoc теги для функции с именем `getArea`.  

```javascript  
/** @description Determines the area of a circle that has the specified radius parameter.  
 * @param {number} radius The radius of the circle.  
 * @return {number}  
 */  
function getArea(radius) {  
    var areaVal;  
    areaVal = Math.PI * radius * radius;  
    return areaVal;  
}  
```  

 В предыдущем примере IntelliSense отображает описание, параметры и возвращаемые сведения при вводе открывающей скобки для `getArea`.  

 ![Сведения IntelliSense для функции](../ide/media/js-intellisense-jsdoc-comments.png "JS_IntelliSense_JSDoc_Comments")  

 В следующем примере показано, как использовать @typedef пометить @property тега.  

```javascript  
/**  
  * @typedef {object} Weather  
  * @property {string} current The current weather.  
  */  
function getForecast(Weather) {  
}  

var w = new Weather();  
```  

 В следующем примере показано использование @type тегов JSDoc. Как показано в этом примере единый звездочки (*), выполните начальное звездочками (\*\*) не являются обязательными.  

```javascript  
/**  
    @type {string}  
*/  
const RED = 'FF0000';  

```  

 В следующем примере показано, как использовать @deprecated тег JSDoc.  

```javascript  
/**  
 * @deprecated since version 2.0  
 */  
function old() {  
}  
```



