---
title: Tür Görselleştiriciler ve özel görüntüleyicileri uygulama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], custom viewer
- debugging [Debugging SDK], type visualizer
ms.assetid: abef18c0-8272-4451-b82a-b4624edaba7d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c56d093c2e6380b29c8c9a788ea34d148fbe64b4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="implementing-type-visualizers-and-custom-viewers"></a>Uygulama türü Görselleştiriciler ve özel görüntüleyicileri
> [!IMPORTANT]
>  Visual Studio 2015'te ifade değerlendiricisi uygulama bu şekilde kullanım dışıdır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricileri](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Tür görselleştiriciler ve özel görüntüleyiciler onaltılık sayı döküm basit daha anlamlı bir şekilde belirli bir türdeki verileri görüntülemek bir kullanıcı izin verir. Bir ifade değerlendiricisi (EE), belirli türde veri veya değişkenleri özel görüntüleyiciler ilişkilendirebilirsiniz. Bu özel görüntüleyiciler EE tarafından uygulanır. EE başka bir üçüncü taraf satıcı ya da son kullanıcı gelebilir dış türü görselleştiriciler de destekler.  
  
## <a name="discussion"></a>Tartışma  
  
### <a name="type-visualizers"></a>Tür Görselleştiriciler  
 Visual Studio türü görselleştiriciler ve özel görüntüleyiciler Her nesne için bir izleme penceresinde görüntülenecek listesini ister. Bir ifade değerlendiricisi (EE) bu tür görselleştiriciler ve özel görüntüleyicileri desteklemek istediği her tür için böyle bir liste sağlar. Çağrılar [GetCustomViewerCount](../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) ve [GetCustomViewerList](../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) türü görselleştiriciler ve özel görüntüleyicileri erişen tüm işlemini başlatmak (bkz [Visualizing ve görüntüleme veri](../../extensibility/debugger/visualizing-and-viewing-data.md)arama sırası hakkında ayrıntılı bilgi için).  
  
### <a name="custom-viewers"></a>Özel görüntüleyiciler  
 Özel görüntüleyicileri EE bir özel veri türü için uygulanır ve tarafından temsil edilen [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md) arabirimi. Yalnızca bu belirli özel Görüntüleyicisi uygulayan EE yürütürken, kullanılabilir olduğundan özel bir Görüntüleyici türü Görselleştirici kadar esnek değildir. Özel bir Görüntüleyici uygulama, türünü görselleştiriciler desteği uygulama daha basittir. Ancak, türü görselleştiriciler destekleyen en son kullanıcıya bilgilendirilmesine verileri görselleştirmek için esneklik. Bu tartışma kalanı yalnızca türü görselleştiriciler ilgilidir.  
  
## <a name="interfaces"></a>Arabirimler  
 EE türü görselleştiriciler, Visual Studio tarafından tüketilmesi desteklemek için aşağıdaki arabirimlerini uygular:  
  
-   [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md)  
  
-   [IPropertyProxyEESide](../../extensibility/debugger/reference/ipropertyproxyeeside.md)  
  
-   [IPropertyProxyProvider](../../extensibility/debugger/reference/ipropertyproxyprovider.md)  
  
-   [IEEDataStorage](../../extensibility/debugger/reference/ieedatastorage.md)  
  
-   [IDebugProperty3](../../extensibility/debugger/reference/idebugproperty3.md)  
  
-   [IDebugObject](../../extensibility/debugger/reference/idebugobject.md)  
  
 EE türü görselleştiriciler desteklemek için aşağıdaki arayüzleri kullanır:  
  
-   [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md)  
  
-   [IEEVisualizerServiceProvider](../../extensibility/debugger/reference/ieevisualizerserviceprovider.md)  
  
-   [IDebugBinder3](../../extensibility/debugger/reference/idebugbinder3.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir CLR ifade değerlendiricisi yazma](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)   
 [Görselleştirme ve verileri görüntüleme](../../extensibility/debugger/visualizing-and-viewing-data.md)   
 [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md)