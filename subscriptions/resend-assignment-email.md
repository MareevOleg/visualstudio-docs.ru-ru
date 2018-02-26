---
title: "Как повторно отправлять электронные сообщения о назначении подписки с сайта manage.visualstudio.com или через VLSC | Документация Майкрософт"
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 2/13/2018
Ms.topic: Get-Started-Article
Description: Learn how to resend the subscription assignment to subscribers from manage.visualstudio.com or VLSC
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: 0ba7d6e36c25ced78b0c6b25688e5eb5b26eb04a
ms.sourcegitcommit: a07b789cc41ed72664f2c700c1f114476e7b0ddd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2018
---
# <a name="how-to-resend-subscription-assignment-emails"></a>Как повторно отправлять электронные сообщения о назначении подписки

Действия по повторной отправке сообщений электронной почты о назначении подписки зависят от того, с помощью какого портала выполняется управление подписками. 

## <a name="resending-assignment-emails-from-within-managevisualstudiocom"></a>Повторная отправка электронных сообщений о назначении подписки с сайта manage.visualstudio.com

Повторная отправка электронных сообщений о назначениях с помощью портала manage.visualstudio.com выполняется очень просто:

1. Войдите на портал [manage.visualstudio.com](https://manage.visualstudio.com). 
2. На вкладке **Фильтр** найдите подписчика, которому необходимо повторно отправить электронное сообщение о назначении подписки. Дополнительные сведения о фильтрации см. в инструкциях по [поиску подписок](/visualstudio/subscriptions/search-license).
3. Выберите подписчика.  Выбрать несколько подписчиков можно, удерживая клавиши CTRL или SHIFT.
4. Щелкните **Повторная отправка** в верхней части результатов поиска.  

## <a name="resending-assignment-emails-from-within-vlsc"></a>Повторная отправка электронных сообщений о назначении подписки с помощью VLSC
Если вы назначили подписку определенному подписчику через VLSC, а затем этот подписчик попросил повторно отправить ему сообщение о назначении, для этого проще всего изменить адрес электронной почты в этой подписке, а затем восстановить прежний адрес. Это действие приводит к автоматической отправке сообщения о назначении подписки.

Следуйте приведенным ниже инструкциям, чтобы повторно отправить сообщение о назначении.


1. Откройте центр поддержки корпоративных лицензий (VLSC) и войдите в него.
2. На сайте администрирования Volume Licensing Service Center щелкните **Подписки** и выберите **Подписки Visual Studio**.
3. Выберите **номер соглашения**, связанный с нужной подпиской Visual Studio.
4. Щелкните стрелку вниз на панели **поиска**.  
5. Выполните поиск подписчика при помощи поля "Адрес электронной почты".
6. В списке результатов щелкните **фамилию** подписчика.
7. Нажмите кнопку **Правка**.
8. Внесите изменения в подписку. Не имеет значения, что именно вы будете изменять, важно про просто любое изменение.  Достаточно удалить один символ из адреса электронной почты подписчика, например букву m из доменного имени .com. Нажмите кнопку **Сохранить**.
9. Сохранив информацию, снова нажмите кнопку **Изменить** и восстановите удаленный символ в адресе электронной почты. Нажмите кнопку **Сохранить**.
   
Теперь VLSC определит, что в подписке произошли изменения, и повторно отправит сообщение электронной почты о назначении на адрес, указанный на портале. 

> [!NOTE]
> - Для новых подписок сообщение электронной почты о назначении отправляется автоматически. Описанный выше процесс нужен только в том случае, если пользователь просит отправить новое уведомление или исходное уведомление не было доставлено по любой причине.