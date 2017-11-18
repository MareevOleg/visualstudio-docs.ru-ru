---
title: "Установка платформ модульного тестирования сторонних поставщиков | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 47893b70-46f8-49dc-84bd-ec820178f683
caps.latest.revision: 10
ms.author: douge
manager: douge
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 5ab78b6b8eaa8156ed2c8a807b1d8a80e75afa84
ms.openlocfilehash: 1c0cf482a2a5862ea8e34d20e3e75f005dbc0f17
ms.lasthandoff: 04/04/2017

---
# <a name="install-third-party-unit-test-frameworks"></a>Установка платформ модульного тестирования сторонних поставщиков
Обозреватель тестов Visual Studio может запускать любую платформу модульного тестирования, разработавшую интерфейс адаптера для обозревателя. Программа установки платформы устанавливает двоичные файлы и добавляет шаблоны проекта Visual Studio для поддерживаемых языков. При создании проекта с шаблоном платформа регистрируется с помощью обозревателя тестов. Решение Visual Studio может содержать проекты модульного тестирования, которые используют разные платформы, предназначенные для разных языков. Обозреватель тестов выполняет их все.  
  
 **Requirements**  
  
-   Visual Studio Enterprise, Visual Studio Professional  
  
## <a name="acquiring-third-party-frameworks"></a>Приобретение сторонних платформ  
 Вы можете скачать и установить множество сторонних платформ модульного тестирования, используя диспетчер расширений Visual Studio, или сделать это в коллекции Visual Studio на веб-сайте MSDN. Платформы можно также скачать с других сайтов, например с веб-сайта платформы.  
  
### <a name="installing-from-visual-studio"></a>Установка из Visual Studio  
  
1.  Выберите **Сервис** в стандартном меню, а затем **Расширения и обновления**.  
  
2.  Разверните узел **В сети**, **Галерея Visual Studio**, **Сервис**. Выберите **Тестирование**.  
  
3.  Откройте список, чтобы найти платформу.  
  
4.  Выберите платформу и нажмите кнопку **Скачать**.  
  
 Дополнительные сведения см. в разделе [Поиск и использование расширений Visual Studio](../ide/finding-and-using-visual-studio-extensions.md).  
  
### <a name="installing-from-the-web"></a>Установка из Интернета  
 Если вы знаете интересующую вас платформу:  
  
1.  Откройте [галерею Visual Studio](http://go.microsoft.com/fwlink/?LinkId=236267) на веб-сайте MSDN.  
  
2.  Введите имя платформы в поле **Найти**.  
  
3.  Выберите платформу в списке результатов, чтобы перейти на страницу "Коллекция Visual Studio" инструмента.  
  
 Чтобы открыть список платформ с другими средствами тестирования:  
  
1.  Откройте [галерею Visual Studio](http://go.microsoft.com/fwlink/?LinkId=236267) на веб-сайте MSDN.  
  
2.  Щелкните **Обзор**.  
  
3.  В списке **Категория** разверните узел **Сервис** и выберите **Тестирование**.  
  
4.  Выберите платформу в списке результатов, чтобы перейти на страницу "Коллекция Visual Studio" инструмента.  
  
## <a name="see-also"></a>См. также  
 [Модульное тестирование кода](../test/unit-test-your-code.md)
