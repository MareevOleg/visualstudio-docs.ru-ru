---
title: "Визуализация и просмотр данных | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], viewing data
- debugging [Debugging SDK], visualizing data
ms.assetid: 699dd0f5-7569-40b3-ade6-d0fe53e832bc
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: ca7c86466fa23fb21a932f26dc24e37c71cf29b4
ms.openlocfilehash: 3f2317abd4bfaf6ebf8151812cf15541a1c94ecf
ms.contentlocale: ru-ru
ms.lasthandoff: 04/05/2017

---
# <a name="visualizing-and-viewing-data"></a>Визуализация и просмотр данных
Визуализаторами типов и пользовательских средств просмотра представить данные способом быстро осмысленное разработчика. Вычислитель выражений (Эстония) можно поддерживать визуализаторами типов сторонних разработчиков, а также предоставить свои собственные пользовательские средства просмотра.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]Определяет, сколько визуализаторами типов и пользовательских средств просмотра, связанный с типом объекта путем вызова [GetCustomViewerCount](../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) метод. При наличии хотя бы один тип визуализатора или пользовательское средство просмотра, Visual Studio вызывает [GetCustomViewerList](../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) метод, чтобы получить список этих визуализаторы и средства просмотра (на самом деле список `CLSID`, которые реализуют визуализаторы и средства просмотра) и показывает их пользователю.  
  
## <a name="supporting-type-visualizers"></a>Поддержка визуализаторами типов  
 Существует несколько интерфейсов, которые должны реализовывать EE для поддержки визуализаторами типов. Эти интерфейсы можно разделить на две большие категории: те, которые перечислены визуализаторами типов и те, которые обращаются к данным свойства.  
  
### <a name="listing-type-visualizers"></a>Листинг визуализаторами типов  
 EE поддерживает вывод визуализаторами типов в своей реализации `IDebugProperty3::GetCustomViewerCount` и `IDebugProperty3::GetCustomViewerList`. Эти методы передачи вызова соответствующих методов [GetCustomViewerCount](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md) и [GetCustomViewerList](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md).  
  
 [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md) получается путем вызова метода [CreateVisualizerService](../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md). Этот метод требует [IDebugBinder3](../../extensibility/debugger/reference/idebugbinder3.md) интерфейс, получаемый из [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md) передается интерфейс [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md). `IEEVisualizerServiceProvider::CreateVisualizerService`также требуется [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md) и [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md) интерфейсы, которые были переданы `IDebugParsedExpression::EvaluateSync`. Последний интерфейс, необходимый для создания `IEEVisualizerService` интерфейс [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md) интерфейс, который реализует EE. Этот интерфейс позволяет вносить изменения в свойство визуализации. Все свойства данных, содержащийся в [IDebugObject](../../extensibility/debugger/reference/idebugobject.md) интерфейс, который также реализован EE.  
  
### <a name="accessing-property-data"></a>Доступ к данным, свойство  
 Доступ к данным свойства выполняется с помощью [IPropertyProxyEESide](../../extensibility/debugger/reference/ipropertyproxyeeside.md) интерфейса. Чтобы получить этот интерфейс, Visual Studio вызывает [QueryInterface](/cpp/atl/queryinterface) для свойства объекта, чтобы получить [IPropertyProxyProvider](../../extensibility/debugger/reference/ipropertyproxyprovider.md) интерфейс (реализованный на тот же объект, реализующий [IDebugProperty3](../../extensibility/debugger/reference/idebugproperty3.md) интерфейс), а затем вызывает [GetPropertyProxy](../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) метод, чтобы получить `IPropertyProxyEESide` интерфейс.  
  
 Все данные, передаваемые в `IPropertyProxyEESide` интерфейс инкапсулируется в [IEEDataStorage](../../extensibility/debugger/reference/ieedatastorage.md) интерфейса. Этот интерфейс представляет собой массив байтов и реализуется с помощью Visual Studio и EE. Если данные свойства должен быть изменен, Visual Studio создает `IEEDataStorage` объект, содержащий новые данные и вызовы [CreateReplacementObject](../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md) с этим объектом данных, чтобы получить новый `IEEDataStorage` объект, который в свою очередь, передается [InPlaceUpdateObject](../../extensibility/debugger/reference/ipropertyproxyeeside-inplaceupdateobject.md) для обновления данных свойства. `IPropertyProxyEESide::CreateReplacementObject`позволяет EE создать свой собственный класс, реализующий `IEEDataStorage` интерфейса.  
  
## <a name="supporting-custom-viewers"></a>Поддержка пользовательских средств просмотра  
 Флаг `DBG_ATTRIB_VALUE_CUSTOM_VIEWER` задается в `dwAttrib` поле [DEBUG_PROPERTY_INFO](../../extensibility/debugger/reference/debug-property-info.md) структуры (возвращается путем вызова [GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)) для указания, что объект имеет пользовательские средства просмотра, связанного с ним. Если этот флаг установлен, Visual Studio получает [IDebugProperty3](../../extensibility/debugger/reference/idebugproperty3.md) интерфейс из [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) интерфейса с помощью [QueryInterface](/cpp/atl/queryinterface).  
  
 Если пользователь выбирает пользовательское средство просмотра, Visual Studio создает пользовательское средство просмотра, используя средство просмотра `CLSID` предоставляемые `IDebugProperty3::GetCustomViewerList` метод. Visual Studio вызывает [DisplayValue](../../extensibility/debugger/reference/idebugcustomviewer-displayvalue.md) отображать значение для пользователя.  
  
 Как правило `IDebugCustomViewer::DisplayValue` отображается только для чтения представление данных. Чтобы разрешить изменения в данные, EE необходимо реализовать пользовательский интерфейс, поддерживающий изменяющихся данных в объект свойства. `IDebugCustomViewer::DisplayValue` Метод использует этот пользовательский интерфейс для поддержки изменения данных. Метод ищет пользовательский интерфейс `IDebugProperty2` интерфейса, переданного в качестве `pDebugProperty` аргумент.  
  
## <a name="supporting-both-type-visualizers-and-custom-viewers"></a>Поддержка типов визуализаторы и пользовательские средства просмотра  
 Может поддерживать EE визуализаторами типов и пользовательских средств просмотра в [GetCustomViewerCount](../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) и [GetCustomViewerList](../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) методы. Во-первых, EE добавляет число пользовательских средств просмотра, он предоставляет значение, возвращаемое [GetCustomViewerCount](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md) метод. Во-вторых, добавляет EE `CLSID`s свои собственные пользовательские средства просмотра в список возвращенных [GetCustomViewerList](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md) метод.  
  
## <a name="see-also"></a>См. также  
 [Задачи отладки](../../extensibility/debugger/debugging-tasks.md)   
 [Визуализатор типов и пользовательское средство просмотра](../../extensibility/debugger/type-visualizer-and-custom-viewer.md)