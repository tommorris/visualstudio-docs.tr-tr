---
title: Görselleştirici ve özel Görüntüleyicisi yazın | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], custom viewer
- debugging [Debugging SDK], type visualizer
ms.assetid: fd3691e6-9c78-4767-846f-43f85ada4375
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d419130cd93c6cc2f7dcff132fdafc8986bfd30a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126916"
---
# <a name="type-visualizer-and-custom-viewer"></a>Türü Görselleştirici ve özel Görüntüleyicisi
Türü Görselleştirici çok belirli bir biçimde veri parçası görüntüleyen bir bileşenidir. Bu biçim tamamen Görselleştirici uygulayan kadar son kullanıcı veya bir üçüncü taraf sağlayıcısına görselleştiriciler olabilir.  
  
 Özel bir Görüntüleyici veri parçası çok belirli bir biçimde görüntüler bir özel ifade değerlendiricisi parçasıdır. Tamamen biçimi (EE) ifade değerlendiricisi uygulayan kadar anlamına gelir özel Görüntüleyicisi uygulayan kadar bu biçimidir.  
  
## <a name="support-for-type-visualizers-in-an-expression-evaluator"></a>Bir ifade değerlendiricisi içinde türü Görselleştiriciler desteği  
 Bir EE görselleştiriciler için erişilebilir arabirimleri kümesi destekleyerek türü görselleştiriciler destekleyebilir: gibi arabirimleri [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md) ve [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md). Ancak, EE türü Görselleştirici uygulamak için sorumlu olmadığını unutmayın: EE yalnızca dış görselleştiriciler türü bilgilerini erişime izin. Bu tür görselleştiriciler EE birlikte sevk ve Visual Studio, son kullanıcı tarafından bile veya başka bir üçüncü taraf satıcı tarafından sağlanan uygun bir yerinde yüklenir.  
  
## <a name="support-for-custom-viewers-in-an-expression-evaluator"></a>Bir ifade değerlendiricisi özel izleyicilerin desteği  
 Bir EE EE veri türü görüntülemek için kod sağlayan özel görüntüleyiciler de destekler. Özel bir Görüntüleyici uygulayan [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md) verileri ne olursa olsun biçiminde gösteren, tüm görevleri işleme arabirimi istenen; Görüntüleyici görüntü üzerinde tam denetime sahiptir ve değiştirilecek veri bile izin verebilirsiniz. Ürün gönderildiğinde EE tarafından sağlanan herhangi bir özel görüntüleyiciler EE ile gelir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı bileşenleri](../../extensibility/debugger/debugger-components.md)   
 [İfade değerlendirici](../../extensibility/debugger/expression-evaluator.md)   
 [Altyapısı hata ayıklama](../../extensibility/debugger/debug-engine.md)   
 [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md)   
 [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md)   
 [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md)