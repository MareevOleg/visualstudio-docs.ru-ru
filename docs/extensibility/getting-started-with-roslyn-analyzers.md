---
title: Начало работы с анализаторами Roslyn | Документация Майкрософт
ms.date: 04/02/2018
ms.technology: vs-ide-sdk
ms.topic: conceptual
ms.assetid: 367c2ec8-3059-46a5-9d1c-57bead0419e7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6077fb8a9f0db360389953ef6a7ed25c6d242247
ms.sourcegitcommit: d7f232a7596420e40ff8051d42cdf90203af4a74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2018
ms.locfileid: "52821296"
---
# <a name="get-started-with-roslyn-analyzers"></a>Начало работы с анализаторами Roslyn

С анализаторами динамическую, основанную на проект кода в Visual Studio авторы API могут поставляться анализа кода для конкретного домена как часть своих пакетов NuGet. Так как эти анализаторы работают на платформе компилятора .NET (кодовое название «Roslyn»), они создают предупреждения в коде при вводе еще до завершения строки (не более ожидания для сборки кода для обнаружения проблем). Анализаторы могут также возникать средство автоматического код из строки лампочки Visual Studio позволяет очистить коде немедленно.

## <a name="get-started"></a>Начало работы

[Общие сведения о анализаторов Roslyn кода в реальном времени и пошаговое руководство](https://msdn.microsoft.com/magazine/dn879356.aspx)

[Добавление средства исправления кода Пошаговое руководство: предоставления пользователям исправления проблем, анализатор](https://msdn.microsoft.com/magazine/dn904670.aspx)

[Общие сведения и пошаговое руководство в реальном мире анализатора](https://channel9.msdn.com/events/Build/2015/3-725)

[Анализатор Roslyn в реальном мире](../extensibility/roslyn-analyzers-and-code-aware-library-for-immutablearrays.md) , вы также можете посмотреть как [говорить](https://channel9.msdn.com/events/Build/2015/3-725)

[Несколько примеров на GitHub, сгруппированы в три вида анализаторы](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Analyzer%20Samples.md)

[Введение и обзор несколько анализаторов](https://channel9.msdn.com/Events/dotnetConf/2015/NET-Compiler-Platform-Roslyn-Analyzers-and-the-Rise-of-Code-Aware-Libraries)

## <a name="see-also"></a>См. также

- [Обзор анализаторов Roslyn](../code-quality/roslyn-analyzers-overview.md)
- [Руководство: Запись вашего первого анализатора и исправлением кода](/dotnet/csharp/roslyn-sdk/tutorials/how-to-write-csharp-analyzer-code-fix)
- [Справочник по версии пакета платформы компилятора .NET](roslyn-version-support.md)
- [Дополнительные документы на сайте GitHub OSS](https://github.com/dotnet/roslyn/tree/master/docs/analyzers)
- [Правила FxCop, реализовано с помощью анализаторов Roslyn на GitHub](https://github.com/dotnet/roslyn/tree/master/src/Diagnostics/FxCop)