---
title: "-Setup (devenv.exe) | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setup Devenv switch
- /setup Devenv switch
- Devenv, /setup switch
ms.assetid: 87608b7f-a156-400c-80f5-fc823f843e61
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e63b69c9d97edf5049dfb6e55b8f9d5010984d4d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
---
# <a name="setup-devenvexe"></a>/Setup (devenv.exe)
Заставляет [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] выполнить слияние метаданных ресурсов, описывающих меню, панели инструментов и группы команд, из всех доступных пакетов VSPackage.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
devenv /setup  
```  
  
## <a name="remarks"></a>Примечания  
 У этого параметра нет аргументов. Команда `devenv /setup` обычно выдается в качестве последнего этапа процесса установки. Использование параметра `/setup` не приводит к запуску [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 Для использования параметров `devenv` и [devenv](../../ide/reference/setup-devenv-exe.md) нужно запустить [devenv](../../ide/reference/installvstemplates-devenv-exe.md) от имени администратора.  
  
## <a name="example"></a>Пример  
 В этом примере показан последний этап установки версии [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], включающей пакеты VSPackage.  
  
```  
devenv /setup  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры командной строки для команды Devenv](../../ide/reference/devenv-command-line-switches.md)