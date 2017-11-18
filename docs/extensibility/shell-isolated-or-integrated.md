---
title: "Оболочка (изолированных или кэш-памяти) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio shell
- Visual Studio, Shell
- Shell [Visual Studio]
- Visual Studio shell, shell-based applications
- Shell [Visual Studio], shell-based applications
ms.assetid: c64a9bf0-9bf8-45c3-8fa2-306fa6cab66a
caps.latest.revision: 25
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: ed0e82dbc2c093a94080fe3fcf07a3e3b20e1a50
ms.lasthandoff: 02/22/2017

---
# <a name="shell-isolated-or-integrated"></a>Оболочка (изолированных или кэш-памяти)
Можно создать собственные приложения на основе Visual Studio в режиме интеграции или изолированной. В интегрированном режиме доступны многие возможности Visual Studio, помимо приложения. В изолированном режиме выбрать подмножество функций Visual Studio, которые вы хотите распространять вместе с собственный модуль.  
  
## <a name="integrated-mode"></a>Интегрированный режим  
 Интегрированный режим позволяет пользователям использовать стандартные функции Visual Studio, а также пользовательские инструменты. Интегрированная оболочка предназначена главным образом для размещения языков программирования и средств разработки программного обеспечения.  
  
 Пользовательские инструменты, построенные на основе интегрированной оболочки автоматически объединяться с любой другой выпуск Visual Studio, которая установлена на том же компьютере. Распространяемая версия Visual Studio интегрированной оболочки можно предоставить, если Visual Studio не установлена.  
  
 Распространяемая версия оболочки Visual Studio интегрирован отсутствует языками программирования и функции, которые поддерживают соответствующие им системы проектирования.  
  
> [!NOTE]
>  В интегрированном режиме оболочки Visual Studio можно установить вместе с все выпуски Visual Studio кроме экспресс-выпусков.  
  
 Дополнительные сведения см. в разделе [оболочки Visual Studio (интегрированная)](../extensibility/visual-studio-shell-integrated.md).  
  
## <a name="isolated-mode"></a>Изолированный режим  
 Изолированный режим позволяет создавать пользовательские средства, которые выполняются side-by-side с другими версиями Visual Studio. Он предназначен главным образом для средств, которые могут обращаться к службам без в зависимости от стандартных функций Visual Studio для Visual Studio. Можно настроить внешний вид приложений, построенных на основе оболочки Visual Studio изолированного. Можно легко отключить функции и группы команды меню, которые вы не хотите отображаются вместе с приложением.  
  
 Дополнительные сведения см. в разделе [изолированной оболочки Visual Studio](../extensibility/visual-studio-isolated-shell.md).  
  
## <a name="distributing-your-integrated-or-isolated-shell-application"></a>Распространение приложения встроенной или изолированной оболочки  
 Чтобы распространять приложения встроенной или изолированной оболочки, необходимо включить приложения специальных встроенной или изолированной оболочки распространяемый пакет и программа установки. Дополнительные сведения об установке и распространения см. в разделе [распространение изолированных приложений оболочки](../extensibility/distributing-isolated-shell-applications.md).  
  
> [!IMPORTANT]
>  [Лицензионное соглашение конечного пользователя (EULA)](https://www.visualstudio.com/en-us/support/legal/mt171552) для интеграции Visual Studio и изолированной оболочки содержит раздел сбора данных (**раздел 3. Data**).  Она описывает данные об использовании клиента, которые могут быть собраны корпорацией Майкрософт от пользователей либо встроенной или изолированной оболочки программного обеспечения, встраивать в приложение. Дополнительные сведения см. в разделе [Visual Studio продукта семейства заявление о конфиденциальности Microsoft](https://www.visualstudio.com/en-us/dn948229).  
>   
>  Если сбор данных об использовании отдельных от клиентов через приложение, необходимо предоставить пользователям приложения можно собирать соответствующее уведомление.  При распространении по изолированного или интегрированной оболочки как часть вашего приложения, в соответствии с лицензией на пакет средств разработки Visual Studio программное обеспечение, необходимо включить один из следующих:  
>   
>  -   Лицензионное соглашение конечного пользователя в рамках лицензии на приложение  
> -   собственные лицензионного соглашения, которое требуется клиентам, чтобы согласиться с условиями, которые защищают Visual Studio интегрированы или изолированной оболочки по крайней мере столько как условия лицензии конечного пользователя Microsoft для программы-оболочки  
  
## <a name="additional-resources"></a>Дополнительные ресурсы  
 Дополнительные сведения о распространяемых пакетов см. в разделе [загрузки расширения Visual Studio](http://go.microsoft.com/fwlink/?LinkID=119298) веб-сайта.  
  
## <a name="see-also"></a>См. также  
 [Расширения Visual Studio доставки](../extensibility/shipping-visual-studio-extensions.md)