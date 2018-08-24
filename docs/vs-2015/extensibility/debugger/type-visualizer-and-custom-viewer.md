---
title: Tür görselleştiricisi ve özel Görüntüleyici | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], custom viewer
- debugging [Debugging SDK], type visualizer
ms.assetid: fd3691e6-9c78-4767-846f-43f85ada4375
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d347e7b18722aa8f8901abac3966150b3dca97cf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674546"
---
# <a name="type-visualizer-and-custom-viewer"></a>Tür Görselleştiricisi ve Özel Görüntüleyici
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [tür görselleştiricisi ve özel Görüntüleyici](https://docs.microsoft.com/visualstudio/extensibility/debugger/type-visualizer-and-custom-viewer).  
  
Tür görselleştiricisi bir veri parçasını çok belirli bir biçimde görüntüleyen bir bileşenidir. Bu biçim tamamen Görselleştirici uygulayan kadar son kullanıcıya veya bir üçüncü taraf sağlayıcı görselleştiriciler, olabilir.  
  
 Özel bir Görüntüleyici, bir veri parçasını çok belirli bir biçimde görüntüleyen bir özel ifade değerlendiricisi parçasıdır. Tamamen biçimi (EE) ifade değerlendiricisi ' uygulayan kadar olduğu anlamına gelir özel Görüntüleyici'nin uygulayan kadar bu biçimidir.  
  
## <a name="support-for-type-visualizers-in-an-expression-evaluator"></a>İfade değerlendiricisi, tür Görselleştiricileri desteği  
 Bir EE arabirimleri görselleştiriciler için erişilebilir bir dizi destekleyerek tür görselleştiricileri destekleyebilir: gibi arabirimleri [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md) ve [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md). Ancak, EE tür görselleştiricisi uygulamak için sorumlu olduğunu unutmayın: EE, dış görselleştiriciler yalnızca tür bilgisi erişmesine izin verir. Tür görselleştiricileri EE birlikte sevk ve uygun bir yerden başka bir üçüncü taraf satıcı veya bile son kullanıcı tarafından sağlanan Visual Studio yüklü.  
  
## <a name="support-for-custom-viewers-in-an-expression-evaluator"></a>İfade değerlendiricisi, özel görüntüleyiciler için destek  
 Özel görüntüleyiciler EE veri türünü görüntülemeye ilişkin kodu sağladığı bir EE de destekler. Özel bir Görüntüleyici uygulayan [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md) tüm görevleri, verileri hangi biçimde göstermenin işleyen arabirimi istenen; Görüntüleyici görünümü üzerinde tam denetime sahiptir ve değiştirilecek veri bile izin verebilirsiniz. Ürün gönderildiğinde EE tarafından sağlanan herhangi bir özel görüntüleyiciler EE ile gelir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı bileşenleri](../../extensibility/debugger/debugger-components.md)   
 [İfade değerlendirici](../../extensibility/debugger/expression-evaluator.md)   
 [Hata ayıklama altyapısı](../../extensibility/debugger/debug-engine.md)   
 [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md)   
 [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md)   
 [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md)

