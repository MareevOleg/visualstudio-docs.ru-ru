---
title: Подготовка к публикации или развертыванию облачной службы из Visual Studio | Документация Майкрософт
description: Сведения о процедурах для настройки облачной службы и учетной записи службы хранилища и настройка приложения Azure.
author: ghogen
manager: douge
ms.assetid: 92ee2f9e-ec49-4c7a-900d-620abe5e9d8a
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/10/2017
ms.author: ghogen
ms.openlocfilehash: d7643d87f60b953b9c0928571036c7890e4d11f0
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002977"
---
# <a name="prepare-to-publish-or-deploy-a-cloud-service-from-visual-studio"></a>Подготовка к публикации или развертыванию облачной службы из Visual Studio

Чтобы опубликовать проект облачной службы, необходимо настроить следующие службы как описано в этой статье:

* Объект **облачная служба** для запуска роли в среде Azure, и 
* Объект **учетной записи хранения** , предоставляющий доступ к службам BLOB-объектов, очередей и таблиц.

## <a name="create-a-cloud-service"></a>Создание облачной службы

Облачная служба запускает ваши роли в среде Azure. Можно создать облачную службу в Visual Studio или с помощью [портала Azure](https://portal.azure.com/) как описано в следующих разделах.

### <a name="create-a-cloud-service-from-visual-studio"></a>Создание облачной службы из Visual Studio

1. Ранее созданный проект облачной службы, щелкните правой кнопкой мыши проект select **публикации**.
1. При необходимости войдите с помощью корпорации Майкрософт или учетная запись организации связывается с вашей подпиской Azure, а затем выберите **Далее** для перехода к **параметры** страницы.
1. Объект **Создание облачной службы и учетной записи хранения** откроется диалоговое окно (если это не так, выберите **Create New** из **облачной службы** списка).
1. Введите имя, без учета регистра для облачной службы, который является частью URL-адреса и должно быть уникальным. Также выберите регион или территориальную группу и выберите функцию репликации.

### <a name="create-a-cloud-service-through-the-azure-portal"></a>Создание облачной службы на портале Azure

1. Войдите на [портал Azure](https://portal.azure.com/).
1. Выберите **облачные службы (классические)** в левой части страницы.
1. Выберите **+ добавить**, затем введите требуемые сведения (DNS имя, подписку, группу ресурсов и расположение). Это не требуется отправлять пакет на этом этапе, так как это сделать позже в Visual Studio.
1. Выберите **создать** для завершения процесса.

## <a name="create-a-storage-account"></a>Создание учетной записи хранения

Учетная запись хранения предоставляет доступ к службам BLOB-объектов, очередей и таблиц. Можно создать учетную запись хранения с помощью Visual Studio или [портала Azure](https://portal.azure.com/).

### <a name="create-a-storage-account-from-visual-studio"></a>Создайте учетную запись хранилища из Visual Studio

1. В **обозревателе решений** ранее созданный проект облачной службы, найдите **подключенных служб** узла в проект роли, щелкните правой кнопкой мыши и выберите **добавить подключенную службу**. (В Visual Studio 2015, щелкните правой кнопкой мыши **хранения** узел и выберите **создать учетную запись хранения**.)
1. В **подключенных служб** списка выберите **Облачное хранилище в службе хранилища Azure**.
1. В появившемся диалоговом окне службы хранилища Azure, выберите **+ создать новую учетную запись хранения**, чего откроется диалоговое окно, в котором указаны подписки, имя fo учетной записи, ценовой уровень, группу ресурсов и расположение.
1. Выберите **создать** после завершения. Учетная запись хранения появится в списке доступных учетных записей хранения в подписке.
1. Выберите учетную запись и выберите **добавить**.

### <a name="create-a-storage-account-through-the-azure-portal"></a>Создание учетной записи хранения на портале Azure

1. Войдите на [портал Azure](https://portal.azure.com/).
1. Выберите **+ создать** в левом верхнем углу.
1. Выберите **хранения** в разделе «Azure Marketplace,» затем **учетная запись хранения — большой двоичный объект, файл, таблица, очередь** с правой стороны.
1. Введите требуемые сведения (имя, модель развертывания и т. д.
1. Выберите **создать** для завершения процесса.

## <a name="configure-your-app-to-use-the-storage-account"></a>Настройка приложения для использования учетной записи хранения

После создания учетной записи хранения, подключение к нему из Visual Studio автоматически обновляет конфигурации службы для проекта, включая URL-адреса и ключи доступа.

Если вы создали облачную службу из Visual Studio с помощью **добавить подключенную службу**, можно проверить соединения, открыв `ServiceConfiguration.Cloud.cscfg` и `ServiceConfiguration.Local.cscfg`.

Если вы создали облачную службу с помощью портала Azure, выполните те же действия, в [создать учетную запись хранилища из Visual Studio](#create-a-storage-account-from-visual-studio) , но выберите существующую учетную запись, а не создавать новую. Visual Studio будет обновлена конфигурация.

Чтобы настроить параметры вручную, используйте страницы свойств в Visual Studio для применимой роли в проект облачной службы (щелкните правой кнопкой мыши роль и выберите **свойства**). Дополнительные сведения см. в разделе [Настройка строки подключения к учетной записи хранения](vs-azure-tools-multiple-services-project-configurations.md#configuring-a-connection-string-for-a-storage-account).

### <a name="about-access-keys"></a>О ключах доступа

На портале Azure отображаются URL-адреса, можно использовать для доступа к ресурсам в каждой из служб хранилища Azure, а также первичный и вторичный ключи доступа для учетной записи. Использовать эти ключи для проверки подлинности запросов к службам хранилища.

Вторичный ключ доступа предоставляет такой же доступ к вашей учетной записи хранения, как первичный ключ доступа и создается как запасной первичный ключ доступа скомпрометирована. Кроме того рекомендуется повторно создать ключи доступа на регулярной основе. Вы можете изменить строку подключения для использования вторичного ключа, одновременно повторно создавая первичный ключ, то можно изменить его для использования первичного ключа, одновременно повторно создавая вторичный ключ.

## <a name="next-steps"></a>Следующие шаги

Дополнительные сведения о публикации приложений в Azure из Visual Studio, см. в разделе [публикация облачной службы с помощью средств Azure](vs-azure-tools-publishing-a-cloud-service.md).
