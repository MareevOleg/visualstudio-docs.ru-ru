---
title: Что&#39;возможности пакета SDK для Visual Studio 2017 | Документация Майкрософт
ms.custom: ''
ms.date: 10/31/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 9efcf0a3-dbde-4cab-8ed3-425826a48b2e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6f2a003bc19764aa07262552d3f0cc41316835b6
ms.sourcegitcommit: ef828606e9758c7a42a2f0f777c57b2d39041ac3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2018
ms.locfileid: "39566912"
---
# <a name="what39s-new-in-the-visual-studio-2017-sdk"></a>Что&#39;возможности пакета SDK для Visual Studio 2017

Пакет SDK для Visual Studio имеет следующие новые и обновленные функции для Visual Studio 2017.

## <a name="vsix-v3-format"></a>Формат VSIX v3

Чтобы обеспечить поддержку установки нового облегченные версии Visual Studio 2017, формат манифеста расширения VSIX был обновлен до версии 3 (VSIX v3).

Новый формат имеет поддержку:

* Явно объявив необходимые условия для выявления и установленные установщик VSIX.
* NGen сборки на время ожидания установки расширения.
* Установка ресурсами за пределами корневого обычные расширения.

Дополнительные сведения об этих изменениях, см. в разделах:

* [Изменения в расширяемости для 2017 г.](breaking-changes-2017.md)
* [Поддержка NGen в VSIX v3](ngen-support.md)
* [Установка за пределами папки расширений](set-install-root.md)
* [Часто задаваемые вопросы по расширяемости Visual Studio 2017](faq-2017.md)

## <a name="migrate-extensibility-project-to-visual-studio-2017"></a>Перенос проектов расширяемости в Visual Studio 2017

Сведения об обновлении проектов расширяемости и манифесты VSIX для Visual Studio 2017, см. в разделе [как: перенос проектов расширяемости в Visual Studio 2017](how-to-migrate-extensibility-projects-to-visual-studio-2017.md).

## <a name="custom-project-and-item-templates"></a>Настраиваемые шаблоны проектов и элементов

Начиная с Visual Studio 2017, сканирование на наличие шаблонов пользовательских проектов и элементов больше не выполняется. Вместо этого расширения необходимо указать файлы манифеста, которые описывают расположение установки из этих шаблонов. Visual Studio 2017 можно использовать, чтобы обновить расширения VSIX. При развертывании расширения с помощью MSI, необходимо создать файлы манифеста шаблонов вручную. Дополнительные сведения см. в разделе [обновление настраиваемых шаблонов проектов и элементов для Visual Studio 2017](../extensibility/upgrading-custom-project-and-item-templates-for-visual-studio-2017.md). Шаблон манифеста документирована в [Справочник по схемам манифеста шаблонов Visual Studio](../extensibility/visual-studio-template-manifest-schema-reference.md).

## <a name="updated-extension-performance-guidelines"></a>Рекомендации по производительности обновленного расширения

Доступна новая [как: Диагностика производительности расширения](how-to-diagnose-extension-performance.md) статьи в разделе [управления пакеты VSPackage](managing-vspackages.md) демонстрирует, как обнаруживать и анализировать влияние расширения на Visual Studio запуска и загрузки решения раз.
