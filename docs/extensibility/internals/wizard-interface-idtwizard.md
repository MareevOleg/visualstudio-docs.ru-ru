---
title: Интерфейс мастера (IDTWizard) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDTWizard interface
- wizards, interface
ms.assetid: 09618d9d-d115-45b6-bccc-de328994b39c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8f1bc71239ff7923676c35496e103223a6b6e56e
ms.sourcegitcommit: d462dd10746624ad139f1db04edd501e7737d51e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2018
ms.locfileid: "50219865"
---
# <a name="wizard-interface-idtwizard"></a>Интерфейс мастера (IDTWizard)
Интегрированной среде разработки (IDE) использует <xref:EnvDTE.IDTWizard> интерфейс для взаимодействия с помощью мастеров. Мастера должен реализовывать этот интерфейс для установки в интегрированной среде разработки.  
  
 <xref:EnvDTE.IDTWizard.Execute%2A> Метод является единственным способом, связанные с <xref:EnvDTE.IDTWizard> интерфейс. Мастера реализации этого метода и интегрированной среды разработки вызывает метод в интерфейсе. В следующем примере показана сигнатура метода.  
  
```  
/* IDTWizard Method */  
STDMETHOD(Execute)(THIS_  
   /* [in] */ IDispatch *Application,  
   /* [in] */ long hwndOwner,  
   /* [in] */ SAFEARRAY * *ContextParams,  
   /* [in] */ SAFEARRAY * *CustomParams,  
   /* [out] [in] */ wizardResult *RetVal  
   );  
```  
  
 Механизма запуска одинакова для обоих **новый проект** и **Добавление нового элемента** мастеров. Для запуска, вызовите <xref:EnvDTE.IDTWizard> интерфейсом, определенным в Dteinternal.h. Единственное различие — это совокупность контекст и настраиваемые параметры, которые передаются на интерфейс, при вызове интерфейса.  
  
 Ниже описана процедура <xref:EnvDTE.IDTWizard> интерфейс, который должен быть реализован мастеров для работы в [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] интегрированной среды разработки. Интегрированная среда разработки вызовы <xref:EnvDTE.IDTWizard.Execute%2A> метод в мастере, передавая ему следующее:  
  
-   Объект DTE  
  
     Объект DTE является корнем модели автоматизации.  
  
-   Дескриптор диалогового окна, как показано в фрагменте кода, `hwndOwner ([in] long)`.  
  
     Мастер использует это `hwndOwner` как родительский для диалоговое окно мастера.  
  
-   Параметры контекста передается интерфейс как данные variant для безопасного массива SAFEARRAY как показано в фрагменте кода, `[in] SAFEARRAY (VARIANT)* ContextParams`.  
  
     Контекстные параметры содержат массив значений, характерные для типа запуска мастера и текущее состояние проекта. Интегрированная среда разработки передает параметры контекста к мастеру. Дополнительные сведения см. в разделе [параметры контекста](../../extensibility/internals/context-parameters.md).  
  
-   Пользовательские параметры, передаваемые интерфейс как переменная типа variant для безопасного массива SAFEARRAY как показано в фрагменте кода, `[in] SAFEARRAY (VARIANT)* CustomParams`.  
  
     Пользовательские параметры содержат массив пользовательских параметров. VSZ-файл передает пользовательские параметры в интегрированную среду разработки. Значения определяются `Param=` инструкций. Дополнительные сведения см. в разделе [пользовательских параметров](../../extensibility/internals/custom-parameters.md).  
  
-   Возвращаемые значения для интерфейса:  
  
    ```  
    wizardResultSuccess = -1,  
    wizardResultFailure = 0  
    wizardResultCancel = 1  
    wizardResultBackout = 2  
    ```  
  
## <a name="see-also"></a>См. также  
 [Параметры контекста](../../extensibility/internals/context-parameters.md)   
 [Пользовательские параметры](../../extensibility/internals/custom-parameters.md)   
 [Мастеры](../../extensibility/internals/wizards.md)   
 [Файл мастера (VSZ-файл)](../../extensibility/internals/wizard-dot-vsz-file.md)