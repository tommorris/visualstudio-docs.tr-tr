---
title: Verileri görüntüleme ve görselleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], viewing data
- debugging [Debugging SDK], visualizing data
ms.assetid: 699dd0f5-7569-40b3-ade6-d0fe53e832bc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ebaa07c8fe70e1842334b0bf7c28eb7491fd9c44
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31132488"
---
# <a name="visualizing-and-viewing-data"></a>Görselleştirme ve verileri görüntüleme
Görselleştiriciler ve özel görüntüleyiciler mevcut verileri hızlı bir şekilde bir geliştirici anlamlı bir şekilde yazın. İfade değerlendiricisi (EE) üçüncü taraf türü görselleştiriciler desteklemek yanı sıra kendi özel görüntüleyiciler sağlayın.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kaç tane türü görselleştiriciler ve özel görüntüleyicileri çağırarak nesne türüyle ilişkili belirler [GetCustomViewerCount](../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) yöntemi. Varsa en az bir türü Görselleştirici veya özel Görüntüleyicisi kullanılabilir, Visual Studio çağırır [GetCustomViewerList](../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) bu görselleştiriciler ve görüntüleyiciler listesini almak için yöntemi (gerçekte listesini `CLSID`uygulamak s görselleştiriciler ve Görüntüleyiciler) ve kullanıcıya sunar.  
  
## <a name="supporting-type-visualizers"></a>Tür Görselleştiriciler destekleme  
 EE türü görselleştiriciler desteklemek için uygulamalıdır arabirimleri vardır. Bu arabirimleri iki geniş kategoriye ayrılabilir: Bu liste türü görselleştiriciler ve bu özellik veri erişim.  
  
### <a name="listing-type-visualizers"></a>Liste türü Görselleştiriciler  
 EE destekleyen uygulamaya türü görselleştiriciler listeleme `IDebugProperty3::GetCustomViewerCount` ve `IDebugProperty3::GetCustomViewerList`. İlgili yöntem çağrısı bu yöntemlere geçirmek [GetCustomViewerCount](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md) ve [GetCustomViewerList](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md).  
  
 [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md) çağırılarak alınır [CreateVisualizerService](../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md). Bu yöntem gerektirir [IDebugBinder3](../../extensibility/debugger/reference/idebugbinder3.md) öğesinden alınan arabirimi [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md) arabirimi geçirilen [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md). `IEEVisualizerServiceProvider::CreateVisualizerService` Ayrıca gerektirir [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md) ve [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md) için geçirilmiş arabirimleri `IDebugParsedExpression::EvaluateSync`. Oluşturmak için gereken son arabirimi `IEEVisualizerService` arabirimi [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md) EE uygulayan arabirimi. Bu arabirim değişiklik görselleştirilen özellik yapılmasına izin verir. Tüm özellik verileri kapsüllenmiş içinde bir [IDebugObject](../../extensibility/debugger/reference/idebugobject.md) de EE tarafından uygulanan arabirimi.  
  
### <a name="accessing-property-data"></a>Özellik verilerine erişme  
 Özellik verilere erişme aracılığıyla yapılır [IPropertyProxyEESide](../../extensibility/debugger/reference/ipropertyproxyeeside.md) arabirimi. Bu arabirim elde etmek için Visual Studio çağırır [QueryInterface](/cpp/atl/queryinterface) almak için özellik nesnesinde [IPropertyProxyProvider](../../extensibility/debugger/reference/ipropertyproxyprovider.md) arabirimi (uygulayan aynı nesne üzerinde uygulanan [ IDebugProperty3](../../extensibility/debugger/reference/idebugproperty3.md) arabirimi) ve ardından çağırır [GetPropertyProxy](../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) elde etmek için yöntemi `IPropertyProxyEESide` arabirimi.  
  
 İçinde ve dışında tüm verileri geçirilen `IPropertyProxyEESide` arabirimi kapsüllenmiş [IEEDataStorage](../../extensibility/debugger/reference/ieedatastorage.md) arabirimi. Bu arabirim bir bayt dizisi temsil eder ve Visual Studio ve EE tarafından uygulanır. Bir özelliğin veriler değiştirilecek olduğunda, Visual Studio oluşturur bir `IEEDataStorage` çağrıları ve yeni veri tutan nesnenin [CreateReplacementObject](../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md) yeni almak için bu veri nesnesi ile `IEEDataStorage` , sırasıyla nesnesi geçirilen [InPlaceUpdateObject](../../extensibility/debugger/reference/ipropertyproxyeeside-inplaceupdateobject.md) özelliğin verileri güncelleştirmek için. `IPropertyProxyEESide::CreateReplacementObject` EE uygulayan kendi sınıfının örneği sağlayan `IEEDataStorage` arabirimi.  
  
## <a name="supporting-custom-viewers"></a>Özel görüntüleyiciler destekleme  
 Bayrak `DBG_ATTRIB_VALUE_CUSTOM_VIEWER` kümesinde `dwAttrib` alanını [DEBUG_PROPERTY_INFO](../../extensibility/debugger/reference/debug-property-info.md) yapısı (yapılan bir çağrı tarafından döndürülen [GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)) nesne ilişkilendirilmiş özel Görüntüleyici olduğunu belirtmek için kendisiyle. Bu bayrak ayarlandığında, Visual Studio edinir [IDebugProperty3](../../extensibility/debugger/reference/idebugproperty3.md) alanından arabirim [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) arabirimi kullanılarak [QueryInterface](/cpp/atl/queryinterface).  
  
 Kullanıcı bir özel Görüntüleyici seçerse, Visual Studio izleyicinin kullanarak özel Görüntüleyicisi'ni başlatır `CLSID` tarafından sağlanan `IDebugProperty3::GetCustomViewerList` yöntemi. Visual Studio sonra çağırır [DisplayValue](../../extensibility/debugger/reference/idebugcustomviewer-displayvalue.md) kullanıcıya değeri gösterir.  
  
 Normalde, `IDebugCustomViewer::DisplayValue` veriler salt okunur bir görünümünü sunar. Verilerde yapılan değişiklikleri izin vermek için EE değişen verilerini bir özellik nesnesinde destekleyen özel bir arabirimini uygulaması gerekir. `IDebugCustomViewer::DisplayValue` Yöntemi, verilerin değiştirilmesi desteklemek için bu özel arabirim kullanır. Yöntem için özel arabirimi arar `IDebugProperty2` olarak arabirimi geçirilen `pDebugProperty` bağımsız değişkeni.  
  
## <a name="supporting-both-type-visualizers-and-custom-viewers"></a>Her ikisi de destekleyen Görselleştiriciler ve özel görüntüleyiciler yazın  
 Bir EE türü görselleştiriciler ve özel izleyicilerin destekleyebilir [GetCustomViewerCount](../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) ve [GetCustomViewerList](../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) yöntemleri. İlk olarak, EE onu sağladığını özel görüntüleyiciler sayısı tarafından döndürülen değer ekler [GetCustomViewerCount](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md) yöntemi. İkinci olarak, EE ekler `CLSID`kendi özel görüntüleyiciler tarafından döndürülen listesine s [GetCustomViewerList](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama görevleri](../../extensibility/debugger/debugging-tasks.md)   
 [Tür Görselleştiricisi ve Özel Görüntüleyici](../../extensibility/debugger/type-visualizer-and-custom-viewer.md)